An HTML form is used to collect user input. The user input is most often sent to a server for processing.
## The `<form>` Element
- The HTML `<form>` element is used to create an HTML form for user input:
``` html
<form>  
.  
_form elements_  
.  
</form>
```
### Attributes:
- `action`: attribute defines the action to be performed when the form is submitted.
- `target`: like link. `<a></a>`.
- `method` attribute specifies `The HTTP method` to be used when submitting the form data.
	**Notes on GET:**
	- Appends the form data to the URL, in name/value pairs
	- NEVER use GET to send sensitive data! (the submitted form data is visible in the URL!)
	- The length of a URL is limited (2048 characters)
	- Useful for form submissions where a user wants to bookmark the result
	- GET is good for non-secure data, like query strings in Google
	**Notes on POST:**
	- Appends the form data inside the body of the HTTP request (the submitted form data is not shown in the URL)
	- POST has no size limitations, and can be used to send large amounts of data.
	- Form submissions with POST cannot be bookmarked
    
- `autocomplete` attribute specifies whether a form should have autocomplete on or off.
	When autocomplete is on, `the browser automatically complete values` based on values that the user has `entered before`.
	
- The `novalidate` attribute is a `boolean attribute`.
	When present, it specifies that the `form-data` (input) should not be validated when submitted.
## The `<label>` Element
- Notice the use of the `<label>` element in the example above.
- The `<label>` tag defines a label for many form elements.
- The `<label>` element is useful for screen-reader users, because the screen-reader will read out loud the label when the user focuses on the input element.
- The `<label>` element also helps users who have difficulty clicking on very small regions (such as radio buttons or checkboxes) - because when the user clicks the text within the `<label>` element, it toggles the radio button/checkbox.
- The `for` attribute of the `<label>` tag should be equal to the `id` attribute of the `<input>` element to bind them together.

## The `<input>` Element
- The HTML `<input>` element is the most used form element.
- An `<input>` element can be displayed in many ways, depending on the `type` attribute.
	- `text` : Displays a single-line text input field.  <input type="text" value="text">
	- `radio` : Displays a radio button (for selecting one of many choices)  <input type="radio" value="text">
	- `checkbox`: Displays a checkbox (for selecting zero or more of many choices) <input type="checkbox" value="text">
	- `submit`: Displays a submit button (for submitting the form) <input type="submit" value="text">
	- `button`: Displays a clickable button. <input type="button" value="text">
	- `color` : <input type="color">
	- `date` : <input type="date">`
	- `datetime` : <input type="datetime-local">
	- `email` : <input type="email">`
	- `file` : <input type="file">
	- `hidden` : <input type="hidden">
	- `image` : <input type="image">
	- `month` : <input type="month">
	- `number` : <input type="number">
	- `password` : <input type="password">
	- `range` : <input type="range">
	- `reset` : <input type="reset">
	- `search` : <input type="search">
	- `tel` : <input type="tel">
	- `time` : <input type="time">
	- `url` : <input type="url">
	- `week` : <input type="week">


##  `<select>` and `option` Element
- element defines a drop-down list
``` html
<label for="cars">Choose a car:</label>  
<select id="cars" name="cars">  
  <option value="volvo">Volvo</option>  
  <option value="saab">Saab</option>  
  <option value="fiat">Fiat</option>  
  <option value="audi">Audi</option>  
</select>
```
![[Pasted image 20241225132443.png]]
- select: `multiple` : to select multi options
- option: `selected` : to set default selector.
 
##  `<textarea>` Element
- The `<textarea>` element defines a multi-line input field (a text area):
``` html
<form action="/action_page.php">
<!-- row = 10px, column = 30px -->
  <textarea name="message" rows="10" cols="30">The cat was playing in the garden.</textarea>
  <br><br>
  <input type="submit">
</form>
```
![[Pasted image 20241225132724.png]]

##  `<button>`
- simple button to send form.
##  `<fieldset>` and `<legend>`
- The `<fieldset>` element is used to group related data in a form.
- The `<legend>` element defines a caption for the `<fieldset>` element.
``` html
<fieldset>  
    <legend>Personalia:</legend>  
    <label for="fname">First name:</label><br>  
    <input type="text" id="fname" name="fname" value="John"><br>  
    <label for="lname">Last name:</label><br>  
    <input type="text" id="lname" name="lname" value="Doe"><br><br>  
    <input type="submit" value="Submit">  
</fieldset>
```
![[Pasted image 20241225144451.png]]
##  `<datalist>`
- The `<datalist>` element specifies a list of pre-defined options for an `<input>` element.
``` html
<form action="/action_page.php">
  <input list="browsers" name="browser">
  <datalist id="browsers">
    <option value="Edge">
    <option value="Firefox">
    <option value="Chrome">
    <option value="Opera">
    <option value="Safari">
  </datalist>
  <input type="submit">
</form>
```
![[Pasted image 20241225144641.png]]

##  `<output>`
- The `<output>` element represents the result of a calculation (like one performed by a script).
``` html
<form action="/action_page.php"  
  oninput="x.value=parseInt(a.value)+parseInt(b.value)">  
  0  
  <input type="range"  id="a" name="a" value="50">  
  100 +  
  <input type="number" id="b" name="b" value="50">  
  =  
  <output name="x" for="a b"></output>  
  <br><br>  
  <input type="submit">  
</form>
```
![[Pasted image 20241225144942.png]]

##  `<optgroup>