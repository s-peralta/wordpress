Beginners Guide to JavaScript
=============================

<!--All of the credit for this cheat sheet goes to <a href="http://blog.adtile.me/authors/viljami/">Viljami S.</a>. Majority of this JS Guide is a condensed/straight to the point version of his article.-->

Syntax / Snippets / Best Design Patterns



Getting the DOM ready
---------------------

```
  document.addEventListener("DOMContentLoaded", function() {
    // Code
  }, false);
```

Selectors API
---------------------

```
  var element = document.querySelector("div");
```

OR

```
  var elements = document.querySelectorAll(".container div");
```

Traversing the DOM
---------------------

```
  // Getting the parent node
var parent = document.querySelector("div").parentNode;

// Getting the next node
var next = document.querySelector("div").nextSibling;

// Getting the previous node
var next = document.querySelector("div").previousSibling;

// Getting the first child element
var child = document.querySelector("div").children[0];

// Getting the last child
var last = document.querySelector("div").lastElementChild;
```

Adding, Removing and Toggling Classes
---------------------

```
element.classList.add("bar");

// Removing a class
element.classList.remove("foo");

// Checking if has a class
element.classList.contains("foo");

// Toggle a class
element.classList.toggle("active");
```
