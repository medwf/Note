JavaScript Object Notation (JSON) is a standard text-based format for representing structured data based on JavaScript object syntax. It is commonly used for transmitting data in web applications (e.g.,

sending some data from the server to the client,

so it can be displayed on a web page,

or vice versa

).

You'll come across it quite often, so in this article, we give you all you need to work with JSON using JavaScript, including parsing JSON so you can access data within it, and creating JSON.

|   |   |
|---|---|
|Prerequisites:|A basic understanding of HTML and CSS, familiarity with JavaScript basics (see [First steps](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps) and [Building blocks](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks)) and OOJS basics (see [Introduction to objects](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics)).|
|Objective:|To understand how to work with data stored in JSON, and create your own JSON strings.|

[No, really, what is JSON?](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON#no_really_what_is_json)

[JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) is a text-based data format following JavaScript object syntax, which was popularized by [Douglas Crockford](https://en.wikipedia.org/wiki/Douglas_Crockford). Even though it closely resembles JavaScript object literal syntax, it can be used independently from JavaScript, and many programming environments feature the ability to read (parse) and generate JSON.

JSON exists as a string — useful when you want to transmit data across a network. It needs to be converted to a native JavaScript object when you want to access the data. This is not a big issue — JavaScript provides a global [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) object that has methods available for converting between the two.

Note: Converting a string to a native object is called deserialization, while converting a native object to a string so it can be transmitted across the network is called serialization.
```JSON
superHeroes =

{

  "squadName": "Super hero squad",

  "homeTown": "Metro City",

  "formed": 2016,

  "secretBase": "Super tower",

  "active": true,

  "members": [

    {

      "name": "Molecule Man",

      "age": 29,

      "secretIdentity": "Dan Jukes",

      "powers": ["Radiation resistance", "Turning tiny", "Radiation blast"]

    },

    {

      "name": "Madame Uppercut",

      "age": 39,

      "secretIdentity": "Jane Wilson",

      "powers": [

        "Million tonne punch",

        "Damage resistance",

        "Superhuman reflexes"

      ]

    },

    {

      "name": "Eternal Flame",

      "age": 1000000,

      "secretIdentity": "Unknown",

      "powers": [

        "Immortality",

        "Heat Immunity",

        "Inferno",

        "Teleportation",

        "Interdimensional travel"

      ]

    }

  ]

}
```
If we loaded this string into a JavaScript program and parsed it into a variable called superHeroes for example, we could then access the data inside it using the same dot/bracket notation we looked at in the [JavaScript object basics](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics) article. For example:

JSCopy to Clipboard

superHeroes.homeTown;

superHeroes["active"];

To access data further down the hierarchy, you have to chain the required property names and array indexes together. For example, to access the third superpower of the second hero listed in the members list, you'd do this:

superHeroes["members"][1]["powers"][2];

1. First, we have the variable name — superHeroes.
2. Inside that, we want to access the members property, so we use ["members"].
3. members contains an array populated by objects. We want to access the second object inside the array, so we use [1].
4. Inside this object, we want to access the powers property, so we use ["powers"].
5. Inside the powers property is an array containing the selected hero's superpowers. We want the third one, so we use [2].

[Active learning: Working through a JSON example](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON#active_learning_working_through_a_json_example)

So, let's work through an example to show how we could make use of some JSON formatted data on a website.

[Getting started](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON#getting_started)


# Manipulation JSON
Manipulating JSON data in JavaScript is a common task, as JSON (JavaScript Object Notation) is a lightweight data interchange format. JavaScript provides built-in methods and functions to work with JSON. Here are some common operations:

1. **Parsing JSON:**

   To convert a JSON string into a JavaScript object, you use the `JSON.parse()` method.

```JSON
var jsonString = '{"name": "John", "age": 30, "city": "New York"}';
var jsonObj = JSON.parse(jsonString);
console.log(jsonObj);

```
2. **Stringifying JavaScript Object to JSON:**

   To convert a JavaScript object into a JSON string, you use the `JSON.stringify()` method.

```JSON
var jsonObj = { name: "John", age: 30, city: "New York" };
var jsonString = JSON.stringify(jsonObj);
console.log(jsonString);
```

3. **Accessing and Modifying JSON Data:**

   Once you have the JSON data as a JavaScript object, you can access and modify its properties as you would with any other JavaScript object.

```JSON
var jsonObj = { name: "John", age: 30, city: "New York" };
// Accessing properties
console.log(jsonObj.name); // Output: John
// Modifying properties
jsonObj.age = 31;
console.log(jsonObj);
// Output: { name: "John", age: 31, city: "New York" }
```

4. **Adding and Deleting Properties:**

   You can add or delete properties from a JavaScript object, and then convert it back to a JSON string if needed.

```JSON
var jsonObj = { name: "John", age: 30, city: "New York" };
// Adding a new property
jsonObj.gender = "Male";
// Deleting a property
delete jsonObj.age;
console.log(jsonObj);
// Output: { name: "John", city: "New York", gender: "Male" }
```

Remember to handle errors appropriately, especially when parsing JSON, as malformed JSON can cause errors. You can use try-catch blocks to handle exceptions.

```JSON
var jsonString = '{"name": "John", "age": 30, "city": "New York"}';
try {
  var jsonObj = JSON.parse(jsonString);
  console.log(jsonObj);
} catch (error) {
  console.error("Error parsing JSON:", error);
}
```

These are the basic operations for manipulating JSON data in JavaScript. Depending on your use case, you may need more advanced techniques, such as iterating over arrays within the JSON or handling nested structures.
