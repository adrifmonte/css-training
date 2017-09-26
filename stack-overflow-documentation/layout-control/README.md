# Layout Control
<sub>[back](../../README.md#canonical-learning-resources)</sub>

> <strong>This content was ported over from Stack Overflow Documentation, [now retired](https://meta.stackoverflow.com/q/356294/1064325). To access the source and attribution please access the [Docs archive](https://archive.org/details/documentation-dump.7z) and reference topic ID: ##201709262218296273468##</strong>

- [The display property](#the-display-property)
  - [Inline](#inline)
  - [Block](#block)
  - [Inline Block](#inline-block)
  - [None](#none)

## The display property
<sub>[top](#layout-control)</sub>
<blockquote>

The `display` CSS property is fundamental for controlling the layout and flow of an HTML document. Most elements have a default `display` value of either `block` or `inline` (though some elements have other default values).

# Inline

An `inline` element occupies only as much width as necessary. It stacks horizontally with other elements of the same type and may not contain other non-inline elements.

    <span>This is some <b>bolded</b> text!</span>

[![][1]][1]

As demonstrated above, two `inline` elements, `<span>` and `<b>`, are in-line (hence the name) and do not break the flow of the text.

# Block

A `block` element occupies the maximum available width of its' parent element. It starts with a new line and, in contrast to `inline` elements, it does not restrict the type of elements it may contain.

    <div>Hello world!</div><div>This is an example!</div>

[![][2]][2]

The `div` element is block-level by default, and as shown above, the two `block` elements are vertically stacked and, unlike the `inline` elements, the flow of the text breaks.

# Inline Block

The `inline-block` value gives us the best of both worlds: it blends the element in with the flow of the text while allowing us to use `padding`, `margin`, `height` and similar properties which have no visible effect on `inline` elements.

Elements with this display value act as if they were regular text and as a result are affected by rules controlling the flow of text such as `text-align`. By default they are also shrunk to the the smallest size possible to accommodate their content.

<!--Lets us display using unordered list-->
    
    <!--Inline: unordered list-->
    <style>
    li {
        display : inline;
        background : lightblue;
        padding:10px;

        border-width:2px;
        border-color:black;
        border-style:solid;
        }
    </style>    

    <ul>
    <li>First Element </li>
    <li>Second Element </li>
    <li>Third Element </li>
    </ul>

[![Display:inline][3]][3]

    <!--block: unordered list-->
    <style>
    li {
        display : block;
        background : lightblue;
        padding:10px;

        border-width:2px;
        border-color:black;
        border-style:solid;
        }
    </style>    

    <ul>
    <li>First Element </li>
    <li>Second Element </li>
    <li>Third Element </li>
    </ul>

[![Display:block][4]][4]

    <!--Inline-block: unordered list-->
    <style>
    li {
        display : inline-block;
        background : lightblue;
        padding:10px; 

        border-width:2px;
        border-color:black;
        border-style:solid;
        }

    </style>    

    <ul>
    <li>First Element </li>
    <li>Second Element </li>
    <li>Third Element </li>
    </ul>

[![Display:inline-block][5]][5]

# none
An element that is given the none value to its display property will not be displayed at all.

For example let's create a div-element that has an id of `myDiv`:

    <div id="myDiv"></div>
This can now be marked as not being displayed by the following CSS rule:

<!-- language: lang-css -->

    #myDiv {
        display: none;
    }
When an element has been set to be `display:none;` the browser ignores every other layout property for that specific element (both `position` and `float`). No box will be rendered for that element and its existence in html does not affect the position of following elements.

Note that this is different from setting the `visibility` property to `hidden`. Setting `visibility: hidden;` for an element would not display the element on the page but the element would still take up the space in the rendering process as if it would be visible. This will therefore affect how following elements are displayed on the page.

The `none` value for the display property is commonly used along with JavaScript to show or hide elements at will, eliminating the need to actually delete and re-create them.

  [1]: http://i.stack.imgur.com/tv9k8.png
  [2]: http://i.stack.imgur.com/MCTnB.png
  [3]: http://i.stack.imgur.com/eTy8E.png
  [4]: http://i.stack.imgur.com/fJErb.png
  [5]: http://i.stack.imgur.com/RNjHH.png
</blockquote>

<sub>[top](#layout-control)</sub>
