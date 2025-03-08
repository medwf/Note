![[Pasted image 20241212130539.png]]

In CSS, the term "box model" is used when talking about design and layout.

margin properties are used to create space around elements, outside of any defined borders.

- margin:  (top, right, bottom, left). // one value;
- margin:  (top, right-left, bottom). // tree value;
- margin:  (top-bottom, , left-right). // one value;

- Specific with side have margin:

- margin-top: ;
- margin-right: ;
- margin-bottom: ;
- margin-left: ;

padding properties are used to create space around elements, inside of any defined borders.

- padding :  (top, right, bottom, left). // one value;
- Padding :  (top, right-left, bottom). // tree value;
- padding :  (top-bottom, , left-right). // one value;

- Specific with side have padding:

- padding-top
- padding-right
- padding-bottom
- padding-left

border A border that goes around the padding and content

Style border in one line:

- border: style color width; // can change order.
- Can get side by write border-(top | right | bottom | bottom).

Style border specific parameter:

- border-style: for styling solid dotted . . . ;

  border-top-style: dotted;

  border-right-style: solid;

  border-bottom-style: dotted;

  border-left-style: solid;

- border-color: for color black white . . . or // rgb(red, green, blue).
- border-width: for size line ?px;

Style border radios:

border-radios : one value; effect (1-2-3-4);

border-radios : two value; effect (1-3, 2-4);

border-radios : tree value; effect (1, 2-3, 4);

border-radios : four value; effect (1, 2, 3, 4);