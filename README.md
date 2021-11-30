# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  SOFTWARE ENGINEERING IMMERSIVE


## Dom Manipulation w/ Forms

### The Humble Text Input

Mouse (and other various) keyboard events are a good first attempt to process user interactions and update the DOM in process, but there are many more and potentially richer methods at our disposal.  _Input_ tags are one of these methods.

Perhaps the most commonly recognized is the "text" input:

```html
<input type="text" />
```

Notice that it is a self-closing tag.  It has no children or inner content exposed directly.  Text inputs manage the state of the text inside them automatically.  Forms can manage several inputs, text or others, using the `name` attribute on the element, but for now let's just extract the value of the input with javascript.

```js
const input = document.querySelector('input');
const value = input.value;
```

The `input` element returned by `querySelector` includes a `value` property that can either be read or updated:

```js
input.value = 'doggo';
console.log(input.value);
```

All we need is a button or click event to trigger some code to fetch the value out of the input and then perform a given action with it, e.g., creating a new element and appending it to the DOM.

### Todo List Exercise

Let's write up a form with a text input and a button:

- Create a ```<form></form>``` element.
	- All form attributes are optional. You can build a form without the ```<form>``` tag just using ```inputs``` and ```buttons``` but you won't have access to some features specifically designed for ```forms```.
	- The `action` attribute defines the location (URL) where the form's collected data should be sent when it is submitted. This is the built-in attribute that causes forms to reload a page, and the reason we often have to use ```preventDefault()``` when submitting data.

- Add a text input to the html with an id of todo-input: `<input id='todo-input'/>`. Notice how this tag is self closing.
	- ```inputs``` have a ```type``` attribute. The most common is ```text```.
	- The ```value``` attribute keeps track of the content (or state) inside the input field. This will be very important later.
	- ```autoFocus``` is an attribute that can be added to force focus to this specific input when the page loads.
- Add a ```<label></label>``` element above your `<input />`.
       - Labels always need the attribute ```for``` which is the id of the `input` belonging to this label.
       For example you might have:
       ```html
       <label for="yourName">Name</label>
       <input type="text" id="yourName">
       ```
- Add a ```<button></button>```
	- Inside a form, add a ```button``` element with an attribute of ```type``` equal to 'submit'. You will also see forms with```<input type='submit'>``` but accessibility best practice is to use a button.
- Let's create a ```<ul>``` element with an id of 'todo-list'. This is where our to-do items will be rendered.

#### Form Accessibility

http://web-accessibility.carnegiemuseums.org/code/forms/

#### Different Types of Inputs

What other types of inputs do you see in this example form? What good accessibility practices do you see in this example form?

https://codepen.io/esin87/pen/QWKoMQZ


#### Let's jump into the our JS file
First, query select for all of the elements we just created.

Next, we need to initializing an empty array and store it as a variable. This array will eventually contain a set of strings that represent each item on our to-do list.

#### Add a Todo

Register a click event listener on the ```button``` or ```submit```. This click needs to call a function that should:
- extract the value of the text input
- add the value to the `todos` array
- loops through our array and adds each todo to the ```ul``` as a ```li```.

Uh oh, you may have some duplicates!

- In the looping function, add a command that resets the ```innerText``` of our ```<ul>``` to an empty string before it loops and adds.
- For good measure let's clear out our text input too.

If we've done this correctly, all items we enter into the input field should be displayed on our page!


### Hungry for More?
#### Videos
- [HTML Forms](https://www.youtube.com/watch?v=-5tH2qnTnH0&index=16&list=PLdnONIhPScST0Vy4LrIZiYKpFNoxgyH7J)

#### Readings
- [Select Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)
- [HTML Form Reference](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms)
- [HTML Input Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
- [Native Form Widgets](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms/The_native_form_widgets)
- [Inspiration for Text Inputs](http://tympanus.net/codrops/2015/01/08/inspiration-text-input-effects/)

