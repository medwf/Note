## Difference Between var, let and const
| Property                | var      | let         | const       |
| ----------------------- | -------- | ----------- | ----------- |
| Scope                   | Function | Block       | Block       |
| Redeclare (change type) | Allowed  | Not allowed | Not allowed |
| Reassign (change value) | Allowed  | Allowed     | Not allowed |
| Hoisted                 | Yes      | No          | No          |
| Binds this              | Yes      | No          | No          |
## Scope and redeclare
``` node
{
	// Global scope var 
	// Block scope const and let
	let x = 2;
	var a = 10;


}
// x can NOT be used here.
// a can be used here.

// Redeclared.
let b = 10;
let b = "hi mohamed?" // let can not redeclared.

// but with var can do it.
var c = 11;
var c = "yes, we can do it :).";

// Redeclared with scope. let vs var.
var x = 10;  
// Here x is 10  
  
{  
var x = 2;  
// Here x is 2  
}  
  
// Here x is 2, problem with change value from outside-block to inside-block.
// let solve this problem and seperate redeclare from outside-block to inside-block.
let x = 10;  
// Here x is 10  
  
{  
let x = 2;  
// Here x is 2  
}  
  
// Here x is 10

```

## hoisting.
```javascript
carName = "Volvo";  
var carName;
// we can do it with var.

carName = "Saab";  
let carName = "Volvo";
// error in carName = "Saab";
				   ^
				   
```

## Reassigned `const`
- const can not be Reassigned.
```javascript
const PI = 3.141592653589793;  
PI = 3.14;      // This will give an error  
PI = PI + 10;   // This will also give an error
```
- When to use JavaScript const?
	- **Always declare a variable with `const` when you know that the value should not be changed.**
		- Use `const` when you declare:
			- A new Array
			- A new Object
			- A new Function
			- A new RegExp
- Constant Arrays?
```javascript
// You can create a constant array:
const cars = ["Saab", "Volvo", "BMW"];
console.log(cars)

// You can change an element:
cars[0] = "Toyota";
console.log(cars)

// You can add an element:
cars.push("Audi");
console.log(cars)

// But you can NOT reassign the array:
cars = ["Toyota", "Volvo", "Audi"];    // ERROR
```

- Constant Objects ? 
``` javascript
// You can create a const object:  
const car = {type:"Fiat", model:"500", color:"white"};  
  
// You can change a property:  
car.color = "red";  
  
// You can add a property:  
car.owner = "Johnson";

// but you NOT reassign the Object.
car = {type:"Volvo", model:"EX60", color:"red"};    // ERROR
```

- const RegExp ?
```javascript 
const myRegex = new RegExp(/^[a-z]+$/);  // Matches lowercase letters only
console.log(myRegex.test("hello"));   // true
// Attempting to reassign will result in a TypeError:
// myRegex = /somethingElse/;

```

`Wornning` : cant change type variable from const to let or var or just resigned.
```javascript
const x = 11;

// can't do att of this.
x = 12;
let x = 111;
var x = 222;
const x = 99;
```