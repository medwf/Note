# Styling.
- **Inline** - by using the `style` attribute inside HTML elements
``` html
<p style="css styles" >this is paragraph</p>

%% Example paragraph with color red %%
<p style="color: red" >this is paragraph</p>

```

- **Internal** - by using a `<style>` element in the `<head>` section
``` html
<head>
  <title>Document</title>
  <style>
    /* style intern */
  </style>
</head>
```

- **External** - by using a `<link>` element to link to an external CSS file
``` html
<head>
  <title>Document</title>
  <link rel="stylesheet" type="text/css" href="style.css">
</head>
```

