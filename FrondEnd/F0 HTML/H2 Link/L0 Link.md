## HTML Links - Hyperlinks
- HTML links are hyperlinks.
- You can click on a link and jump to another document.
- When you move the mouse over a link, the mouse arrow will turn into a little hand.

`<a href="link" >link text</a>` : syntax of link.
By default, links will appear as follows in all browsers:
- An unvisited link is `underlined` and `blue`
- A visited link is `underlined` and `purple`
- An active link is `underlined` and `red`

## Attribute
### href
-  `Absolute URLs`  : start with https//Doman Name/path/to
- `Relative URLs` : /path/to.
### target
The `target` attribute specifies where to open the linked document.
The `target` attribute can have one of the following values:
- `_self` - Default. Opens the document in the same window/tab as it was clicked
- `_blank` - Opens the document in a new window or tab
- `_parent` - Opens the document in the parent frame
- `_top` - Opens the document in the full body of the window

### Email Address
Use `mailto:` inside the `href` attribute to create a link that opens the user's email program (to let them send a new email):
``` html
<a href="mailto:someone@example.com">Send email</a>
```

### Link Titles
The `title` attribute specifies extra information about an element. The information is most often shown as a tooltip text when the mouse moves over the element.

``` html
<a href="https://www.w3schools.com/html/" title="Go to W3Schools HTML section">Visit our HTML Tutorial</a>
```

