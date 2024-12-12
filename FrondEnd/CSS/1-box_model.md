In CSS, the term "box model" is used when talking about design and layout.
![[box-model-html-css.jpg]]

**Explanation of the different parts:**

- **Content** - The content of the box, where text and images appear
- **Padding** - Clears an area around the content. The padding is transparent
- **Border** - A border that goes around the padding and content
- **Margin** - Clears an area outside the border. The margin is transparent

# margin
## Short one:
```CSS
div {

	/* take one value*/
	margin: top-bottom-right-left;

	/* take two value*/
	margin: top-bottom right-left;

	/* take four value */
	margin: top right bottom left;	
}
```

## specific side:
```css
div {
	margin-top: value;
	margin-left: value;
	margin-bottom: value;
	margin-right: value;
}
```

## margin auto: 
- You can set the margin property to `auto` to horizontally center the element within its container.
```css
div {
	width: 300px;
	margin: auto;
	border: 1px solid red;
 }
```

4. inherit value
	- his example lets the left margin of the `<p class="ex1">` element be inherited from the parent element (`<div>`):
```css
/* div is parent of p*/
div {  border: 1px solid red;  margin-left: 100px;} 
p.ex1 {  margin-left: inherit;}
```


# border
- The CSS border properties allow you to specify the `style`, `width`, and `color` of an element's border.
## border-style
- The `border-style` property specifies what kind of border to display.

- The following values are allowed:
	- `dotted` - Defines a dotted border
	-  `dashed` - Defines a dashed border
	- `solid` - Defines a solid border
	- `double` - Defines a double border
	- `groove` - Defines a 3D grooved border. The effect depends on the border-color value
	- `ridge` - Defines a 3D ridged border. The effect depends on the border-color value
	- `inset` - Defines a 3D inset border. The effect depends on the border-color value
	- `outset` - Defines a 3D outset border. The effect depends on the border-color value
	- `none` - Defines no border
	- `hidden` - Defines a hidden border

- Example:
``` css
p.dotted {border-style: dotted;}  
p.dashed {border-style: dashed;}  
p.solid {border-style: solid;}  
p.double {border-style: double;}  
p.groove {border-style: groove;}  
p.ridge {border-style: ridge;}  
p.inset {border-style: inset;}  
p.outset {border-style: outset;}  
p.none {border-style: none;}  
p.hidden {border-style: hidden;}  
p.mix {border-style: dotted dashed solid double;}
```
- Result:
![[Screenshot 2024-08-06 193725.png]]

## shorthand border:
- The `border` property is a shorthand property for the following individual border properties:
	- `border-width`
	- `border-style` (required)
	- `border-color`
- border: width style color; 
``` css
p {  border-left: 6px solid red;}
```
- there is also: 
```css
border-top
border-right
border-left
border-bottom
```

## border-radius.
```css
div {
	border-radius: value; /* used to add rounded to an element*/
}
```
# padding
- same as margin same syntax same objective.

# Content
