# With PHP, there are two basic ways to get output: `echo` and `print`.

|              | echo  | print                       |
| ------------ | ----- | --------------------------- |
| return value | No    | Yes 1 can use in expression |
| parameter    | multi | just `one`.                 |

## echo.
```php
echo "Hello"; //same as:
echo("Hello");

// The following example shows how to output text with the `echo` command (notice that the text can contain HTML markup):
echo "<h2>PHP is Fun!</h2>";
echo "Hello world!<br>";
echo "I'm about to learn PHP!<br>";
echo "This ", "string ", "was ", "made ", "with multiple parameters.";

$txt1 = "Learn PHP";
$txt2 = "W3Schools.com";

echo "<h2>$txt1</h2>";
echo "<p>Study PHP at $txt2</p>";

/**
* Strings are surrounded by quotes, but there is a difference between single and double quotes in PHP.
* When using double quotes, variables can be inserted to the string as in the example above.
* When using single quotes, variables have to be inserted using the `.` operator, like this:
*/

$txt1 = "Learn PHP";
$txt2 = "W3Schools.com";

echo '<h2>' . $txt1 . '</h2>';
echo '<p>Study PHP at ' . $txt2 . '</p>';

```

## print
```PHP

print "Hello";
//same as:
print("Hello");


// The following example shows how to output text with the `print` command (notice that the text can contain HTML markup):
print "<h2>PHP is Fun!</h2>";
print "Hello world!<br>";
print "I'm about to learn PHP!";

## Display Variables

// The following example shows how to output text and variables with the `print` statement:
$txt1 = "Learn PHP";
$txt2 = "W3Schools.com";

print "<h2>$txt1</h2>";
print "<p>Study PHP at $txt2</p>";


[Try it Yourself »](https://www.w3schools.com/php/phptryit.asp?filename=tryphp_print2)

## Using Single Quotes

// Strings are surrounded by quotes, but there is a difference between single and double quotes in PHP.
// When using double quotes, variables can be inserted to the string as in the example above.
// When using single quotes, variables have to be inserted using the `.` operator, like this:

$txt1 = "Learn PHP";
$txt2 = "W3Schools.com";

print '<h2>' . $txt1 . '</h2>';
print '<p>Study PHP at ' . $txt2 . '</p>';
```
```