## `video` tag

The `<video>` HTML Tag gives the capability to add a native video player in your HTML.

Accessibility tip: It’s essential to provide an alternative text in case the `<video>` tag is not supported or the video doesn’t exist anymore.

Avoid using the attribute `autoplay` and let the user decide if they want to play the video. Of course, for videos used in the background, `autoplay` and `loop` will probably be essential.

``` html
<video width="640" height="480" src="https://archive.org/download/Popeye_forPresident/Popeye_forPresident_512kb.mp4" controls>
  Sorry, your browser doesn't support HTML5 <code>video</code>, but you can
  download this video from the <a href="https://archive.org/details/Popeye_forPresident" target="_blank">Internet Archive</a>.
</video>
```

### Resources

- [video: The Video Embed element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/r89w-HojDmpVGYE-3roZBw "video: The Video Embed element - HTML: Hypertext Markup Language | MDN")
- [Media formats for HTML audio and video](https://intranet.alxswe.com/rltoken/TwY3y1Z9zGzEgDgSHAZUxg "Media formats for HTML audio and video")
- [Can I use… video](https://intranet.alxswe.com/rltoken/WRdHPbgJXk1-Iko5D3SgDA "Can I use... video")

---

## `audio` tag

The `audio` HTML Tag gives the capability to embed sound content in your HTML.

``` html
<!-- single audio file -->
<audio src="/music/audiofile.mp3" controls>
<!-- multiple audio files -->
<audio controls>
  <source src="audiofile.mp3" type="audio/mpeg">
  <source src="audiofile.ogg" type="audio/ogg">
</audio>
```

### Resources

- [audio: The Embed Audio element](https://intranet.alxswe.com/rltoken/0wY2U7vnxiEESfZkMKXKJw "audio: The Embed Audio element")
- [Can I use… audio](https://intranet.alxswe.com/rltoken/co5Ozg7IzHV8tQ9cq-utRg "Can I use... audio")

---

## `iframe` tag

An iframe embed an external browsing content in your current HTML page.

|Type|Self-closing|
|---|---|
|Block|No|

``` html
<iframe
  title="Inline Frame Example"
  width="300"
  height="200"
  src="https://www.google.com/">
  Fallback text for non-supported browsers
</iframe>
```

Accessibility tip: Always specify a title attribute on your iFrame.

Tip: Use iFrames with parcimony as they can add extra weight to your webpage.

### Resources

- [iframe: The Inline Frame element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/WAmGV637aqvPANlUz2aEiA "iframe: The Inline Frame element - HTML: Hypertext Markup Language | MDN")
- [3 Reasons You Should Never Use Iframes](https://intranet.alxswe.com/rltoken/hEf1_Be1SWNQezLw8_IAow "3 Reasons You Should Never Use Iframes")