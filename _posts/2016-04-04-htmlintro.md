---
layout: post
title:  "Intro to HTML"
date:   2016-04-04 00:00:00 -0700
---

So what is HTML? What's all the crazy and hype about it? What makes it so cool? The idea behind HTML is that it provides a simple way for people to create "markup" to then be viewed on the web. *We all love the web, so let's make some HTML!*

Let's start with a basic HTML structure.

```html
<html>
  <head>
    
  </head>
  <body>
    
  </body>
</html>
```

So right off the bat, we can see the HTML has two very important sections, the `head` and the `body`. What do those sections do? The head section is where you import and initialize items that often won't be viewed on the page. Below is an example of what goes into a head tag.

```html
<head>
  <title>My Awesome Site</title>
  <link type='stylesheet' href='css/style.css'>
  <meta name='desc' content='This is a description for my awesome site.'>
</head>
```

So what does all this stuff do? Well first off, we initialize a title, like the one's you can see on the tabs of your web browser. Then we import a stylesheet (more on this later) from `css/style.css`. Finally, we set up a meta description that will appear when this site is shown on websites.

Awesome, now let's add some body content.

```html
<body>
  <h1>
    My Awesome Site
  </h1>
  <p>
    This is just an example of how I made one of my awesome sites.
  </p>
  <a href='http://google.com'>Link to Google</a>
</body>
```

Perfect, so we are first declaring a header tag that has the content "My Awesome Site" in it. We then make a paragraph tag with some other content. Finally, we add a link and set the `href` to [http://google.com](http://google.com).

So now that we got some basic HTML going, your code should look like this.

```html
<html>
  <head>
    <title>My Awesome Site</title>
    <link type='stylesheet' href='css/style.css'>
    <meta name='desc' content='This is a description for my awesome site.'>
  </head>
  <body>
    <h1>
      My Awesome Site
    </h1>
    <p>
      This is just an example of how I made one of my awesome sites.
    </p>
    <a href='http://google.com'>Link to Google</a>
  </body>
</html>
```

In this tutorial we barely scratched the surface of all the awesome and cool things you can do with HTML, stay tuned for our next tutorial where we will go into HTML in more depth and add some more cool tags.

_Thanks for reading!_

Reach out to me [@kaufmanhenry](https://twitter.com/kaufmanhenry) on Twitter or by [email](mailto:hello@henrykaufman.me).
