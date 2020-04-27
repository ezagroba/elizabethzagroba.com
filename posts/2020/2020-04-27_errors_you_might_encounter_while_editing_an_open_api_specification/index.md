.. title: Errors You Might Encounter While Editing an Open API Specification
.. date: 27 April 2020
.. tags: swagger, open-api, api-specs, apis


One of the tasks for my team last week was updating an existing GET API call in our specification with some new fields. The [Open API Specification](https://swagger.io/specification/), formerly known as Swagger, allows you to provide the details for building in API in a compact, informative way. When you've got the authentication set up correctly, you can use the examples to actually call the API right from the spec!

My team builds with a framework that has the power to auto-generate API specs in this format. We've chosen to write them ourselves rather than have them auto-generated so we can be more specific in what kinds of errors and error messaging people will encounter for different calls. For example, a 404 Not Found might make sense on a GET call for a specific resource, but not for a search call.

When you open [http://editor.swagger.io/](http://editor.swagger.io/), you should see a two-pane view of the editor on the left and the rendering on the right. If you've opened this URL before, your browser session will remember and display your most recent changes. If it's the first time you've opened it, the example specification of the Swagger Petstore should appear like this:

![](/images/posts/2020/petstore-example-spec.png "Petstore example spec")

I hope that in describing the errors I encountered, you can keep an eye on them as you're editing rather than having to go back through the specification at the end to figure out what went wrong. 

## Errors I encountered

### Red errors in the box at the top and next to line numbers in editor

![](/images/posts/2020/swagger-red-error-at-top.png)

Indentation errors and using reserved characters (I found square brackets, dashes, colons at least fall into this category) in unexpected ways will likely give you an error in a red box between the navigation and the title of the spec. 

If you're lucky, the error corresponds to the line it mentions, you find a red X on that line, and you'll be able to figure out what went wrong there. 

If you're less lucky, the line mentioned in the red box will refer to the beginning of the next code block that's unparsable because of the syntax error, or the first place where the reserved character you've used incorrectly is actually used correctly. 

The hardest part about these errors is that you may not notice them. If you're scrolled down the page far enough, you won't see the error box or the red X as you're creating the error. 

### Spinning without loading

![](/images/posts/2020/swagger-spinner-failed-reference.png)

If you're getting a spinner where a part of the specification should be loading, you've got a issue with the reference to a schema. [Schemas](https://swagger.io/docs/specification/data-models/) allow you to chunk out and reuse part of the spec, with a reference to them in another place. 

I kept getting the spinner when I referred to a schema that didn't exist, either because I'd updated the name (but not the reference to it) or because I'd screwed up whether it was singular or plural. Fixing the error isn't always enough to make this particular error disappear. Reloading the page will make it re-evaluate what you've got. 

### 😱 could not render this component, see the console.

What a fun and exciting mistake you've made in the specification, to cause this very comforting and reassuring error message. 

![](/images/posts/2020/swagger-scream.png)

Like the endless spinning error, this one means something very specific: you've designated something as an array, but you haven't explained what kinds of items appear in the array. [Adding a description or reference in the items section](https://swagger.io/docs/specification/data-models/data-types/#array) should do the trick. 

## Editing without the Open API editor

It's possible the Open API web editor was not the best tool for this job. 

![](/images/posts/2020/swagger-vs-code.png)

The [Visual Studio Code Open API plugin](https://marketplace.visualstudio.com/items?itemName=42Crunch.vscode-openapi) did make the red errors obvious enough that you could see them from anywhere in the document. It also gave me the collapsed version of the longer spec in alphabetical order. This allowed me to navigate around without remembering the line numbers of where I dumped the schema separately from the overall spec. Unfortunately the extension didn't catch when I referred to a spec that didn't exist, but I expect seeing the list of schemas on the side would help discover this mistake. The extension also didn't notice if I didn't define the objects in an array.  

There's also an [Open API spec tool for offline use](https://github.com/swagger-api/swagger-ui), but the instructions went beyond the interest I had for this blog post. Try it out yourself, and maybe I will the next time I've got to edit these specs. 
