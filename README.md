# Vanilla-Dom-Intro-Js

# DOM

Your browser also creates **javascript objects** out of the HTML elements. This is an **abstraction**. Why does it do this? Because HTML is just text, and we want a handy way to perform JavaScript operations on the text.

> A browser receives a page as HTML and creates a **representation** of that page as **nested objects**. This representation is stored in memory as the [**D**ocument **O**bject **M**odel](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction). This allows us to interact with the page using JavaScript.

The nested objects form a tree-like structure -- the DOM tree.

![DOM Tree](http://www.webstepbook.com/supplements/slides/images/dom_tree.gif)

The HTML can be considered 'ingredients' from which the DOM is 'cooked'. We interact with the HTML structure by using the objects cooked-up by the browser.


### The document object

Get all of the objects that Chrome has cooked up:

```javascript
document
```

The document looks like HTML in the console, but is an object that contains more objects. The HTML document has child `<body>`, and there is a corresponding object:

```javascript
document.body
```

Shows us all the objects within the body tag.

There is a `<div>` that is a child of `<body>`.

We cannot just grab `document.body.div`, but `document` contains a bunch of useful methods for accessing and manipulating the DOM.
