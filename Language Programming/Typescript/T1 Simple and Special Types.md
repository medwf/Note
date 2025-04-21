# Types
- There are three main primitives in JavaScript and TypeScript.
	- `boolean` - true or false values
	- `number` - whole numbers and floating point values
	- `string` - text values like "TypeScript Rocks"

- There are also 2 less common primitives used in later versions of Javascript and TypeScript.
	- `bigint` - whole numbers and floating point values, but allows larger negative and positive numbers than the `number` type.
	- `symbol` are used to create a globally unique identifier.

# Type Assignment

When creating a variable, there are two main ways TypeScript assigns a type:

- Explicit
- Implicit

In both examples below `firstName` is of type `string`
## Explicit Type

- **Explicit** - writing out the type:
``` TypeScript
let firstName: string = "Dylan";
```
- **Explicit** type assignment are easier to read and more intentional.

---

## Implicit Type

**Implicit** - TypeScript will "guess" the type, based on the assigned value:
``` typescript
let firstName = "Dylan";
```
- Implicit assignment forces TypeScript to **infer** the value.
- **Implicit** type assignment are shorter, faster to type, and often used when developing and testing.

# Special types
## Type: any
- `any` is a type that disables type checking and effectively allows all types to be used.
- The example below does not use `any` and will throw an error:
``` typescript
let u = true;  
u = "string"; // Error: Type 'string' is not assignable to type 'boolean'.  
Math.round(u); // Error: Argument of type 'boolean' is not assignable to parameter of type 'number'.

// to solve that use any types
let v: any = true;  
v = "string"; // no error as it can be "any" type  
Math.round(v); // no error as it can be "any" type

```

- `any` can be a useful way to get past errors since it disables type checking, but TypeScript will not be able provide type safety, and tools which rely on type data, such as auto completion, will not work. Remember, it should be avoided at "any" cost...
## Type: unknown

`unknown` is a similar, but safer alternative to `any`.

TypeScript will prevent `unknown` types from being used, as shown in the below example:

```typescript
let w: unknown = 1;  
w = "string"; // no error  
w = {  
  runANonExistentMethod: () => {  
    console.log("I think therefore I am");  
  }  
} as { runANonExistentMethod: () => void}  
// How can we avoid the error for the code commented out below when we don't know the type?  
// w.runANonExistentMethod(); // Error: Object is of type 'unknown'.  
if(typeof w === 'object' && w !== null) {  
  (w as { runANonExistentMethod: Function }).runANonExistentMethod();  
}  
// Although we have to cast multiple times we can do a check in the if to secure our type and have a safer casting
```

- Compare the example above to the previous example, with `any`.
- `unknown` is best used when you don't know the type of data being typed. To add a type later, you'll need to cast it.
- Casting is when we use the "as" keyword to say property or variable is of the casted type.