# Length Units
<sub>[back](../../README.md#canonical-learning-resources)</sub>

> <strong>This content was ported over from Stack Overflow Documentation, [now retired](https://meta.stackoverflow.com/q/356294/1064325). To access the source and attribution please access the [Docs archive](https://archive.org/details/documentation-dump.7z) and reference topic ID: ##201709262257318074562##</strong>

- [Font size with rem](#font-size-with-rem)
- [Creating scalable elements using rems and ems](#creating-scalable-elements-using-rems-and-ems)
- [vmin and vmax](#vmin-and-vmax)
- [vh and vw](#vh-and-vw)
- [using percent %](#using-percent)
- [List of Length Units](#list-of-length-units)

## Font size with rem
<sub>[top](#length-units)</sub>
<blockquote>

CSS3 introduces a few new units, including the [`rem`](https://www.w3.org/TR/css-values/#font-relative-lengths) unit, which stands for "root em". Let's look at how `rem` works.

First, let's look at the differences between `em` and `rem`.

* **em**: Relative to the font size of the parent. This causes the compounding issue
* **rem**: Relative to the font size of the root or `<html>` element. This means it's possible to declare a single font size for the html element and define all `rem` units to be a percentage of that.

The main issue with using `rem` for font sizing is that the values are somewhat difficult to use. Here is an example of some common font sizes expressed in `rem` units, assuming that the base size is 16px :

 - 10px = 0.625rem
 - 12px = 0.75rem
 - 14px = 0.875rem
 - 16px = 1rem (base)
 - 18px = 1.125rem
 - 20px = 1.25rem
 - 24px = 1.5rem
 - 30px = 1.875rem
 - 32px = 2rem

**CODE:**

<!-- if version [gte 3] -->

<!-- language: lang-css -->

    html { 
      font-size: 16px; 
    }
    
    h1 { 
      font-size: 2rem;          /* 32px */
    }
    
    p { 
      font-size: 1rem;          /* 16px */ 
    }
    
    li { 
      font-size: 1.5em;         /* 24px */
    }

<!-- end version if -->
</blockquote>

## Creating scalable elements using rems and ems
<sub>[top](#length-units)</sub>
<blockquote>

<!-- if version [gte 3] -->
You can use `rem` defined by the `font-size` of your `html` tag to style elements by setting their `font-size` to a value of `rem` and use `em` inside the element to create  elements that scale with your global `font-size`.

**HTML:**

    <input type="button" value="Button">
    <input type="range">
    <input type="text" value="Text">

**Relevant CSS:**

<!-- language: lang-css -->

    html {
      font-size: 16px;
    }
    
    input[type="button"] {
      font-size: 1rem;
      padding: 0.5em 2em;
    }

    input[type="range"] {
      font-size: 1rem;
      width: 10em;
    }

    input[type=text] {
      font-size: 1rem;
      padding: 0.5em;
    }

**Possible Result:**

[![scalable input elements][1]][1]


  [1]: http://i.stack.imgur.com/Klztk.gif
<!-- end version if -->
</blockquote>

## vmin and vmax
<sub>[top](#length-units)</sub>
<blockquote>

* **vmin**: Relative to 1 percent of the viewport's smaller dimension
* **vmax**: Relative to 1 percent of the viewport's larger dimension

In other words, 1 `vmin` is equal to the smaller of _1 vh_ and _1 vw_

1 `vmax` is equal to the larger of _1 vh_ and _1 vw_

**Note**: `vmax` is [not supported](http://caniuse.com/#feat=viewport-units) in:
 - any version of Internet Explorer
 - Safari before version 6.1
</blockquote>

## vh and vw
<sub>[top](#length-units)</sub>
<blockquote>

CSS3 introduced two units for representing size. 

* `vh`, which stands for `viewport height` is relative to 1% of the viewport height
* `vw`, which stands for `viewport width` is relative to 1% of the viewport width


<!-- if version [gte 3] -->
<!-- language: lang-css -->
    div { 
      width: 20vw; 
      height: 20vh;
    }
<!-- end version if -->

Above, the size for the div takes up 20% of the width and height of the viewport
</blockquote>

## using percent %
<sub>[top](#length-units)</sub>
<blockquote>

One of the useful unit when creating a responsive application.

Its size depends on its parent container.

**Equation:** 

> ( Parent Container`s width ) * ( Percentage(%) ) = Output


**For Example:** 

*Parent* has **100px** width while the *Child* has **50%**. 

**On the output**, the *Child*'s width  will be half(50%) of the *Parent*'s,  which is **50px**.

**HTML**

    <div class="parent">
       PARENT
       <div class="child">
         CHILD
       </div>
    </div>

**CSS**

    <style>

    *{
      color: #CCC;
    }
    
    .parent{
      background-color: blue;
      width: 100px;
    }
    
    .child{
      background-color: green;
      width: 50%;
    }
    
    </style>

**OUTPUT**

[![enter image description here][1]][1]


  [1]: http://i.stack.imgur.com/t6pPl.png
</blockquote>

## List of Length Units
<sub>[top](#length-units)</sub>
<blockquote>

| Group  | Comprised of                             | Examples   |
| ------ | ---------------------------------------- | ---------- |
| *A*    | id selectors                             | `#foo`     |
| *B*    | class selectors<br> attribute selectors<br> pseudo-classes | `.bar`<br> `[title]`, `[colspan="2"]`<br> `:hover`, `:nth-child(2)` |
| *c*    | type selectors<br> pseudo-elements       | `div`, `li`<br> `::before`, `::first-letter` |


| Unit | Description |
| ---- | ----------- |
| % | Define sizes in terms of parent objects or current object dependent on property |
| em | Relative to the font-size of the element (2em means 2 times the size of the current font) |
| rem | Relative to font-size of the root element |
| vw | Relative to 1% of the width of the viewport* |
| vh | Relative to 1% of the height of the viewport* |
| vmin | Relative to 1% of viewport's* smaller dimension |
| vmax | Relative to 1% of viewport's* larger dimension |
| cm | centimeters |
| mm | millimeters |
| in | inches (1in = 96px = 2.54cm) |
| px | pixels (1px = 1/96th of 1in) |
| pt | points (1pt = 1/72 of 1in) |
| pc | picas (1pc = 12 pt) |
| s | seconds (used for animations and transitions) |
| ms | milliseconds (used for animations and transitions) |
| ex | Relative to the x-height of the current font |
| ch | Based on the width of the zero (0) character |
| fr | fractional unit (used for CSS Grid Layout) |

</blockquote>

<sub>[top](#length-units)</sub>
