---
title: "HTML Basics: Building Blocks of Every Website"
meta_title: ""
description: "this is meta description"
date: 2025-05-02T05:00:00Z
image: "/images/1.png"
categories: ["Basic", "web-dev"]
author: "Aditya Dhawle"
tags: ["nextjs", "tailwind"]
draft: false
---



### HTML Basics – Your First Step into Web Development

 ## Introduction
So you’ve heard of HTML, but what the heck is it really? Is it hard? Do you need to know everything about it?
Spoiler: Nope.

 ## What is HTML?
HTML stands for HyperText Markup Language.
It’s not a programming language — it’s a markup language, which means it tells the browser how to structure content.

Here’s the skeleton of every HTML page:
```python

<!DOCTYPE html>
<html>
  <head>
    <title>My First Web Page</title>
  </head>
  <body>
    <h1>Hello, world!</h1>
    <p>This is my first web page using HTML.</p>
  </body>
</html>


```
**Boom. That’s your first program. You just told your computer to say something. You’re already winning.**


### Let’s break it down:
- <!DOCTYPE html>: Tells the browser you’re using HTML5.
- <html>: Wraps your entire webpage.
- <head>: Stuff like title and meta data (not visible on the page).
- <body>: The visible stuff like headings, paragraphs, buttons, images, etc.


<hr>

### Tables

| Tables        |      Are      |
| ------------- | :-----------: |
| h1 to h6   | 	Headings (big to small) |
| p         |  	Paragraph   |
| a         |  Anchor tag (links)   |
| img  | display images	 |
| ul ol li      |  Lists (unordered/ordered)  |
| br         |  Line break   |
|div   | 	Division (for layout/structure)|


<hr>

## Quick Project Idea
Try writing this code and saving it as index.html:

```python
<!DOCTYPE html>
<html>
  <head>
    <title>About Me</title>
  </head>
  <body>
    <h1>Hi, I'm Aditya!</h1>
    <p>I’m learning HTML and this is my very first webpage.</p>
    <p>Here's a list of things I like:</p>
    <ul>
      <li>Chess</li>
      <li>Programming</li>
      <li>Astronomy</li>
    </ul>
  </body>
</html>


```
<p>Now open it in your browser. Boom. You’ve built a page!</p>

{{< notice "🎯 Final Thoughts" >}}
HTML is your starting point. Learn the basics, build something small. Don’t aim to memorize every tag — just enough to get things rolling.

And remember — you only need that 20% that helps you move forward.
{{< /notice >}}
