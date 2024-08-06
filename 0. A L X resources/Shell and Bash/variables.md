## type of variable 
shell variables are in uppercase characters by convention, Bash keeps a list of two type of variables: 

#### add variable : 
export PATH=${PATH}:/action 


##### Global variables : 
global variable or environment variables are available in all shells the `env` or `printenv` command can be used to display environment  variable 
- print global variable : printenv

#### local variables :
Local variables are only available in  the current shell : Using the set built-in command without any option will display a list of all variables 
- print local variable : declare

#### variables by content : 
Apart from dividing variables in local and global var, we can also divide them in categories according to sort of content the variables contains. 
- String variables 
- Integer variables 
- Constant variables 
- Array variables 
Make variables FG="hi"

#### Exporting variables 
change variables using export 
- export var="text"
