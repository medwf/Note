# regular expression
A regular expression (regex or regexp for short) is a special text string for describing a search pattern. You can think of regular expressions as wildcards on steroids. You are probably familiar with wildcard notations such as *.txt to find all text files in a file manager. The regex equivalent is ^.*\.txt$

But you can do much more with regular expressions. In a text editor like [EditPad Pro](https://www.regular-expressions.info/editpadpro.html) or a specialized text processing tool like [PowerGREP](https://www.regular-expressions.info/powergrep.html), you could use the regular expression \b[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}\b to search for an email address. Any email address, to be exact. A very similar regular expression (replace the first \b with ^ and the last one with $) can be used by a programmer to check whether the user entered a [properly formatted email address](https://www.regular-expressions.info/email.html). In just one line of code, whether that code is written in [Perl](https://www.regular-expressions.info/perl.html), [PHP](https://www.regular-expressions.info/php.html), [Java](https://www.regular-expressions.info/java.html), [a .NET language](https://www.regular-expressions.info/dotnet.html), or a multitude of other languages.

Regular Expressions Quick Start

If you just want to get your feet wet with regular expressions, take a look at the [one-page regular expressions quick start](https://www.regular-expressions.info/quickstart.html). While you can’t learn to efficiently use regular expressions from this brief overview, it’s enough to be able to throw together a bunch of simple regular expressions. Each section in the quick start links directly to detailed information in the tutorial.


 ### Select character :

|   |   |
|---|---|
|[abc]|A single character of: a, b, or c|
|[^abc]|Any single character except: a, b, or c|
|[a-z]|Any single character in the range a-z|
|[a-zA-Z]|Any single character in the range a-z or A-Z<br><br>Start and end line string:|
|^|Start of line|
|$|End of line|
|\A|Start of string or file|
|\z|End of string or file|
|||
||Characters:|

|   |   |
|---|---|
|.|Any single character<br><br>Whitespace|
|\s|Any whitespace character|
|\S|Any non-whitespace character<br><br>Select Digit :|
|\d|Any digit|
|\D|Any non-digit<br><br>     Word:|
|\w|Any word character (letter, number, underscore)|
|\W|Any non-word character|
|\b|Any word boundary<br><br>Select character or more:|
|(...)|Capture everything enclosed|
|(a \| b)|a or b|
|a?|Zero or one of a|
|a*|Zero or more of a|
|a+|One or more of a|
|a{3}|Exactly 3 of a|
|a{3,}|3 or more of a|
|a{3,6}|Between 3 and 6 of a|

### options:
 i   : case insensitive
m  : make dot match newlines
x   : ignore whitespace in regex
o   :  perform #{...} substitutions only once