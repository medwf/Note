## Create a Bookmark in HTML
- Bookmarks can be useful if a web page is very long.
- To create a bookmark - first create the bookmark, then add a link to it.
- When the link is clicked, the page will scroll down or up to the location with the bookmark.

- First, use the `id` attribute to create a bookmark:
``` html
<h2 id="C4">Chapter 4</h2>

### Then, add a link to the bookmark ("Jump to Chapter 4"), from within the same page:
<a href="#C4">Jump to Chapter 4</a>
```

- You can also add a link to a bookmark on another page:
``` html
<a href="html_demo.html#C4">Jump to Chapter 4</a>
```
