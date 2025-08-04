---
title: " javaScript Project 1- Counter APP"
meta_title: ""
description: "this is meta description"
date: 2025-05-02T05:00:00Z
image: "/images/JSproject1.png"
categories: ["Basic", "JavaScript"]
author: "Aditya Dhawle"
tags: ["JavaScript", "DOM"]
draft: true
---


### HTML , Structure of Your App

 1. HTML Code Block (Structure)
📝 Text Before Code:
<p>
Let’s start with the basic structure of our counter app. This HTML code sets up the layout — a title, a number display, and three buttons: increase, decrease, and reset.

💡 Tip: Mention that id attributes will be used in JavaScript to control the elements. </p>

```javascript
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Counter App</title>
    <link rel="stylesheet" href="style.css" />
</head>

<body>
    <div class="container">
        <h1>Counter App</h1>
        <div id="count">0</div>
        <div class="buttons">
            <button id="increase">➕ Increase</button>
            <button id="decrease">➖ Decrease</button>
            <button id="reset">🔄 Reset</button>
        </div>
    </div>
    <script src="counter.js"></script>
</body>

</html>

```
{{< adsense >}}

### CSS , Have some style


```javascript
body {
    font-family: Arial, sans-serif;
    background-color: #f0f4f8;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.container {
    background: white;
    padding: 30px;
    border-radius: 12px;
    text-align: center;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
}

#count {
    font-size: 4rem;
    margin: 20px 0;
    color: #333;
}

.buttons button {
    padding: 10px 20px;
    margin: 0 10px;
    font-size: 1rem;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: 0.2s ease;
}

#increase {
    background-color: #28a745;
    color: white;
}

#decrease {
    background-color: #dc3545;
    color: white;
}

#reset {
    background-color: #007bff;
    color: white;
}

button:hover {
    opacity: 0.9;
}

```

<hr>

### with html and css , your page must be looking like this

{{< image src="images/counterapp.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="image title"  webp="false" >}}

<hr>

{{< adsense >}}

### Jump to the JavaScript logic we need behind the bars



### Flowchart

{{< image src="images/jsflow1.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="image title"  webp="false" >}}

<hr>

{{< adsense >}}

```javascript
let count = 0;
const counter = document.getElementById('count');
const increase = document.getElementById('increase');


increase.addEventListener('click', () => {
    count = count + 1;
    counter.innerText = count;
});

```

{{< adsense >}}

```javascript

let count = 0;

const counter = document.getElementById('counter');
const increase = document.getElementById('increase');


increase.addEventListener('click', () => {
    count++;
    counter.innerText = count;
});

decrease.addEventListener('click', () => {
    count--;
    counter.innerText = count;
});

reset.addEventListener('click', () => {
    count = 0;
    counter.innerText = count;
});

```


