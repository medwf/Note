# Special characters
- " " : _Whitespace_ ; special character save `$\`
- $ : _Expansion_ : parameter expansion (e.g. $var or ${var}) 
        command substitution (e.g. $(command))
         arithmetic expansion (e.g. $((expression)))
- '' : _Single quotes_ : 
        protect the text inside them so that it has a _literal_ meaning.
- "" : _Double quotes_ 
         protect the text inside them from being split into multiple words or arguments
- \\ : _Escape_ ((backslash))
        prevents the next character from being interpreted as a special character
- \# :  _Comment_ 
        the # character begins a commentary that extends to the end of the line
- = : _Assignment_
        assign a value to a variable (e.g. logdir=/var/log/myprog)
- \[\[ ]] :   _Test_ 
        an evaluation of a conditional expression to determine whether it is "true" or "false"
- ! : _Negate_
        used to negate or reverse a test or exit status. For example: ! grep text file; exit $?.
- >, >>, < : _Redirection_
         redirect a command's _output_ or _input_ to a file. Redirections will be covered later
- | : _Pipe_ 
        send the output from one command to the input of another command.
        echo "Hello beautiful." | grep -o beautiful
- ; : _Command separator_
        used to separate multiple commands that are on the same line  
- { } : _Inline group_ 
        commands inside the curly braces are treated as if they were one command
- ( ) : _Subshell group_ 
        similar to the above but where commands within are executed in a [subshell](http://mywiki.wooledge.org/SubShell) (a new process)
- (( )) : _Arithmetic expression_ 
         with an [arithmetic expression](http://mywiki.wooledge.org/ArithmeticExpression), characters such as +, -, *, and / are mathematical operators used for calculations. They can be used for variable assignments like (( a = 1 + 4 )) as well as tests like if (( a < b )). More on this later.
- $(( )) : _Arithmetic expansion_ 
        Comparable to the above, but the expression is replaced with the result of its arithmetic evaluation. Example: echo "The average is $(( (a+b)/2 ))".
- \*, ? : _[Globs](http://mywiki.wooledge.org/glob)_
         "wildcard" characters which match parts of filenames (e.g. ls *.txt).
- ~ : _Home directory_ 
        he tilde is a representation of a home directory. When alone or followed by a /, it means the current user's home directory; otherwise, a username must be specified (e.g. ls ~/Documents; cp ~john/.bashrc .).
- & :  _Background_ 
        when used at the end of a command, run the command in the background (do not wait for it to complete)
- ^ :The caret symbol 
         is a regular expression anchor that matches the beginning of a line.