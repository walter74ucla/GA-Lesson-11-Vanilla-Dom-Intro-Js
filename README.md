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

all the methods for elements are listed [here on mdn](https://developer.mozilla.org/en-US/docs/Web/API/Element)

Will give us the element with id 'container'.

```javascript
document.querySelectorAll('.info');
```

Will give us all elements with class 'info'

What is returned is called a [node list](https://developer.mozilla.org/en-US/docs/Web/API/NodeList) the methods are that you can perform on the list are in the link.

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
puppy.src="https://s3.amazonaws.com/cdn-origin-etr.akc.org/wp-content/uploads/2018/03/12191542/Two-Newfoundland-puppies-running-outside-header.jpg"
```

#### Viewing and changing attributes 

```javascript
const puppy = document.querySelector('#first-img');
```

- access html attribute with `.getAttribute()`

```js
console.log( puppy.getAttribute('src') );
```

- You can also change them with the setAttribute method

```js
const newImgUrl = 'https://i.pinimg.com/originals/dc/e8/c7/dce8c797a6cee1985da55ba6cfcf0bb9.jpg'
puppy.setAttribute('src', newImgUrl)

```


**Create an element**

Created elements will not show until they are **appended** to the DOM.

* **create** an element first ...

```javascript
const div = document.createElement('div');
```

* change a property (text within the element)

```javascript
div.innerText = 'Let there be light'
```
Still will not show up ...

* then **append** it to the body of the page

```javascript
document.body.appendChild(div);
```

You can see in the **Elements** tab whether the element has appended:

![](https://i.imgur.com/2mJQ9Dl.png)


**We can create any tag we want, such as a 'p'**

```javascript
const someP = document.createElement('p');

someP.innerText = "What we have here is a p."

document.body.appendChild(someP);
```

**Prompts**

1. Get the element with id 'container', save it to a variable, and console.log it.

2.  Create a div, saving it to a variable.

3.  Give the div some text with `.innerText =`.

4.  Append the new div to the element with id 'container' `.appendChild()`.

Confirm that new div is **inside** container div (it is a sibling of the **section**s):

![](https://i.imgur.com/5UwEaWD.png)

<br>
<hr>

1.  change all the .big divs to have the text "cheese"

```js
const theDivs = document.querySelectorAll('.big');
for(let i = 0; i < theDivs.length; i++) {
  theDivs[i].textContent = "cheese"
}
```

- look what happens when you try to add html to those elements
```js
for(let i = 0; i < theDivs.length; i++) {
  theDivs[i].textContent = "<h1>cheese</h1>"
}
```

-  it just says `"<h1>cheese</h1>"` on the page.  that's no good.

-  to set HTML inside of an element, use the .innerHTML property

```js
for(let i = 0; i < theDivs.length; i++) {
  theDivs[i].innerHTML = "<h1>cheese</h1>"
}

```


#### Changing CSS

- every element's CSS lives in an object in that element's object called "Style"

```js
const firstBigDiv = document.querySelector('#direct-child-example div:first-child')
console.log(firstBigDiv.style);
```

-  to change a CSS property, you can access it via it's property in camelCase

```js
firstBigDiv.style.backgroundColor = "green"
```


#### Dom Traversal

- you can access any node from any other node using DOM traversal 

```js
const img = document.querySelector('#second-img')

console.log("here's img.parentNode:");
console.log(img.parentNode);
console.log(img.parentNode.parentNode);
console.log(img.parentNode.parentNode.parentNode);
```

- You can access siblings

```js
const img = document.querySelector('#second-img')

console.log(img.previousSibling.previousSibling)
console.log(img.nextSibling.nextSibling)
console.log(img.img.nextElementSibling)
```



**We won't be using many commands**

DOM commands fall into a few broad categories:

* Search / retrieval of elements on the page
* Creating new elements
* Editing the DOM
* Traversal (related to search) - navigating the DOM

We will only need a small handful of these commands for now. Here is a sample:

* **Search**
  * document.querySelector()
  * document.getElementById()
  * document.getElementsByClassName()
  * document.getElementsByName()

* **Creation**
  * document.createElement()
  * node.style
* **DOM editing**
  * node.appendChild()
  * node.removeChild()
  * node.innerText
  * node.setAttribute()
  * node.innerHTML
  * node.id
  * node.classList
* **Traversal**
  * node.childNodes
  * node.children
  * node.firstChild
  * node.previousElementSibling
  * node.nextElementSibling
  * node.nextSibling
  * node.previousSibling

