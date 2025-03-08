# Creating (Declaring) PHP Variables
- In PHP, a variable starts with the `$` sign, followed by the name of the variable:

## Example
```php
$x = 5;
$y = "John";
```

- In the example above, the variable `$x` will hold the value `5`, and the variable `$y` will hold the value `"John"`.
- **Note:** When you assign a text value to a variable, put quotes around the value.
- **Note:** Unlike other programming languages, PHP has no command for declaring a variable. It is created the moment you first assign a value to it.
- Think of variables as containers for storing data.

# PHP Variables

A variable can have a short name (like `$x` and `$y`) or a more descriptive name (`$age`, `$carname`, `$total_volume`).

Rules for PHP variables:

- A variable starts with the `$` sign, followed by the name of the variable
- A variable name must start with a letter or the underscore character
- A variable name `cannot start with a number`
- A variable name can only contain `alpha-numeric` characters and `underscores` (A-z, 0-9, and _ )
- Variable names are case-sensitive (`$age` and `$AGE` are two different variables)

- Remember that PHP variable names are case-sensitive!

### Example

```php
$txt = "W3Schools.com";
echo "I love " . $txt . "!";
// output I love W3Schools.com!
```


## Assign Multiple Values
You can assign the same value to multiple variables in one line:
- All three variables get the value "Fruit":
```php
$x = $y = $z = "Fruit";
```

# PHP constants
**`const` vs. `define()`**

- `const` cannot be created inside another block scope, like inside a function or inside an `if` statement.
- `define` can be created inside another block scope.
## Create constants using define()
```php
define(name_variable, value); // name_variable case-sensitive
echo name_variable;
```

## Create constants using const
```php
const name_variable = value;
echo name_variable;
```

## Magic constants
- PHP has nine predefined constants that change value depending on where they are used, and therefor they are called "magic constants".

- `__CLASS__`: if used inside a class, the class name is returned.
- `__DIR__` : The directory of the file.
- `__FILE__` : The file name including the full path.
- `__FUNCTION__` : If inside a function, the function name is returned.
- `__LINE__` : The current line number.
- `__METHOD__` : if used inside a function that belongs to a class, both class and function name is returned.
- `__NAMESPACE__` : If used inside a namespace, the name of the namespace is returned.
- `__TRAIT__` : if used inside a trait, the trait name is returned.
- `ClassName::class ` : Returns the name of the specified class and the name of the namespace, if any
###### The magic constants are case-insensitive, meaning `__LINE__` returns the same as `__line__`.
