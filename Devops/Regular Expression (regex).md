# Regular expression
- A regular expression (regex or regexp for short) is a special text string for describing a search pattern.
- You can think of regular expressions as wildcards on steroids.
- You are probably familiar with wildcard notations such as:
	- `*.txt` to find all text files in a file manager.
	- The regex equivalent is `^.*\.txt$`.

But you can do much more with regular expressions. In a text editor like [EditPad Pro](https://www.regular-expressions.info/editpadpro.html) or a specialized text processing tool like [PowerGREP](https://www.regular-expressions.info/powergrep.html), you could use the regular expression `\b[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}\b` to search for an email address. Any email address, to be exact. A very similar regular expression (replace the first \b with ^ and the last one with $) can be used by a programmer to check whether the user entered a [properly formatted email address](https://www.regular-expressions.info/email.html). In just one line of code, whether that code is written in [Perl](https://www.regular-expressions.info/perl.html), [PHP](https://www.regular-expressions.info/php.html), [Java](https://www.regular-expressions.info/java.html), [a .NET language](https://www.regular-expressions.info/dotnet.html), or a multitude of other languages.


# Regular Expressions (Regex)
1. Metacharacters: `.`,`*`, `+`, `?`, `{`, `}`, `[`, `]`, `|`, `(`, `)`, `^`, `$`:
	1. `.` : match any single characters.
2. Character classes: `[abc]` , `[^abc]`, `[a-zA-Z]`, `[0-9]`
	1. `[]` : match any single character.
	2. `[^]` : match any single characters excepts.
	3. `[a-z]` : any single characters in range a to z
3. Groups and captures: `()`:
	1. `(\d+)` : match number in grpuped.
	2. `(a(bc))`:  Capture Sub-group match `a` or `bc` or `both`.
4. Quantifiers: `*`, `+`, `?`, `{n,m}`:
	1. `a*` : Zero or more of a. 
	2. `a+` : one of more of a.
	3. `a?` : Zero or One of a.
	4. `a{n,m}` : exactly Between n and m of a.
		1. Usage `{start, end}` or `{start, }` or `{, end}` .  
5. Anchors: `^`, `$` :
	1. `^` : start of line.
	2. `$` : end of line.
6. Alternation: `|`
7. Escape sequences: `\` (e.g., `\.` matches literal dot)
8. `\d` digit - `\D` non digit:
9. `\s` whitespace - `\S` non-whitespace.
10. `\w`  word character (letter|number|underscore)`\W` non word character.
 
### options:
 i   : case insensitive
m  : make dot match newlines
x   : ignore white-space in regex
o   :  perform #{...} substitutions only once