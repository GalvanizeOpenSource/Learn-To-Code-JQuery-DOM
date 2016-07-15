# Learn To Code: Intro to JQuery and the DOM

Learn how to code the Galvanize way in jQuery and explore the Document Object Model (DOM).

This tutorial is heavily derived from [Learn jQuery](http://learn.jquery.com). To learn more, visit their site and explore!

## What IS jQuery?

JQuery (also called jQuery in this tutorial) is a JavaScript library initially released in 2006 and stands as the most popular JavaScript library in use today. JQuery *IS* JavaScript, in a sense, written in a way that requires less code and improves the accessibility of an already relatively accessible language.

This very quick tutorial will help you set up jQuery onto your computer and learn some of its basic usages.

## What IS the DOM?

The Document Object Model (commonly known as the DOM) is a cross-platform, language-independent convention that allows you to communicate and interact with elements in HTML, XHTML, and XML. Applying a tree-like structure, the DOM is essential to any training of jQuery.

## Pre-requisites for this course

It will be most helpful for you to have a basic understanding of HTML, CSS, and JavaScript. You can gain that knowledge by completing the following courses by yourself or at your nearby Galvanize campus:

- [Introduction to HTML and CSS](http://github.com/galvanizeOpenSource/learn-to-code-html-css)
- [Introduction to JavaScript](http://github.com/galvanizeOpenSource/learn-to-code-javascript)

**Installation requirements for this course**

1. A reliable web browser. We recommend [Google Chrome](http://chrome.google.com) for element inspection.
2. A good text editor. We recommend [Atom.io](http://flight-manual.atom.io/getting-started/sections/installing-atom/).

## Let's get started!

**Get the necessary files onto your computer!**

1. Go to the link for this course [here](http://github.com/galvanizeOpenSource/learn-to-code-jquery).
2. Download the ZIP file of the course.
3. Open the ZIP file of this course (do not try to make changes without extraction).
4. Open the unzipped folder of this course in your text editor:
5. Open the above files in your text editor so that we can view them.
     5. index.html
     6. CSS/style.css
     7. JS/custom.js

**Set up your files to communicate with one another**

At first, your index.html file is not configured with the others or with jQuery. In order for your HTML file to read and apply style and function code, we first have to set it up properly.

Below is what your code should look like once downloaded:
```html
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <title>Demo of jQuery</title>
</head>
<body>
<h1>Welcome to jQuery! Let's get started below.</h1>
</body>
</html>
```
Let's change that. Add the following links to the `<head>` element and near the bottom of the `<body>`.
- `<link rel="stylesheet" type="text/css" href="CSS/style.css" />` in between `<head>` and `</head>`
- - `<script src="https://code.jquery.com/jquery-3.1.0.min.js"></script>` to the bottom of your body tag, just before `</body>`
- `<script src="JS/custom.js"></script>` to the very bottom of your body tag, just before `</body>` but below the Google jQuery API link **(this specific placement is vital!)**


Your code should now look a lot more like the following:
```html
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <title>Demo of jQuery</title>
    <link link rel="stylesheet" type="text/css" href="CSS/style.css" />
</head>
<body>
<h1>Welcome to jQuery! Let's get started below.</h1>     
   <script src="https://code.jquery.com/jquery-3.1.0.min.js"></script>
   <script src="JS/custom.js"></script>
</body>
</html>
```
We will be loading jQuery from Google APIs instead of downloading the entire library onto our own computer. You're welcome to download the file yourself [here](http://plugins.jquery.com/multiDownload/), but this will be a more efficient way to use jQuery moving forward.

## Your first task: Ready the Document!

Let's begin by familiarizing ourselves with the the general syntax of jQuery. \n

#### JQuery is so "money" (nobody talks like that anymore)

**You can invoke jQuery in generally two ways:**
- `jQuery.` - the "super" jQuery object that invokes all other objects to point to your jQuery library in your JavaScript file.
- `$` - Become familiar with this symbol - it is the alias for `jQuery`. Its appearance in a JavaScript file or an HTML script tag implies that jQuery will be used on this line and the blocks that follow. One would say that this is the reason jQuery is so .... money!

After invoking jQuery, the syntax follows the JavaScript standard of "Define, Declare, Call". Behold, the first function you declare: "Document, Ready"!
```javascript
$( document ).ready(function() {
     // insert the rest of your code here.
});
```
It is not wise to manipulate a page unless the elements are completely loaded. This is why we put our JavaScript invocations near the bottom to allow for the page to load first. in jQuery, we start that process with "Document, Ready", and the rest of your code will be initialized here.

**Remember:** we've set up our page so that jQuery will be running on a different file, not the HTML one. *Why should we get into the practice of coding this way?*

#### Now what? Let's create an alert!

Let's add the following code to your `$( document ).ready` function:
```javascript
     alert("The document is ready! (jQuery is working!)");
```
This should create a pop-up window saying "The document is ready!" (You'll need to allow pop-ups in your browser.)

Add the code to look like the following, then save and refresh your browser.
```javascript
$( document ).ready(function() {
     alert("The document is ready! (jQuery is working!)");
});
```
**Note:** is this alert pops up, that means your JavaScript code is working. This is one way to check if that is the case. (What are some more conventional ways to check this?)

## More functionality: On-Click Events!

In jQuery, events are methods that happen with the user's interaction. There are a LOT of them in the jQuery library, but we're going to start with a common on: `click`.

First, let's create something in our HTML for the user to click on. Insert the following code somewhere in the `<body>`:

```html
<button>This is a button.</button>
```

This is a button in HTML, set to the browser's default settings. Add it to your `<body>`.

Save your HTML file and refresh your browser. It should now appear. How do we make this button interact with the jQuery?

**Choose your selector!** Capture `button` in the jQuery's selector:
```javascript
     $('button')
```
**Declare the method!** Cite the jQuery method we want to use. In this case, we're using `.click` so that something happens when you click the button:
```javascript
     $('button').click()
```
**Define the method!** We are going to create a JavaScript function within the `.click` method to do a specific function for this `event` with an empty parameter. For simplicity, let's create another alert.
```javascript
     $('button').click(function() {
          alert("Nice clicking, there, friend!");
     });
```     
**Save and check!** Put it all in the `$( document ).ready()`, save your JS file, and refresh the browser. Did it work?
```javascript
$( document ).ready(function() {
     alert("The document is ready!");
     // new code below
     $('button').click(function() {
          alert("Nice clicking, there, friend!");
     });
});
```
Now you know the general process of using jQuery. Let's try something new!

## Adding and Removing Classes in jQuery

Let's face it - your button is ugly. We can make it look better. We're going to create three things:

1. A link that will add our button with new styles  
2. A link that will remove the styles
3. A link that will toggle between having the two styles


#### Back to CSS

Fortunately, your CSS file already has a class called `.super-button` that can instantly improve the quality of yours:
```css
.super-button {
    color: #fff;
    background-color: #0275d8;
    border-color: #0275d8;
    padding: .75rem 1.25rem;
    font-size: 1.25rem;
    line-height: 1.333333;
    border-radius: .3rem;
    border: 1px solid transparent;
}    
```
Don't worry if you don't fully understand what's happening here, but if you're interested, we're sampling the [Bootstrap large button](http://v4-alpha.getbootstrap.com/components/buttons/) class.

#### Create the first link: #Add-Class

Add the following code into the `<body>` of your HTML. It is a link with text, but for now it lacks function.
```html
<div>
     <a>Add Class</a>
</div>     
```
We'll need to give this link an `id` so that it matches up with the jQuery we'll create later. I suggest `#add-class`.
```html
<div>
     <a id="add-class">Add Class</a>
</div>
```
Now we're ready to set up our jQuery function. Add the following script into your `$( document ).ready()` function:
```javascript
     $( '#add-class' ).click(function() {
     });
```
Right now ths function does nothing when you click on it. Add the following script to this new function:
```javascript
     $( '#add-class' ).click(function() {
          $( 'button' ).addClass('super-button');
     });
```
Let's slow down for a second. What we've done is set up our jQuery file so that when you click on an element with the ID `#add-class`, it will add the CSS styles under `.super-button` to that `button`. Make sense?

*Gut check: what if we added more buttons? What would happen if we clicked this link?*

Save all of your code and refresh your browser. Test the link. Did it work?

#### Create the second link: #Remove-Class

Let's keep the party going. Let's add a link that will remove the class. First step: adding the HTML below the last link.
```html
<div>
     <a id="remove-class">Remove Class</a>
</div>
```
We're now working with a new ID `#remove-class`. Let's make sure it has something to work with in the jQuery file. Add the following code in your `$( document ).ready()` function.
```javascript
     $( '#remove-class' ).click(function(){
          $( 'button' ).removeClass('super-button');
     });
```
Notice the new event handler `.removeClass` - if you click on this new link, you'll remove the class you've just added (but only if you've added it).

*Gut check: what if you never clicked on the first link? What would be the effect of clicking this one?*

#### Create just one more link: #Toggle-Class

Creating a button to do one thing and another to undo it is... kind of lame. Fortunately, in jQuery, there's another method you can use to `toggle` back and forth between `add` and `remove`: the conveniently named `.toggleClass()`.

First step: create a third link in your HTML with the ID `toggle-class`.
```html
<div>
     <a id="toggle-class">Toggle Class</a>
</div>
```
Second step:
```javascript
     $( '#toggle-class' ).click(function(){
          $( 'button' ).toggleClass('super-button');
     });
```
Save your changes and refresh your browser. Did it work?

Now you know how to add classes and IDs in HTML that you can interact with in jQuery!

## Can you deal with `$( this )`?

Earlier, we asked what would happen if your selector contained `button`, and **spoiler alert** the jQuery method changes every instance of `button` on the page. What if we just wanted to change the very thing we clicked on instead?

Let's create a few `<div>` fields with a class with style attributes that's already in your CSS: `.click-this`.

```html
<div class="click-this">
Click this #1!
</div>
<div class="click-this">
Click this #2!
</div>
<div class="click-this">
Click this #3!
</div>
```
Good! Now move over to your `custom.js` file and add the following jQuery code into the `$( document ).ready()` function block. Notice something different in one of the selectors?

```javascript
     $( '.click-this' ).click(function(){
          $( this ).toggleClass('click-this');
     });
```
The selector `this` is a cool jQuery selector that affects the same element in the selector above it. It will only impact that particular element, even if they share the same class!

Save your changes, refresh your browser, and test whether this works on all three `<div>`s.

## Time to dive into the DOM!

As started earlier, the **Document Object Model** or **DOM** for short is how your HTML is structured to allow for jQuery and other languages to move or *traverse* through them to find what they need in a page.

![alt text](http://www.w3schools.com/jquery/img_travtree.png "DOM Traverse Tree from W3Schools")

**Illustration from W3Schools.com explained:**
- The `<div>` element is the parent of `<ul>`, and an ancestor of everything inside of it
- The `<ul>` element is the parent of both `<li>` elements, and a child of `<div>`
- The left `<li>` element is the parent of `<span>`, child of `<ul>` and a descendant of `<div>`
- The `<span>` element is a child of the left `<li>` and a descendant of `<ul>` and `<div>`
- The two `<li>` elements are siblings (they share the same parent)
- The right `<li>` element is the parent of `<b>`, child of `<ul>` and a descendant of `<div>`
- The `<b>` element is a child of the right `<li>` and a descendant of `<ul>` and `<div>`

In other words, elements follow an implicit family tree-style hierarchy of "parent" and "child", of "ascendant" and "descendant". If they are are equivalent in hierarchy, they are known as "siblings."

In jQuery, we can write code for a `parent` element that impacts the `child`. Let's use the example where this comes in most handy: **the list**.

Create a list with the following HTML code in your `index.html` file. Add a button at the bottom.
```html
<ul>This is a list!
     <li>Item #1</li>
     <li>Item #2</li>
     <li>Item #3</li>
</ul>
<button></button>
```

#### Remove the children (settle down...)

Let's create a jQuery function that deletes the children elements of the list.

**Gut check:** one of our functions may be conflicting with the one we're about to make. I'm going to disable it with double dashes before each line:
```javascript
    // $( 'button' ).click(function() {
     //    window.alert("Nice clicking there, my friend!");
    // });
```
You can delete it or disable it - we won't be using it again.

First, we have to create an ID for the list: `item-list`. We also need an ID for the button: `delete-item`. Name the button as well.
```html
<ul id="item-list">This is a list!
     <li>Item #1</li>
     <li>Item #2</li>
     <li>Item #3</li>
</ul>
<button id="delete-list">Delete list</button>
```

Next, we go into our `custom.js` file and add yet another jQuery function:

```javascript
     $( '#delete-list' ).click(function() {
          $( '#item-list' ).children().remove();
     });
```

What's happening here is that when you click on the button with ID `#delete-item`, it will look for the ID `item-list`, then for one of its children elements, and remove it. Save all of your changes and try it out yourself.

Did the entire list get deleted? If so, it worked!

Notice how we had to **chain** the methods of `.children()` and `.remove()` in order to make this work. This is part of the fun of working in an *object-oriented language* in dot notation!

*Gut check: what if we just wanted to remove one of the items at a time? Can you do it without creating an entirely new jQuery function?*

#### Let's get back at our parents instead! (Settle down...)

Create a new method where if you click on one of the items of the list, it will do something to the parent element. This time, let's change the text of that element to something else. We're going to make this conditional to any `<ul>` element.

```javascript
     $( 'li' ).click(function() {
          $( this ).parent();
      });
```

This time, let's add a method `.text("We just changed the text! Take that, parents!");` to this function.

```javascript
     $( 'li' ).click(function() {
          $( this ).parent().text("We just changed the text! Take that, parents!")>;
      });
```

Save your work and refresh your browser. What happened? *and at what cost...?*

#### Play into the sibling rivalry instead!

The `<ul>` elements are siblings of one another. Let's click on one element and change the others! We'll need to modify our current block so that there are no conflicts.

```javascript
     $( 'li' ).click(function() {
          $( this ).siblings().text("My siblings are dorks!");
      });
```

Did it work? What happens if you click on another sibling? (Oh, does your medicine taste bitter...)

# CONGRATS! YOU NOW KNOW (A LITTLE) JQUERY AND THE DOM!

## Play around in the sandbox!

Nice work - you're picking up the basics so far, but the jQuery library is vast! Why not try some more complicated tasks:

- Add `<li>` elements so that your list doesn't disappear when you change the content
- Create a form to submit values directly to the page
- Add an image and modify its height and width
- Make an element disappear.... slowly...

Here are some solid resources for you to explore and tinker around:

- [Learn jQuery](https://learn.jquery.com/)
- [Codecademy](https://www.codecademy.com/tracks/jquery)
- [W3Schools](http://www.w3schools.com/jquery/)

Want to code more the best instructors? Check out Galvanize's Full Stack Immersive Program!

- 24 Week Full-Time Program
- 97% Job Placement Rate within six months
- Average starting salary: $77,000 per annum
- Scholarships available for those who qualify
- Learn more at http://galvanize.com/courses/fullstack/

#### About the Author

[Lee Ngo](http://linkedin.com/in/leengo) is an evangelist for Galvanize based in Seattle. Previously he worked for UP Global (now Techstars) and founded his own ed-tech company in Pittsburgh, PA. Lee believes in learning by doing, engaging and sharing, and he teaches code through a combination of visual communication, teamwork, and project-oriented learning.

You can email him at lee.ngo@galvanize.com for any further questions.
