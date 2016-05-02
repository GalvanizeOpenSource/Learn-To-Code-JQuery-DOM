# Learn To Code: Intro to JQuery and the DOM

Learn how to code the Galvanize way in jQuery and explore the Document Object Model (DOM).

This tutorial is heavily derived from [Learn Query](http://learn.jquery.com). To learn more, visit their site and explore!

## What IS jQuery?

JQuery (also called jQuery in this tutorial) is a JavaScript library initially released in 2006 and stands as the most popular JavaScript library in use today. JQuery *IS* JavaScript, in a sense, written in a way that requires less code and improves the accessibility of an already relatively accessible language. 

This very quick tutorial will help you set up jQuery onto your computer and learn some of its basic usages. 

## What IS the DOM?

The Document Object Model (commonly known as the DOM) is a cross-platform, language-independent convention that allows you to communicate and interact with elements in HTML, XHTML, and XML. Applying a tree-like structure, the DOM is essential to any training of jQuery.

## Pre-requisites for this course

It will be most helpful for you to have a basic understanding of HTML, CSS, and JavaScript. You can gain that knowledge by completing either of the following:

1. The [Galvanize pre-bootcamp course on Codecademy](http://codecademy.com/galvanize), or
2. Completing the [Introduction to HTML and CSS](http://github.com/galvanizeOpenSource/learn-to-code-html-css) and [Introduction to JavaScript](http://github.com/galvanizeOpenSource/learn-to-code-javascript) courses by yourself or at your nearby Galvanize campus.

**Installation requirements for this course**

1. A reliable web browser. We recommend [Google Chrome](http://chrome.google.com) for element inspection.
2. A good text editor. We recommend [Atom.io](atom.io).

## Let's get started!

**Get the necessary files onto your computer!**

1. Go to the link for this course [here](http://github.com/galvanizeOpenSource/learn-to-code-jquery). 
2. Download the ZIP file of the course.
3. Open the ZIP file of this course (do not try to make changes without extraction).
4. Open the unzipped folder of this course in your text editor:
5. Open the above viles in your text editor so that we can view them.
     5. index.html
     6. CSS/style.css
     7. JS/custom.js

**Set up your files to communicate with one another**

At first, your HTML index.html file is not configured with the others or with jQuery. In order for your HTML file to read and apply style and function code, we first have to set it up properly.

Below is what your code should look like once downloaded:
```html
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <title>Demo</title>
</head>
<body>
</body>
</html>
```
Let's change that. Add the following links to the `<head>` element and near the bottom of the `<body>`.
- `<link link rel="stylesheet" type="text/css" href="CSS/style.css" />` in between `<head>` and `</head>`
- `<script src="JS/custom.js></script>` to the bottom of your body tag, just before `</body>`
- `<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>` to the bottom of your body tag, just before `</body>`

Your code should now look a lot more like the following:
```html
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <title>Demo</title>
    <link link rel="stylesheet" type="text/css" href="CSS/style.css" />
</head>
<body>
   <script src="JS/custom.js"></script>
   <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
</body>
</html>
```
We will be lowing jQuery from Google APIs instead of downloading the entire library onto our own computer. You're welcome to download the file yourself [here], but this will be a more efficient way to use JQuery moving forward.

## Your first task: Ready the Document!

Let's begin by familiarizing ourselves the the general syntax of jQuery. \n

**You can invoke jQuery in generally two ways:**
- `jQuery.` - the "super" object that invokes all other objects in your jQuery file.
- `$` - Become familiar with this symbol - it is the alias for `jQuery`. Its appearance in a JavaScript file or an HTML script tag implies that jQuery will be used on this line and the blocks that follow. 

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
     window.alert("The document is ready!");
```
This should create a pop-up window saying "The document is ready!"! (You'll need to allow pop-ups in your browser.)

Add the code to look like the following, then save and refresh your browser.
```javascript
$( document ).ready(function() {
     window.alert("The document is ready!");
});
```

## More functionality: On-Click Events!

In jQuery, events are methods that happen with the user's interaction. There are a LOT of them in the jQuery library, but we're going to start with a common on: `click`.

First, let's create something in our HTML for the user to click on. Insert the following code somewhere in the `<body>`:

```html
<button type="button">This is a button.</button>
```

This is a button in HTML, set to the browser's default settings. Add it to the HTML below:
```html
<!doctype html>
<html>
<head>
     <meta charset="utf-8">
     <title>Demo</title>
     <link link rel="stylesheet" type="text/css" href="CSS/style.css" />
</head>
<body>
     <button type="button">This is a button.</button>
     <script src="JS/custom.js"></script>
     <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
</body>
</html>
```

Save your HTML file and refresh your browser. It should now appear. How do we make this button interact with the jQuery? 1. 1. Capture `button` in the jQuery's selector:
```javascript
     $( button )
```
2. Cite the jQuery method we want to use. In this case, we're using `.click` so that something happens when you click the button:
```javascript
     $( button ).click()
```
3. We are going to create a JavaScript function within the `.click` method to do a specific function for this `event`. For simplicity, let's create another alert.
```javascript
     $( button ).click(function({
          window.alert("Nice clicking, there, friend!");
     });
```     
4. Put it all in the `$( document ).ready()`, save your JS file, and refresh the browser. Did it work?
```javascript
$( document ).ready(function() {
     window.alert("The document is ready!");
     // new code below
     $( button ).click(function({
          window.alert("Nice clicking, there, friend!");
     });
});
``` 
