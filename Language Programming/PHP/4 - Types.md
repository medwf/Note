# Types.
- PHP supports the following data types:
#### String.
- can be `""`  and  `''` double quote can `process special characters`, single does `not`!.
```php
# methods used in string.
strlen(string) // return number of caharacters.
str_word_count(string) // return number of word.
strpos("Hello world!", "world") // search 'world' in 'Hello world!'

# modifier string.
strtoupper(string) // change string to UPPERCASE.
strtolower(string) // change string to lowercase.
str_replace(s1, s2, s) // change txt s1 to s2 in s.
strrev(string) // reverse string.
trim(string) // remove any whitespace from beginning or end. 
explode(sep, str) // split str with sep return array.

# concatenation string.
"Hello " . "world!" // cancate with . no space added;
"$var1 $var2" // power of Double Qouate.

# slice string.
substr(str, indexStart, numberCharSlice) // str always start with 0. like : str[indexStart, indexStart + indexCharSlice]
substr(str, -indexStart, numberCharSlice) // str always end with -1. like : str[-indexStart, -indexStart + indexCharSlice]
substr(str, indexStart, -numberCharSlice) // str always start with 0 and end with -1 . like : str[indexStart, -indexCharSlice]
substr(str, indexStart) // return str start with indexStart to end. like : str[indexStart,]


```
#### Number 
-  Integer
-  Float (floating point numbers - also called double)
-  Number Strings
- Boolean
-  Array.
- Object
- NULL
- Resource

## Get the Type
- To get the data type of a variable, use the `var_dump()` function.
### Example
The `var_dump()` function returns the data type and the value:
```php
$x = 5;
var_dump($x);

// Example
// See what `var_dump()` returns for other data types:
var_dump(5);
var_dump("John");
var_dump(3.14);
var_dump(true);
var_dump([2, 3, 56]);
var_dump(NULL);
```
