# JavaScript

## Where did it come from?

In the early 1990's, the Netscape Navigator web browser dominated the browser market. The founder of Netscape believed that HTML needed a glue language that was easy to use by web designers. For this purpose, Netscape hired Brandon Ike in 1995 to integrate the scheme programming language into Netscape Navigator. He created a prototype of what he called Live Script in 1995. Later in the year, it was renamed and released as JavaScript.

## What is it?

JavaScript is a high-level, interpreted programming language. Being an interpreted langauge means that you don't have to compile the code before you execute it. It is interpreted at runtime. Being a high-level language means that it is a high abstraction from the computer. In contrast, the C programming language is a low-level language that gives you more control over things like memory management.

JavaScript != Java!

JavaScript can be used the manipulate HTML, the browser, and to talk to servers. In the following example, we can see how writing "in-line" JavaScript is possible:

```html
<body>
    <button type="button"
            onclick="document.getElementById('demo').innerHTML = Date()">
        See the date
    </button>
    <p id="demo"></p>
</body>
```

The code above will display a button that has the text "See the date" on it. When the user clicks the button, it will select the element with the id "demo" and then set the inner HTML of that to the complete current date and time with the call to Date().

Let's look an another way to write the above code, in a full HTML document:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My HTML page!</title>
    <script>
        function ShowDate() {
            document.getElementById('demo').innerHTML = Date();
        }
    </script>
</head>
<body>
    <button type="button"
            onclick="ShowDate();">
        See the date
    <button>
    <p id="demo"></p>
</body>
</html>
```

This is the exact same HTML and JavaScript code. The only difference is that we moved the JavaScript code into a function within a script tag in the head tag. This makes it reusable on other buttons that we may wish to implement.

Let's break it out further and see another way we could implement this functionality:

HTML Document
```html
<!DOCTYPE html>
<html>
<head>
    <title>My HTML page!</title>
</head>
<body>
    <button type="button"
            onclick="ShowDate();">
        See the date
    <button>
    <p id="demo"></p>

<script src="ScriptFile.js"></script>

</body>
</html>
```

ScriptFile.js
```JavaScript
function ShowDate() {
    document.getElementById('demo')
            .innerHTML = Date();
}
```

This is the same HTML as before, except that we extracted out the ShowDate() function into its own JavaScript file. We reference the JavaScript file from within the HTML document. By doing this, we allow it to be reusable across multiple HTML documents.

We can also use JavaScript to interact with the web broswer. The following example opens up a promt from the window object and asks for a name, which it then stores in the name object. If there was a name entered, the text variable gets the value of "Hello" with the entered name. Finally, it is displaued in the "name" element.

```JavaScript
<script>

function PromptUser() {
    var txt;
    var name = window.prompt("Enter your name");
    if (name != null || name != "") {
        txt = "Hello " + name;
    }

    document.getElementById("name").innerHTML = txt;
}

</script>
```

We can also make AJAX calls. Using AJAX you can do all sorts of interactive and advanced things in the browser without having to refresh the page. AJAX stands for Asynchronous JavaScript and XML. In your web browser, you may have loaded your HTML document and some JavaScript from an external .js file. From the browser you might have the need to call an external API which returns a .txt file to be viewed in the browser. The point is that you can call server-side code without the need to refresh your browser. Let's take a look at an axample of AJAX:

```html
<!DOCTYPE html>
<html>
<body>

<div id="demo">
<h2>My Ajax Page</h2>
<button type="button" onclick="loadDoc()">Change Content</button>
</div>

<script>
function loadDoc() {
    var xhttp = new XMLHttpRequest();
    xhttp.onreadystatechange = function() {
        if (this.readState == 4 && this.status == 200) {
            document.getElementById("demo").innerHTML =
            this.responseText;
        }
    };
    xhttp.open("GET", "ajax_info.txt", true);
    xhttp.send();
}
</script>

</body>
</html>
```

In the code above, a button will be displayed that, when clicked, will call the loadDoc() JavaScript function. This function uses Ajax. It uses the XMLHttpRequest object in JavaScript. You can use this object to make calls to servers that are somewhere else, without having to refresh the page. This is the essence of the Ajax technique.

In the code above, we attach the inner function to the xhttp object. The funtion fires when the state of the object changes, which is when a call is made to an external server. The inner function also updates the innerHTML of the div with the id of "demo". It gets the text to put in the div from a document that it gets from calling the xhttp.open() function. We could have also used any url in place of the .txt file.

In short, we can use the Ajax Technique to call API's and work with results from external calls without needing to refresh the web page.

Here are a list of JavaScript libraries that you may want to take a look at for next steps:

* JQuery
* Dojo Toolkit
* Prototype.js
* Bootstrap
* Velocity.js
* D3.js

Some more advanced libraries and frameworks include:

* Angular
* Backbone.js
* Ember.js
* Knockout
* Node.js
* Vue.js
* React
* TypeScript