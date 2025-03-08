# `head` tag
- The `head` tag element contains all the metadatas related to your page. All the elements put in the head are not visible in the window of the browser.
- A lot of meta data exist, some specific to some CMS.

## Usage
You can find inside the `head`:
- `title` of the webpage
- `script` asynchronous script calls
- metadata
- `style` CSS code embed (critical CSS)
- JavaScript code embed

## Resources
- [HEAD - A free guide to head elements](https://intranet.alxswe.com/rltoken/EZtKJx4_IPYRKnC40TOIig "HEAD - A free guide to head elements")
# elements
## Meta
- Below are the essential elements for any web document (websites/apps):

``` html
<!--
  The following 2 meta tags *must* come first in the <head>
  to consistently ensure proper document rendering.
  Any other head element should come *after* these tags.
-->
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">

```

`meta charset` - defines the encoding of the website, `utf-8` is the standard
`meta name="viewport"` - viewport settings related to mobile responsiveness
`width=device-width` - use the physical width of the device (great for mobile!)
`initial-scale=1` - the initial zoom, 1 means no zoom
### Meta charset

The `meta` charset declares the page’s character encoding.

```html
<head>
    <!-- Set character encoding for the document -->
    <meta charset="value">
</head>
...
```

#### Resources

- [meta: The Document-level Metadata element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/lGlcynIJnOghOV8WRM1KQw "meta: The Document-level Metadata element - HTML: Hypertext Markup Language | MDN")
- [Declaring character encodings in HTML](https://intranet.alxswe.com/rltoken/bbD9Y6adMOvzaMAv8tOdgA "Declaring character encodings in HTML")
- [Meta Charset](https://intranet.alxswe.com/rltoken/RX02pjKDo2KIxNzDT65qog "Meta Charset")

### Viewport

The meta `viewport` gives information about the initial size of the viewport.

Tip: The viewport is used by mobile devices only.

Accessibility tip: Never use `maximum-scale=1.0`. [It prevents the user from zooming in on the website](https://intranet.alxswe.com/rltoken/7rvXOxycKKjd9GgCM04PZA "It prevents the user from zooming in on the website"). It causes an accessibility issue.

``` html
<head>
    <!-- Viewport for responsive web design -->
    <meta name="viewport" content="key=value, key=value">
</head>
```

#### Resources

- [Responsive Design With Viewport Control](https://intranet.alxswe.com/rltoken/0yCM0qBDrvmhFc3Rc1Wh4g "Responsive Design With Viewport Control")

### Title

The `title` meta tag defines the title of the web page.

Tip: The title is only visible on the tab/window of your browser.

Warning! The title should always have less than 56 characters.

``` html
  <head>
    <!-- Document Title -->
    <title>Page title</title>
  </head>
...
```

#### Resources

- [The ideal width of the SEO title • Yoast](https://intranet.alxswe.com/rltoken/iiw66IIVemsN72CyLFChxw "The ideal width of the SEO title • Yoast")

### Meta description

```
<head>
    ...
    <!-- Meta Description -->
    <meta name="description" content="Description of the page less than 150 characters">
  </head>
```

#### Resources

- [The ideal length of a meta description • Yoast](https://intranet.alxswe.com/rltoken/HPoXoWYwQS5PLvINc_ksVA "The ideal length of a meta description • Yoast")

### Favicons
``` html
<head>
    ...
    <!-- Standard favicon -->
	    <link rel="icon" type="image/x-icon"
	    href="https://example.com/favicon.ico">
    <!-- Recommended favicon format -->
    <link rel="icon" type="image/png" href="https://example.com/favicon.png">
    ...
  </head>
```

#### Resources
- [Favicon & App Icon Generator](https://intranet.alxswe.com/rltoken/dE8zprnn34BJ9hqM13XfTA "Favicon & App Icon Generator")
- [Favicon Generator for all platforms: iOS, Android, PC/Mac…](https://intranet.alxswe.com/rltoken/ZaE4xx36mKFIMqlHd88csQ "Favicon Generator for all platforms: iOS, Android, PC/Mac...")
- [Obsessive cheat sheet to favicon sizes/types.)](https://intranet.alxswe.com/rltoken/lJIj7qMYgTay169LNImDuw "Obsessive cheat sheet to favicon sizes/types.)")
- [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? | CSS-Tricks](https://intranet.alxswe.com/rltoken/twLUZkUiSfjh335aw8hhyA "Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? | CSS-Tricks")
- [PNG favicons - caniuse](https://intranet.alxswe.com/rltoken/R3Bv_GssJPm0wlqYqxvt4w "PNG favicons - caniuse")

---

## Tag attributes

Attributes provide additional information or instruction for an HTML element. It is **always** included inside the opening tag.

### Data-* attribute

It is possible to declare any attribute using the `data-` prefix

``` html
<tag data-extra-attr="value">some content</tag>
```

### Resources

- [HTML attribute reference - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/A2kOSlPgrXmocxuEqtfIUA "HTML attribute reference - HTML: Hypertext Markup Language | MDN")