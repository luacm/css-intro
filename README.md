# Introduction to CSS
So, you've mastered defining the structure of your website using [HTML](https://github.com/luacm/html) and you're a bit... underwhelmed. Sure, it has structure, but it has no *style*. That's where CSS comes in.

Remember our Web Trifecta:

1. HTML: The semantics of the site.
2. CSS: The presentation of the site.
3. JavaScript: The behavior of the site.

So now we're on the second part! The presentation.

## What is CSS?
CSS stands for Cascading Style Sheet. That might not make much sense now, but it will shortly. 

Basically, CSS is just a list of rules - rules that define how certain elements on your page look. Here's an example:

```CSS
h1 {
  color: purple;
  font-size: 36px;
  text-align: center;
}
```

Here, we said that all ```<h1>``` tags should have purple text, a font size of 36px, and be center aligned. Cool, huh?

## Where Do I Write My CSS?
Truth be told, you can put your CSS lots of places. However, for now, we'll just go over the best place to put it: a separate file.

### Folder Structure
Generally, this is a good folder structure to follow:
```
root
|_index.html
|_css
  |_main.css
  
```
That means you want to create a ```css``` folder and make a file called ```main.css``` inside of it. You don't have to call it ```main.css```, but it's a decent choice.

### Linking in your CSS File
So, now that we have our folder structure setup, we can link in the CSS file to be used with our HTML page. We typically put it in the ```<head>``` tag.

```HTML
<html>
  <head>
    <title>The Daily Bugle</title>
    <link href="css/main.css" type="text/css" rel="stylesheet">
  </head>
  <body>
    ...
  </body>
</html>
```
Do you see the ```<link>``` tag in there? That where we pull in our stylesheet. You just reference the path of the css file in the ```href``` attribute. You'll also notice that ```<link>``` has neither a closing tag nor a ```/``` in the tag. Sometimes you just don't need it. HTML isn't always the most consistent of languages. Luckily there aren't too many tags to memorize, so you'll memorize this stuff quickly.

## How Do I Write CSS?
So, we provided one example above, but you can do so much more. But before we can get into all the stuff you can do, we have to go over *how* you do it. 

### Format of a Selector and Rule
CSS is a list of selectors and rules. Selectors are ways to describe groups of HTML elements. Here are some examples where we select elements by groups of tags:

```CSS
h1 {
  /* Applies to all h1 elements */
}

h1, h2 {
  /* Applies to all h1 and h2 elements */
}

li {
  /* Applies to all li elements (list items) */
}

ul li {
  /* Applies only to list items that are in unordered lists */
}

ul > li {
  /* Applies only to list items that are direct descendents of unordered lists 
     e.g. it would apply to this:
     <ul>
        <li></li>
     </ul>
     
     but NOT this:
     <ul>
        <span><li></li></span>
     </ul>
  
  */
}
```

### Classes and ID's
Styling tags is nice and all, but what if you don't want to style *all* of the unordered lists, but just *some* of them. That brings us into two new concepts: **classes** and **ids**. 

#### Classes
Classes let you describe groups of elements that should have common properties. For example, maybe you want to have a class that indicates what an item looks like in a list if it was selected by the user.

**index.html**
```HTML
<h1>Which Superhero doesn't belong?</h1>
<ul>
  <li>Batman</li>
  <li>Superman</li>
  <li class="selected">Spider-Man</li>
  <li>Green Lantern</li>
</ul>

<h1>Top Superheros of All Time</h1>
<h2>Choose your favorite.</h2>
<ol>
  <li class="selected">Spider-Man</li>
  <li>Iron Man</li>
  <li>Batman</li>
  <li>Superman</li>
</ol>
```

**css/main.css**
```CSS
ul .selected {
  color: red;
}

ol .selected {
  color: blue;
}

li.selected {
  font-size: 24px;
}
```

### Cascading and the Point System
To be continued...

# Additional Resources

* [HTML/CSS/JavaScript from the Ground Up](http://www.youtube.com/watch?v=60O1CJqh8IM&list=PLDE314C0C8581E8BA): While the official video were taken down a while ago, this tutorial series by Google lives on in a YouTube playlist. We can't recomment this series enough. It can move a little fast, but there isn't any other tutorial series we've found that's so comprehensive and well-laid-out.
