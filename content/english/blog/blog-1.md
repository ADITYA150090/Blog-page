---
title: "[web-dev]: Introduction to HTML, CSS & JS"
meta_title: ""
description: "this is meta description"
date: 2025-05-02T05:00:00Z
image: "/images/workshop.png"
categories: ["KDK", "web-dev"]
author: "Aditya Dhawle"
tags: ["kdkce", "Workshop"]
draft: false
---

# HTML

### What is a Markup Language?

A **markup language** is a way of writing text so that **computers can understand the structure and meaning** of the content.

It **"marks up"** plain text with **tags** that describe **how the text should appear or behave**.

### 📌 Example (Plain Text vs Markup):

Plain Text:
This is heading.
This is a paragraph
with markup (HTML):
```javascript

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

```

Here, `<h1>` and `<p>` are **markup tags**. They tell the browser:

- "Hey! This part is a heading!"
    
- "And this part is a paragraph!"

### Why use a markup language?

- To organize content
    
- To add structure (like headers, lists, links)
    
- To format the content (like bold, italic)
    
- To make content readable by browsers and other machines (like screen readers)

### Common Markup Languages:

- **HTML** – For web pages
    
- **XML** – For storing and transporting data
    
- **Markdown** – For lightweight formatting (used in README files)


## Basic Structure

```javascript

<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>
  </body>
</html>


```

ID and CLASS

```javascript

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <div id="body">
        <div class="btn">dark mode</div>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Offi</p>
    </div>

    <script src="script.js"></script>
</body>

</html>



```

Target ID and Class in CSS
```javascript
/* Target the class */
/* Base styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: gilroy;
}

html,
body {
    height: 100%;
    width: 100%;
}

#body {
    background-color: white;
    width: 100vw;
    height: 100vh;
    margin: 0%;
    padding: 0%;
}

.btn {
    height: 20px;
    width: 80px;
    background-color: aqua;
    cursor: pointer;
}
  
```



```mermaid

flowchart TD

    A[Start] --> B{Is flag equal to 1?}

    B -- Yes --> C[Set background to black]
    C --> D[Set text color to white]
    D --> E[Change button text to Light Mode]
    E --> F[Set flag to 0]
    F --> G[End]

    B -- No --> H[Set background to white]
    H --> I[Set text color to black]
    I --> J[Change button text to Dark Mode]
    J --> K[Set flag to 1]
    K --> G


```


```javascript


let flag = 1;
document.querySelector(".btn").addEventListener("click", function() {
    let B = document.querySelector("#body");
    let btn = document.querySelector(".btn");

    if (flag === 1) {
        // Switch to dark mode
        B.style.backgroundColor = "black";
        B.style.color = "white";
        btn.innerHTML = "Light Mode";
        flag = 0;
    } else {
        // Switch to light mode
        B.style.backgroundColor = "white";
        B.style.color = "black";
        btn.innerHTML = "Dark Mode";
        flag = 1;
    }
});



```

## Creative Design

Nam ut rutrum ex, venenatis sollicitudin urna. Aliquam erat volutpat. Integer eu ipsum sem. Ut bibendum lacus vestibulum maximus suscipit. Quisque vitae nibh iaculis neque blandit euismod.

> Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo vel ad consectetur ut aperiam. Itaque eligendi natus aperiam? Excepturi repellendus consequatur quibusdam optio expedita praesentium est adipisci dolorem ut eius!

Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo vel ad consectetur ut aperiam. Itaque eligendi natus aperiam? Excepturi repellendus consequatur quibusdam optio expedita praesentium est adipisci dolorem ut eius!