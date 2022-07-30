.. title: The Power of Separating Setup and Teardown From Your Tests
.. date: 30 July 2022
.. description: Pytest gives you a failure in the test, and an error on setup or teardown.
.. tags: python, testing, pytest

This week, I was trying to find an explanation for my colleagues about when it's better to separate the setup and teardown of your tests from the test code itself. I was hoping that pytest's own documentation would have a recommendation, since our test code for this particular repository is written in Python with pytest as a test runner. Pytest does explain [many features of fixtures](https://docs.pytest.org/en/7.1.x/how-to/fixtures.html), and [what different test output can look like](https://docs.pytest.org/en/7.1.x/how-to/fixtures.html), but not the power of combining them. That's what I'd like to explain here. 

## An example

I can't show you the code I was looking at from work, so here is a relatively trivial and useless example I was able to contrive in an hour. (Sidebar: I once tested an address field that truncated the leading zeroes of post codes, so though this test may be trivial, testing that the post code made it to the database intact can provide value.)

There's an API called Zippopotamus that can either:
1. take a city and state, and return you details about matching places; or
2. take a post code, and return you details about matching places.

I've got two tests below, both trying to accomplish the same thing: see if all the post codes returned for the city of Waterville in the state of Maine also include Waterville in their results. 

- Setup: get list of post codes for Waterville, Maine
- Test: for each post code, check that `Waterville` is in the list of matching places

```python
import requests
import pytest

zippopotamus_url = "https://api.zippopotam.us/us"


@pytest.fixture()
def post_codes():
    response = requests.get(f'{zippopotamus_url}/me/waterville')
    assert response.status_code == 200
    places = response.json()['places']
    post_codes = [place['post code'] for place in places]
    return post_codes


class TestZippopotamus:

    def test_setup_included_waterville_maine_included_in_each_post_code(self):
        response = requests.get(f'{zippopotamus_url}/me/waterville')
        assert response.status_code == 200
        places = response.json()['places']
        post_codes = [place['post code'] for place in places]
        for post_code in post_codes:
            response = requests.get(f'{zippopotamus_url}/{post_code}')
            assert response.status_code == 200
            places = response.json()['places']
            assert any(place['place name'] == 'Waterville' for place in places)

    def test_setup_separated_waterville_maine_included_in_each_post_code(self, post_codes):
        for post_code in post_codes:
            response = requests.get(f'{zippopotamus_url}/{post_code}')
            assert response.status_code == 200
            places = response.json()['places']
            assert any(place['place name'] == 'Waterville' for place in places)

```

The first test shows the setup included in the test. The second test has the setup separated from the test. It appears in the fixture called `post_codes`. 

```bash
(venv) ez@EZ-mini blog-examples % pytest                     
========================== test session starts ===========================
platform darwin -- Python 3.10.1, pytest-7.1.2, pluggy-1.0.0
rootdir: /Users/ez/blog-examples
collected 2 items                                                        

test_error_vs_failure_pytest.py ..                                 [100%]

=========================== 2 passed in 1.46s ============================
```

When you run these tests, they both pass. One test is a little longer, which you may find easier to follow than navigating around in the code, or harder to follow because there's code that's more about data collection than what we want to test. I find it yucky (a technical term) to have more than one thing called `request` or `response` in a single test, but these are all personal preferences. 

Now imagine instead of `waterville` in the API requests, I've gone on auto-pilot and typed `whatever` in the setup for the tests. Here's what pytest gives us as the output. 

```bash
(venv) ez@EZ-mini blog-examples % pytest
========================== test session starts ===========================
platform darwin -- Python 3.10.1, pytest-7.1.2, pluggy-1.0.0
rootdir: /Users/ez/blog-examples
collected 2 items                                                        

test_error_vs_failure_pytest.py FE                                 [100%]

================================= ERRORS =================================
_ ERROR at setup of TestZippopotamus.test_setup_separated_waterville_maine_included_in_each_post_code _

    @pytest.fixture()
    def post_codes():
        response = requests.get(f'{zippopotamus_url}/me/whatever')
>       assert response.status_code == 200
E       assert 404 == 200
E        +  where 404 = <Response [404]>.status_code

test_error_vs_failure_pytest.py:10: AssertionError
================================ FAILURES ================================
_ TestZippopotamus.test_setup_included_waterville_maine_included_in_each_post_code _

self = <test_error_vs_failure_pytest.TestZippopotamus object at 0x101f4c160>

    def test_setup_included_waterville_maine_included_in_each_post_code(self):
        response = requests.get(f'{zippopotamus_url}/me/whatever')
>       assert response.status_code == 200
E       assert 404 == 200
E        +  where 404 = <Response [404]>.status_code

test_error_vs_failure_pytest.py:20: AssertionError
======================== short test summary info =========================
FAILED test_error_vs_failure_pytest.py::TestZippopotamus::test_setup_included_waterville_maine_included_in_each_post_code
ERROR test_error_vs_failure_pytest.py::TestZippopotamus::test_setup_separated_waterville_maine_included_in_each_post_code
======================= 1 failed, 1 error in 0.71s =======================
```

Neither test passes. They both get mad at the same spot, where they're checking that they got the post codes for "Whatever, Maine" and found that, oh wait no, they haven't been able to do that. 

But one test fails and one test errors: The test with the setup included fails. The test with the setup in the fixture errors. This difference is why I prefer to separate my setup (and teardown, which behaves the same way) from my test code. 

## The power of separating setup and teardown from your tests

1. More of the test code is about what's being tested, instead of being about how you get to the right place.

2. Pytest will give you an error when code fails in the setup or teardown, and a failure when the code inside the test fails.

3. If you're reusing setup or teardown, you'll only have to fix an issue in the code in one spot.

4. If you're running a bunch of tests with shared setup or teardown in a pipeline, it'll be easier to diagnose when something outside what you're trying to test has gone awry. 


## Reasons to keep the setup and teardown with your tests

1. You are early enough in the development process that the setup and teardown don't need to be used anywhere else yet. You can extract them when they do, but for now, it's a little faster to read with everything in one place.

2. If you don't have your IDE setup correctly, PyCharm may not let you Ctrl + click through the code to follow the fixture code. ([Here's how to setup PyCharm to recognize pytest fixtures.](https://www.jetbrains.com/help/pycharm/testing-frameworks.html#a036958d))

3. If you don't trust someone reading or debugging the test (other colleagues, future you, or possibly even other colleagues after you've moved to a different team) to be able to follow the code through to the fixtures. Or no one else is looking at the code!


## What have I missed?

What other reasons are there? What do you tend to do for your team when your code is shared? What do you tend to do for yourself when you only have your future self to help out? How would you have written this Python code differently? Which articles do you point to when you're explaining a separation of concerns? 