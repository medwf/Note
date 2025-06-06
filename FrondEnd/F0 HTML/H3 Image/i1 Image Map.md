# HTML Image Maps
- With HTML image maps, you can create clickable areas on an image.
## Image Maps

The HTML `<map>` tag defines an image map. An image map is an image with clickable areas. The areas are defined with one or more `<area>` tags.

Try to click on the computer, phone, or the cup of coffee in the image below:

![Workplace](https://www.w3schools.com/html/workplace.jpg)

### Example

Here is the HTML source code for the image map above:

<img src="workplace.jpg" alt="Workplace" usemap="#workmap">  
  
<map name="workmap">  
  <area shape="rect" coords="34,44,270,350" alt="Computer" href="computer.htm">  
  <area shape="rect" coords="290,172,333,250" alt="Phone" href="phone.htm">  
  <area shape="circle" coords="337,300,44" alt="Coffee" href="coffee.htm">  
</map>

[Try it Yourself »](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_images_map2)

---

## How Does it Work?

The idea behind an image map is that you should be able to perform different actions depending on where in the image you click.

To create an image map you need an image, and some HTML code that describes the clickable areas.

---

---

## The Image

The image is inserted using the `<img>` tag. The only difference from other images is that you must add a `usemap` attribute:

<img src="workplace.jpg" alt="Workplace" usemap="#workmap">

The `usemap` value starts with a hash tag `#` followed by the name of the image map, and is used to create a relationship between the image and the image map.

**Tip:** You can use any image as an image map!

---

## Create Image Map

Then, add a `<map>` element.

The `<map>` element is used to create an image map, and is linked to the image by using the required `name` attribute:

``` html
<map name="workmap">
```

The `name` attribute must have the same value as the `<img>`'s `usemap` attribute .

---

## The Areas

Then, add the clickable areas.

A clickable area is defined using an `<area>` element.

### Shape

You must define the shape of the clickable area, and you can choose one of these values:

- `rect` - defines a rectangular region
- `circle` - defines a circular region
- `poly` - defines a polygonal region
- `default` - defines the entire region

You must also define some coordinates to be able to place the clickable area onto the image. 

---

### Shape="rect"

The coordinates for `shape="rect"` come in pairs, one for the x-axis and one for the y-axis.

So, the coordinates `34,44` is located 34 pixels from the left margin and 44 pixels from the top:

![Workplace](https://www.w3schools.com/html/workplace.jpg)

The coordinates `270,350` is located 270 pixels from the left margin and 350 pixels from the top:

![Workplace](https://www.w3schools.com/html/workplace.jpg)

Now we have enough data to create a clickable rectangular area:  

### Example

``` html
<area shape="rect" coords="34, 44, 270, 350" href="computer.htm">
```

[Try it Yourself »](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_images_map3)

This is the area that becomes clickable and will send the user to the page "computer.htm":

![Workplace](https://www.w3schools.com/html/workplace.jpg)

---

### Shape="circle"

To add a circle area, first locate the coordinates of the center of the circle:

`337,300`

![Workplace](https://www.w3schools.com/html/workplace.jpg)

Then specify the radius of the circle:

`44` pixels

![Workplace](https://www.w3schools.com/html/workplace.jpg)

Now you have enough data to create a clickable circular area:  

### Example

<area shape="circle" coords="337, 300, 44" href="coffee.htm">

[Try it Yourself »](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_images_map4)

This is the area that becomes clickable and will send the user to the page "coffee.htm":

![Workplace](https://www.w3schools.com/html/workplace.jpg)

---

### Shape="poly"

The `shape="poly"` contains several coordinate points, which creates a shape formed with straight lines (a polygon).

This can be used to create any shape.

Like maybe a croissant shape!

How can we make the croissant in the image below become a clickable link?

![French Food](https://www.w3schools.com/html/frenchfood.jpg)

We have to find the x and y coordinates for all edges of the croissant:

![French Food](https://www.w3schools.com/html/frenchfood4.jpg)

The coordinates come in pairs, one for the x-axis and one for the y-axis:

### Example

<area shape="poly" coords="140,121,181,116,204,160,204,222,191,270,140,329,85,355,58,352,37,322,40,259,103,161,128,147" href="croissant.htm">

[Try it Yourself »](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_images_map_croissant)

This is the area that becomes clickable and will send the user to the page "croissant.htm":

![French Food](https://www.w3schools.com/html/frenchfood3.jpg)

---

## Image Map and JavaScript

A clickable area can also trigger a JavaScript function.

Add a `click` event to the `<area>` element to execute a JavaScript function:

### Example

Here, we use the onclick attribute to execute a JavaScript function when the area is clicked:

``` html
<map name="workmap">  
  <area shape="circle" coords="337,300,44" href="coffee.htm" onclick="myFunction()">  
</map>
<script>  
function myFunction() {  
  alert("You clicked the coffee cup!");  
}  
</script>
```
<map name="workmap">  
  <area shape="circle" coords="337,300,44" href="coffee.htm" onclick="myFunction()">  
</map>  
  
---

## Chapter Summary

- Use the HTML `<map>` element to define an image map
- Use the HTML `<area>` element to define the clickable areas in the image map
- Use the HTML `usemap` attribute of the `<img>` element to point to an image map