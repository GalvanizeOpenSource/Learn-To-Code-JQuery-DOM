# Learn To Code: Intro to JQuery and the DOM

Learn how to code the Galvanize way in jQuery and explore the Document Object Model (DOM).

This tutorial is heavily derived from [Learn Query](http://learn.jquery.com). To learn more, visit their site and explore!

## What IS jQuery?

JQuery (also called jQuery in this tutorial) is a JavaScript library initially released in 2006 and stands as the most popular JavaScript library in use today. This very quick tutorial will help you set up jQuery onto your computer and learn some of its basic usages. 

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
```
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
- `<link src="CSS/style.css" />` in between `<head>` and `</head>`
- `<script src="JS/custom.js></script>` to the bottom of your body tag, just before `</body>`
- `<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>` to the bottom of your body tag, just before `</body>`

Your code should now look a lot more like the following:
```
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <title>Demo</title>
    <link src="CSS/style.css" />
</head>
<body>
    <a href="http://jquery.com/">jQuery</a>
   <script src="JS/custom.js"></script>
   <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
</body>
</html>
```



