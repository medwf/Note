```TS
// Query param like ?name=mohamed
// Param like /<name>. 
@Get("/:name")
function fun(
	@Query(define key optinal) query,
	@Param(define key optinal) params,
	@Body("name") name: string,
	// request
	@Req() req,

	 // responce
	 @Res() res // if u use is u should send responce by res.send().
	
)

// 
```