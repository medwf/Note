# Selector
## Different types of selectors
- There are many different types of selectors:

| Selector name                                              | What does it select                                                                                              | Example                                                                                  |
| ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Element selector (sometimes called a tag or type selector) | All HTML elements of the specified type.                                                                         | `p`  <br>selects `<p>`                                                                   |
| ID selector                                                | The element on the page with the specified ID. On a given HTML page, each id value should be unique.             | `#my-id`  <br>selects `<p id="my-id">` or `<a id="my-id">`                               |
| Class selector                                             | The element(s) on the page with the specified class. Multiple instances of the same class can appear on a page.  | `.my-class`  <br>selects `<p class="my-class">` and `<a class="my-class">`               |
| Attribute selector                                         | The element(s) on the page with the specified attribute.                                                         | `img[src]`  <br>selects `<img src="myimage.png">` but not `<img>`                        |
| Pseudo-class selector                                      | The specified element(s), but only when in the specified state. (For example, when a cursor hovers over a link.) | `a:hover`  <br>selects `<a>`, but only when the mouse pointer is hovering over the link. |
| Universal selector                                         | select all elements in body                                                                                      | `* {}`  select all elements in body.                                                     |

There are many more selectors to discover. To learn more, see the MDN [Selectors guide](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors).
## Selecting multiple elements:
- You can also select multiple elements and apply a single ruleset to all of them.
- Separate multiple selectors by commas.
```CSS
p,
li,
h1 {
	color: red;
}
```


## Descendent and direct child
### Descendent:
- Selector multi element for example:
```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <style>
    /* select all span in div change color to read*/
     div span {
	     color: red;
     }

    </ style>
    <title>ID in css</title>
  </head>
  <body>
    <div>
      <h2>1 <span>00</ span></h2>
      <h1>2 <span>01</ span></h1>
    </div>
  </body>
</html>
```

## Direct child:
- Selector multi element for example:
```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <style>
    /* select only closer span in div change color to read*/
     div > span {
	     color: red;
     }

    </ style>
    <title>ID in css</title>
  </head>
  <body>
    <div>
      <h2>1 <span>00</ span></h2>
      <h1>2 <span>01</ span></h1>
      <span>01</ span>
    </div>
  </body>
</html>
```

