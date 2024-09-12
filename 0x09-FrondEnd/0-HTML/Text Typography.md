## Text Typography
A long list of HTML tags are used to give semantic meaning to specific text. Each tag is essential to help users and browsers understand the specificity of a certain portion of text. It’s crucial to understand which can be used in which situation.

- `<em>` to indicate stress emphasis.
- `<i>` to indicate text set off from the normal prose (foreign word, technical term…).
- `<strong>` to indicate stronger importance.
- `<b>` to draw attention to specific content (keywords in a summary, product names in a review…).
- `<small>` to represent side-comments or small text (copyright, legal text…).
- `<del>` to represent a text that has been deleted.
- `<ins>` to represent a text that has been inserted.
- `<s>` to render text with a strikethough or a line through it.
- `<wbr>` to specify where the text could have a line-break.
- `<mark>` to indicate relevance, representing text marked or highlighted for reference.
- `<cite>` to mark the name of a work, such as a book, play, or song.
- `<dfn>` to mark the defining instance of a term.
- `<abbr>` to represents an abbreviation or acronyme.
- `<code>` to indicate at short fragment of computer code.
- `<time>` to indicate a specific period in time.
- `<address>` to indicate contact information (person, people or organization).

Warning!

Some tags like `<strong>` and `<b>` may look the same visually in your browser. Please remember that HTML is about content, semantics, and not the visual aspect.

``` html
<ul>
  <li>
    I <em>really</em> like driving in San Francisco.
  </li>
  <li>
    The term <i>voilier</i> is a french word which mean "sailing ship".
  </li>
  <li>
    <strong>Warning!</strong> This is not a drill!
  </li>
  <li>
    <b>This text is bold.</b>
  </li>
  <li>
    <p>Atomic Habits: An Easy & Proven Way to Build Good Habits & Break Bad Ones <small>(Penguin Group USA) <small>Kindle Edition</small>
by</small> James Clear <small>  (Author)</small></p>
  </li>
  <li>
    <p>I'm silently correcting <del>you're</del> <ins>your</ins> grammar.</p>
  </li>
  <li>
    I received <s>$500</s> $1000 for that job!
  </li>
  <li>
    I want to understand <wbr>what</wbr><wbr>is</wbr><wbr>going</wbr><wbr>on</wbr>!
  </li>
  <li>
    <mark>This whole text should be highlighted in yellow.</mark>
  </li>
  <li>
    <blockquote>
    Any inaccuracies in this index may be explained by the fact that it has been sorted with the help of a computer.<br>
    — from <cite>The Art of Computer Programming</cite> by Donald Knuth
    </blockquote>
  </li>
  <li>
    <p>The <strong>HTML Definition element</strong>
    (<strong><dfn>&lt;dfn&gt;</dfn></strong>) is
    used to indicate the term being defined within the context<br/> of a
    definition phrase or sentence.</p>
  </li>
  <li>
    <p>You are the <abbr title="Cascading Style Sheets">CSS</abbr> of my <abbr title="HyperText Markup Language">HTML</abbr>.</p>
  </li>
  <li>
    <code></code>
  </li>
  <li>
    <pre>
      <code>
        body {
          color: red;
        }
      </code>
    </pre>
  </li>
  <li>
    <time datetime="2019-09-19">Sept 19, 2019</time>
  </li>
  <li>
    <address>
      <a href="mailto:someone@example.com">someone@example.com</a>
    </address>
  </li>
</ul>
```

### Resources

- [em: The Emphasis element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/lVrJ6veLqy9J6RI6S7mu0w "em: The Emphasis element - HTML: Hypertext Markup Language | MDN")
- [i - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/OI5cXWI_W9HaZZWbTEtiqw "i - HTML: Hypertext Markup Language | MDN")
- [strong: The Strong Importance element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/0wKHX-dDJvKpzg_RsWZdhQ "strong: The Strong Importance element - HTML: Hypertext Markup Language | MDN")
- [b: The Bring Attention To element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/vcbPYM0dnS07ed_kDpiR7w "b: The Bring Attention To element - HTML: Hypertext Markup Language | MDN")
- [small: the side comment element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/ba8FKzjNHpMaecfGhFMzig "small: the side comment element - HTML: Hypertext Markup Language | MDN")
- [del: The Deleted Text element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/IQJIdqUcOq1jUZLGCkyncw "del: The Deleted Text element - HTML: Hypertext Markup Language | MDN")
- [ins - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/1tbKUReUeXV52pBJw239eA "ins - HTML: Hypertext Markup Language | MDN")
- [s - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/wVnZV9RrrXv7e3Dika4RvA "s - HTML: Hypertext Markup Language | MDN")
- [wbr - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/FIAHdBXoHMVeJauzWZg29g "wbr - HTML: Hypertext Markup Language | MDN")
- [mark: The Mark Text element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/WpyzxAlG2HEidwYmaKfIYw "mark: The Mark Text element - HTML: Hypertext Markup Language | MDN")
- [cite: The Citation element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/J5HxmFIxrUilV1qDHDjxCw "cite: The Citation element - HTML: Hypertext Markup Language | MDN")
- [dfn: The Definition element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/15W0hBPjsondzuWkMtrpWw "dfn: The Definition element - HTML: Hypertext Markup Language | MDN")
- [abbr: The Abbreviation element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/CPVkekSpuOQ4lxmEzU5b4A "abbr: The Abbreviation element - HTML: Hypertext Markup Language | MDN")
- [code: The Inline Code element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/kW_MX9pDDgTbfow5bWRT4A "code: The Inline Code element - HTML: Hypertext Markup Language | MDN")
- [time - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/ijtGJv9-EOZ9I5Fj8cq06g "time - HTML: Hypertext Markup Language | MDN")
- [address: The Contact Address element - HTML: Hypertext Markup Language | MDN](https://intranet.alxswe.com/rltoken/KM10TzUfCuNSG3f1AYeucg "address: The Contact Address element - HTML: Hypertext Markup Language | MDN")