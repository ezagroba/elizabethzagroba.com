.. title: You build it, you run it, and you fix it
.. date: 20 May 2019

<p name="e646" id="e646" class="graf graf--p graf-after--h3">During a meeting of our unit at work today, we were asked if we wanted to become a member of the elite squad of people that are on-call for our software. Our philosophy is: we built it, so we know the most about keeping it up and running. In my next meeting, somebody asked if we ever write bug reports for ourselves. Both reminded me that I wanted to use and fix up a piece of software I wrote.</p>

```bash
$ python3 httperrors.py
There are 15 links outside of the 200 or 300 range of http responses on your site.
```

<p name="d51d" id="d51d" class="graf graf--p graf-after--figure">After using <a href="https://www.screamingfrog.co.uk/broken-link-checker/" data-href="https://www.screamingfrog.co.uk/broken-link-checker/" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">ScreamingFrog</a> software to scan the pages for http error response codes, I decided I could build something easier-to-use myself and test it using my own website, <a href="https://elizabethzagroba.com/" data-href="https://elizabethzagroba.com/" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">elizabethzagroba.com</a>. I wrote a draft that worked initially, but did some things that weren’t great Python. Thanks to my friends <a href="https://twitter.com/DavidaMarion" data-href="https://twitter.com/DavidaMarion" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">Davida</a> and Becky who reviewed and improved my code. You can see what they suggested in the <a href="https://github.com/ezagroba/linkchecker/issues?q=is%3Aissue+is%3Aclosed" data-href="https://github.com/ezagroba/linkchecker/issues?q=is%3Aissue+is%3Aclosed" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">older tickets in my Github repo</a>.</p><p name="c3e3" id="c3e3" class="graf graf--p graf-after--p">Here’s what I have now:</p>

```python
# Mission: Find http codes that aren't in the 200 or 300 range for all the links on a single page

import os
import errno
import http
import requests
import ssl
import string
import urllib.request
from bs4 import BeautifulSoup
from bs4 import SoupStrainer


MY_SITE = "http://www.elizabethzagroba.com"
my_site_response = requests.get(MY_SITE)
only_external_links = SoupStrainer(target="_blank")
page = str(BeautifulSoup(my_site_response.content, "html.parser", parse_only=only_external_links))


def get_url(website):
  start_link = website.find("a href")
  if start_link == -1:
    return None, 0
  start_quote = website.find('"http', start_link)
  end_quote = website.find('"', start_quote + 1)
  stripped_url = website[start_quote + 1: end_quote]
  return stripped_url, end_quote


try:
  os.remove('list_of_all_links.txt')
except OSError:
  pass

count = 0
with open('list_of_all_links.txt', 'a') as file:
  while True: 
    url, n = get_url(page)
    page = page[n:]
    if url:
      try:
        req = urllib.request.urlopen(url)
      except urllib.error.URLError as explanation:
        file.write(str(explanation) + " " + url + '\n')
        count += 1
    else:
      print("There are " + str(count) + " links outside of the 200 or 300 range of http responses on your site.")
      break

```


<p name="018e" id="018e" class="graf graf--p graf-after--figure">It looks for the external links on my website, tries to open them, and writes them to a file if the response code isn’t in the 200 or 300 range. There are things I’d like to improve. I’ve noted some here. But tonight’s scope is: run it and fix it.</p><p name="c4ca" id="c4ca" class="graf graf--p graf-after--p">I run the file on my machine. Fifteen sites I link to come back with error responses. Here’s the file it generated:</p>

```text
HTTP Error 403: Forbidden https://www.mendix.com/
HTTP Error 403: Forbidden https://medium.com/@ezagroba
HTTP Error 403: Forbidden https://medium.com/@ezagroba/have-i-tried-enough-weird-stuff-7ed4105ae994
HTTP Error 403: Forbidden https://medium.com/@ezagroba/doubt-builds-trust-9cee937dc5d1
HTTP Error 403: Forbidden https://conference.eurostarsoftwaretesting.com/conference/programme/2018/#Wednesday-c67b
HTTP Error 403: Forbidden https://www.phpconference.nl/
HTTP Error 404: Not Found http://www.romaniatesting.ro/sessions/succeeding-as-an-introvert/
HTTP Error 404: Not Found http://www.ministryoftesting.com/training-events/testsbash-philadelphia-2016/
HTTP Error 403: Forbidden http://www.associationforsoftwaretesting.org/training/courses/
HTTP Error 403: Forbidden http://codeacademy.com/
HTTP Error 403: Forbidden http://hackdesign.org
HTTP Error 403: Forbidden http://testobsessed.com/
<urlopen error [Errno 8] nodename nor servname provided, or not known> http://developersbestfriend.com
HTTP Error 999: Request denied http://www.linkedin.com/in/ezagroba/
HTTP Error 403: Forbidden https://medium.com/@ezagroba
```

<p name="d0f0" id="d0f0" class="graf graf--p graf-after--figure">I notice most of the error codes were <code class="markup--code markup--p-code">403</code> responses, so I try a few of those pages manually. Those few succeed, so I don’t bother checking the rest. A<code class="markup--code markup--p-code">403</code> status is <a href="https://httpstatuses.com/403" data-href="https://httpstatuses.com/403" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">Forbidden access</a>, so I think it has something to do with these sites having logins. But I don’t need to logins to see the pages I’m linking to. Then I notice that some of the pages are pointing to http instead of https. I don’t know exactly what’s wrong. It’s getting late, so rather than diving in, I write two bugs: <a href="https://github.com/ezagroba/linkchecker/issues/8" data-href="https://github.com/ezagroba/linkchecker/issues/8" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">one about investigating 403s</a>, <a href="https://github.com/ezagroba/linkchecker/issues/9" data-href="https://github.com/ezagroba/linkchecker/issues/9" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">one about updating http to https</a>.</p><p name="442c" id="442c" class="graf graf--p graf-after--p">Next, I look at the other error codes. The <code class="markup--code markup--p-code">999</code> one I’ve seen before. It’s some weird LinkedIn thing. I don’t add a bug because it’s not interesting to fix. One site I’m not able to reach the domain of at all, so I message the owner to see if it’s still being maintained. The <code class="markup--code markup--p-code">404</code> codes are from sites that still exist where the pages have been taken down; fixable, but frustrating. They prove I spoke at these conferences. When these pages die, so does proof of my hard work. Sigh. I remove those links from my site, reload to confirm the fix made it to production, and run the script again. We’re down from 15 to 13 errors, as expected.</p>

```bash
$ python3 httperrors.py
There are 13 links outside of the 200 or 300 range of http responses on your site.
```

<p name="a400" id="a400" class="graf graf--p graf-after--figure graf--trailing">In looking at this code again, I’m reminded of the original motivation and my vision for myself: run it against any site, and know when links break on elizabethzagroba.com. <a href="https://github.com/ezagroba/linkchecker/issues" data-href="https://github.com/ezagroba/linkchecker/issues" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">I added some issues that I’ll pick up another day</a>. I’ll be ready to build again. But for now, goodnight.</p></div></div></section>
</section>

*Originally published on [Medium](https://medium.com/@ezagroba/you-build-it-you-run-it-and-you-fix-it-ba24151c3f2b).*

