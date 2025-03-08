# Basic PHP Syntax
- A PHP script can be placed anywhere in the document.
- A PHP script starts with `<?php` and ends with `?>`:
- **Note:** PHP statements end with a semicolon (`;`).
- The default file extension for PHP files is "`.php`".

```php
<?php
// PHP code goes here
?>
``` 

- A PHP file `normally contains HTML tags`, and some `PHP scripting code`.
- Below, we have an example of a simple PHP file, with a PHP script,
	that uses a built-in PHP function "`echo`" to output the text "Hello World!" on a web page:

``` php
!DOCTYPE html>
<html>
	<body>
		<h1>My first PHP page</h1>
		<?php
		echo "Hello World!";
		?>
	</body>
</html>
```

# PHP Case Sensitivity
- In PHP, keywords (e.g. `if`, `else`, `while`, `echo`, etc.), classes, functions, and user-defined functions are not case-sensitive.
- In the example below, all three echo statements below are equal and legal:

### Example
- `ECHO` is the same as `echo`:
```php
<!DOCTYPE html>
<html>
<body>

<?php
ECHO "Hello World!<br>";
echo "Hello World!<br>";
EcHo "Hello World!<br>";
?>

</body>
</html>
```

# but `variable` is case-sensitive.
