# Special Characters
## `*` ALL
- `*`: zero or all characters
```Shell 
ls * # list all file
ls a* # list all file taht started with a.
```

## `?` Any One Character 
- `?` One characters, Any characters.
```Shell
ls ? # list all file or dir with one character.
ls ?? # all file or directory has 2 char. 
```
### Command Substitution.
```Shell
echo $(ls) # list content directory.
echo $(with ls) # /bin/ls.
```

## `\` backslash
- Insert special characters.
``` Shell
echo ""hi mohamed" # error

# to fix that.
echo "\"hi mohamed" # output: "hi mohamed
```
## `{}` Loop into value {from..To..step}.
- Interrupter expression.   `{a..z}` => `a b c d e f g h i g k l m n o p q r s t u v z x y z`
1. `{a,b,c}` => a b c // a & b & c.
2. `{a..c}` => a b c. // default step 1
3. `{a..c..2}` : a c //  step 2 
## Example
```SHell
echo front-{A,B,C}-back # {A,B,C} == A B C
       # front-A-back  front-B-back front-C-back

echo Number_{1..5} # {1..5} == 1 2 3 4 5 , step 1 by defult. 
       # Number1 Number2 ... Number5

echo {Z..A} # from Z to A step 1 rev
       # Z Y X W ... C B A

echo a{A{1,2},B{3,4}}b
       aA1b aA2b aB3b aB4b

mkdir {2017..2019}-{01..12}
      # 2017-01 2017-07 2018-01 2018-07 2019-01 2019-07 2017-02 2017-08 2018-02 2018-08
      # 2019-02 2019-08 2017-03 2017-09 2018-03 2018-09 2019-03 2019-09 2017-04 2017-10
      # 2018-04 2018-10 2019-04 2019-10 2017-05 2017-11 2018-05 2018-11 2019-05 2019-11
      # 2017-06 2017-12 2018-06 2018-12 2019-06 2019-12

```
## `[]` Square Bracket.
- replacer expression: `[a-z]`
	- if found `a b c d e f g h i g k l m n o p q r s t u v z x y z`
	- else `[a-z]`.
- If found.
	1. `[abcde]`: a b c d e.
	2. `[a-e]`: a b c d e.
	3. `[^abc]` : soft a b c 

# Quoting Characters
## `'` Single Quote
## `"` Double Quote
##  \`\`  
- \``CMD`\` : execute command in \`\`
```Shell

```