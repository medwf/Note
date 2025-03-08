## Image

The image element (`<img>`) allows us to use images on a website.

|Type|Self-closing|
|---|---|
|Inline|Yes|

Accessibility tip: You should always have an `alt` on your image. With text or without, depending if your image is decorative or not. The `alt` should describe what is inside your image. Never use the title of your blog post or some similar text.

Tip: Always specify the width and height of the image. It will avoid layout jank during image loading. Chrome and other browsers are working (Firefox already has that functionality) on improving the experience.

```html
<!-- using a url relative to the HTML page -->
<img src="img/dog.jpg" alt="My dog Hugo sitting in the grass." width="300" height="200">
<!-- using an absolute url from another website -->
<img src="http://dogpictures.com/dog.jpg" alt="A placeholder image of a dog." width="300" height="200">
```

### Resources

- [img: The Image Embed element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/Y7kLrLlbtbEKTPku4rDwvg "img: The Image Embed element - HTML: Hypertext Markup Language | MDN")
- [Essential Image](https://intranet.alxswe.com/rltoken/d2nDdW5Cxc1VPBMm3RKudw "Essential Image")

### Placeholder generators

- [https://placebear.com/](https://intranet.alxswe.com/rltoken/gtz79yj9sNy_NuuJEZEUOw "https://placebear.com/")
- [https://picsum.photos/](https://intranet.alxswe.com/rltoken/U_v_8pJqB8Pq30sSdYkbIQ "https://picsum.photos/")
- [http://placehold.it/](https://intranet.alxswe.com/rltoken/Lln2tI-UFfdmUdp02m9CjQ "http://placehold.it/")
- [https://www.placecage.com/](https://intranet.alxswe.com/rltoken/xDnFkniWBDlK9jF6Dj_rUQ "https://www.placecage.com/")

## Image formats

`JPEG`, `PNG`, `GIF`, `SVG` and `WebP` are the most common format of image used on the Web. Each of them has his own particularity and usage. It’s essential to understand these and always ensure that they are optimized to be shown on a webpage.

- [Support image format](https://intranet.alxswe.com/rltoken/yJZy5gFPvGNSzFQ9eWl8_A "Support image format")
- [JPEG, GIF, PNG OR SVG - Which should You use?](https://intranet.alxswe.com/rltoken/8xDW6SoiF7mFKcEvP2hr-A "JPEG, GIF, PNG OR SVG - Which should You use?")
- [SVG vs PNG vs JPG: Image Format Pros & Cons | Design Shack](https://intranet.alxswe.com/rltoken/I9CsT7NAI7D9QSV5QY7ISw "SVG vs PNG vs JPG: Image Format Pros & Cons | Design Shack")
- [SVGOMG - SVGO’s Missing GUI](https://intranet.alxswe.com/rltoken/B4mUDGTzEr4YK34yHu5bxQ "SVGOMG - SVGO's Missing GUI")

Warning! It’s not unusual to find websites that load images with more than 1 MB. It’s obviously not recommended. Nowadays, people browse the web more using a wireless connection and then could be limited in their data package. It’s important to always keep that in mind.

## Picture

The `<picture>` HTML tag is used as a wrapper to combine different sources which provide different versions of an image. (It can also be use to offer different versions for different devices/display.)

```
<picture>
  <source srcset="/img/logo.webp" type="image/webp">
  <source srcset="/img/logo.jp2" type="image/jp2">
  <img src="/img/logo.jpg">
</picture>
```

### Resources

- [picture: The Picture element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/o2fS0T00D8ExCiXwXa2_uQ "picture: The Picture element - HTML: Hypertext Markup Language | MDN")
- [Bye raster, hello vector: 3 ways to use SVG easier · Devbridge](https://intranet.alxswe.com/rltoken/OVIy7R80-ckahOcLe2FzBA "Bye raster, hello vector: 3 ways to use SVG easier · Devbridge")