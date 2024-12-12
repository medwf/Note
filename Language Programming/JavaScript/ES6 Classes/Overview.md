`Classes` are a `template for creating objects`. They encapsulate data with code to work on that data. Classes in JS are built on [prototypes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) but also have some syntax and semantics that are unique to classes.

```JS
const bigDay = new Date(2019, 6, 19);
console.log(bigDay.toLocaleDateString());
if (bigDay.getTime() < Date.now()) {
  console.log("Once upon a time...");
}
```

- On the first line, we created an instance of the class [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date), and called it `bigDay`. 
- On the second line, we called a [method](https://developer.mozilla.org/en-US/docs/Glossary/Method) [`toLocaleDateString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toLocaleDateString) on the `bigDay` instance, which returns a string. 
- Then, we compared two numbers: one returned from the [`getTime()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime) method, the other directly called from the `Date` class _itself_, as [`Date.now()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/now).

`Date` is a built-in class of JavaScript. From this example, we can get some basic ideas of what classes do:

- Classes create objects through the [`new`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) operator.
- Each object has some properties (data or method) added by the class.
- The class stores some properties (data or method) itself, which are usually used to interact with instances.

These correspond to the three key features of classes:

- Constructor;
- Instance methods and instance fields;
- Static methods and static fields.
# Declaring a class

- Classes are usually created with class declarations.
```JS
// constructor function old javaScript.
function MyClass() {
	// Constructor body.
}

// New syntax constructor function using class declaration.
class MyClass {
  // class body...
  constructor() {
	// Constructor body
  }
}
```

- Within a class body, there are a range of features available.
```JS
class MyClass {
  // Constructor
  constructor() {
	// Constructor body
  }

  // Instance field
  myField = "foo";

  // Instance method
  myMethod() {
    // myMethod body
  }

  // Static field
  static myStaticField = "bar";

  // Static method
  static myStaticMethod() {
    // myStaticMethod body
  }

  // Static block
  static {
    // Static initialization code
  }

  // Fields, methods, static fields, and static methods all have
  // "private" forms
  #myPrivateField = "bar";
}
```

## define getter and setter.
- Example:
```JS
class HolbertonCourse {

  constructor(name, length, students) {
    this.name = name;
    this.length = length;
    this.students = students;
  }

  get name() {
    return this._name;
  }

  get length() {
    return this._length;
  }
 
  get students() {
    return this._students;
  }

  set name(value) {
    if (typeof value !== 'string') { throw new TypeError('Name must be a string'); }
    this._name = value;
  }

  set length(value) {
    if (typeof value !== 'number') { throw new TypeError('length must be a number'); }
    this._length = value;
  }

  set students(value) {
    if (!(value instanceof Array) || !(value.every((st) => typeof st === 'string'))) {
	    throw new TypeError('students must be an array of string');
    }
    this._students = value;
  }
}
```