Virtue code can be categorized as synchronous or Asynchronous.
# Synchronous :
- Run task one by one: Each task can run before last task begging.
- for example All http request ran run one by one.
	- 1 request // when you finish this move to 2 request.
	- 2 request // when you finish this move to 2 request.
	- 3 request // when you finish this move to the end request ... 
# Asynchronous :
- every task can begging process in The sometimes.
- for example All http request run as same times that we save time.
	- 1 request // start at same times
	- 2 request // start at same times
	- 3 request // start at same times

## Subroutines and Coroutines
### Subroutines. `sub is sudset of large program`
- sub routine is a block of code that can be call as needed, when sub routines is called control of program is transferred to that sub routines, when it's done, control is return back to the main program and continues from where they left off.
- sub routines can't stop they run until done.
### Coroutines. `Co for togeder` 
- co routines is a special kind of function that can have its executions paused and resumed this is possible because they maintain state between pauses.
- Application:
	- I/O Operations.
	- Database Queries.
	- Http Requests.