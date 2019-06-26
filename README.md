# Vanilla-Dom-Intro-Js

# DOM

Your browser also creates **javascript objects** out of the HTML elements. This is an **abstraction**. Why does it do this? Because HTML is just text, and we want a handy way to perform JavaScript operations on the text.

> A browser receives a page as HTML and creates a **representation** of that page as **nested objects**. This representation is stored in memory as the [**D**ocument **O**bject **M**odel](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction). This allows us to interact with the page using JavaScript.

The nested objects form a tree-like structure -- the DOM tree.

![DOM Tree](https://www.webstepbook.com/supplements/slides/images/dom_tree.gif)

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


In Chrome console:

```javascript
document.querySelector('#container');
```

Will give us the element with id 'container'.

```javascript
document.querySelectorAll('.info');
```

Will give us all elements with class 'info'

<br>
<hr>

## Common pattern: Save a DOM element to a variable

In Chrome console

**Select an element**

When you select an element from the DOM, save it a variable for handy reference.

```javascript
const puppy = document.querySelector('#first-img');
```

Change the attribute `src`, which is **property** of the object:

```javascript
kitten.src="https://s3.amazonaws.com/cdn-origin-etr.akc.org/wp-content/uploads/2018/03/12191542/Two-Newfoundland-puppies-running-outside-header.jpg"
```
**Create an element**

Created elements will not show until they are **appended** to the DOM.

* **create** an element first ...

```javascript
const elem = document.createElement('div');
```

* change a property (text within the element)

```javascript
elem.innerText = 'Let there be light'
```
