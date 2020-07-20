# Cascading Style Sheets (CSS)

## Where did it come from?

In 1994, CCS was proposed as a stylesheet language. Other languages were also being proposed a tthe time. However, the World Wide Web Condortium, who were already working on the HTML standard, added CSS to the deliverables of the HTML working group. This resulted in the official recommendation of the CCS level 1 standard in 1996. Such a recommendation is considerd a specification that all web broswers should adapt to handle CCS.

## What is it?

CSS is a style sheet language used for describing the presentation of a document written in a markup language.

We can link to an external stylesheet by using the following tag in the <head> tag of our HTML document:

```
<link rel="stylesheet" type="text/css" href="StyleSheet.css">
```

In the style sheet, we will define the styles that we want to use. It's contents might look something like this:

```
div {
    color: blue;
}

.italic {
    font-style: italic;
}
```

By extracting out the ccs into it's own .css page, we can reuse the styles in multiple HTML documents.

As we can see above, css consists of properties and attributes like the color being blue and the text being italic. CSS can indicate which element these properties should be applied. We do this by using selectors. For example above, the div property will be applied to all of the dev elements in an html page.

In the following example, the ccs will be applied to all of the elements that have a class attribute set to class1:

```
.class1 {
    color: blue;
}
```

In the next example, we are specifying an "id". The css will be applied to all html elements that have an id of para1.

```
#para1 {
    color: blue;
}
```

You can also nest things as follows. This css will be applied to all paragraph elements that have a div element as their parent:

```
div p {
    text-align: enter;
    color: red;
}
```

The following example shows how we can apply css to multiple elements on an html page (h1, h2 and p elements will use the ccs):

```
h1, h2, p {
    text-align: center;
    color: red;
}
```

CSS is called cascading because properties are applied based on priority. Order of priority is "selector", "class" and then "id". This means that if an element has attributes from all three, and say background-color is being specified in all three, then only the background-color specified in the "id" section will be applied. It will overwrite the background-color specified in class. In the same way, class would override the background-color in the selector if it is not specified in the id. Another way to override this further is to use the !important value as shown below:

```
.specific {
    boarder: none !important;
}
```

There are some advanced capabilities of css. An exmaple is as follows:

```
@media screen and (min-width: 480px) {
    body {
        background-color: lightgreen;
    }
}
```

In the example above, we are telling the web browser that whenever we are displaying html on the screen, as apposed to when we print a page, and when the screen has a minimum width of 480 pixels, we want the body element to have the background color of lightgreen.

This allows for a more responsive webpage, for instance if our webpage is being displayed on a smart phone vs a laptop.

One of the most popular libraries for css is called "bootstrap". It allows us to easily creat responsive web pages.