It can easily be daunting for newcomers to web development when first starting out. We often get overwhelmed with all the different technologies and terminologies used in the web, trying to make sense of it all can be frustrating. In my **What Is** series, I try to explain concepts to beginners in the simplest way I can in a form of brief and digestable articles, today we will talk about CSS and its place in the large scheme of web design!

## What is CSS?
CSS stands for Cascading Style Sheets.

It is a ***style sheet language*** used to define the presentation of a markup language document (like HTML for example). We denote a **style sheet** a style sheet language document (CSS file in this context).

If you don't know what a markup language is or what HTML is, refer to my article  ["What is HTML"](https://yamanidev.hashnode.dev/what-is-html) 

When addressing the difference between HTML and CSS in terms of role, the best example I can come up with is that of a human's body (which is our web page):

**The skeleton of the body is the HTML.**

**While the skin, hair, eyes, ears, clothes and everything that covers it, is the CSS!**

With this distinction, we call:

- HTML the ***structural layer***,

- CSS the ***presentational layer***.

Simply put:

> CSS determines what the structure (that HTML defined) is going to look like.


## Syntax

In terms of syntax, CSS is not a markup langauge like HTML or even a scripting langauge like Javascript, but a ***style sheet language*** which means that it consists of rules that selects elements in the markup language document and modify the properties that they wish to set.

What CSS code basically looks like:


![css-syntax.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1615980538790/CjdL2xYb0.png)

- ***Selector: *** is as it names implies, the selected element (or elements) on which we apply the desired rules.

- ***Property: *** is a detail about the element (for example, color of the font, boldness, size...) that we wish to change.

- ***Value: *** is the value we want the property to have (20px as the font-size for example).

## Types of CSS

We categorize CSS based on how/where we write it, and thus we have 3 types:

### 1. Inline CSS: 

We apply our style rules to the desired HTML element through the ***style attribute***. We inject our style (such a fancy name of our rules I know right) inside of our HTML element.


```
<p style="color: red">Me like banana</p>
``` 

### 2. Internal or Embedded CSS:

We insert our CSS inside of the HTML document through the ***style tag*** that we place inside of our ***head section***.


```
<head>
     <title>Example page</title>
     <style>
           p{
             color: red
           }
     </style>
</head>
``` 

### 3. External or Linked or Imported CSS:

We write our CSS code in a separate file with a .css extension (style.css in our example) and attach it to our HTML document with the ***link tag***. This is how most common CSS is written; in external files!


```
<head>
     <link rel="stylesheet" type="text/css" href="style.css" />
</head>
``` 

Breaking down the **attributes** and the **values**:

- ***rel: *** defined the relationship between the HTML document and the file defined in the **href** attribute. It takes the value **stylesheet**.

- ***type: *** specifies the type of content of the linked file (CSS file in our case), which has the value ***text/css*** .

- ***href: *** specifies the location of the linked file in perspective to the HTML document. For example, if the linked file is in the same directory (a fancy synonym of folder) the value of the ***href*** attribute simply takes the name of the linked file. If the linked file is not in the same directory as the HTML document, we define the linked file's path in regard to the HTML's, I will explain:

Say that our linked file is called **style.css** and it is inside of a directory called **styles** at the same scope of our HTML file. In order to link the style.css file, the ***href*** attribute must be ***href="styles/style.css"***.

Now if the HTML document (for whatever reason) is inside of some directory, and our linked file is outside of that directory (one level up) the ***href*** would be ***href="../style.css"***. Where the two dots (..) mean one level up our current directory.


## Why the hell is it called Cascading?


Styles are applied to the HTML in the order that they are found, ***cascading*** down from external to local styles.

What do you think happens when 2 different styles are applied to the same element? This is what we call a conflict.

The rule that gets applied (thus displayed on your browser) is the last one, which means that there is a hierarchical order according to the priority:

We denote the following order, the last one being the most important (highest priority): 

1. Browser defaults (the styles that the browser defines by default)

2. External CSS

3. Internal CSS

4. Inline CSS

For example, if we have the following code in an external CSS file


```
p{
   color: red;
}
``` 

and 


```
<p style="color: blue">Banana man</p>
``` 

The inline CSS **overrides** the external one based on the cascading feature of CSS!
And we get the text "Banana man" in blue.


### Thank you for reading!

That was a brief introduction to CSS, I hope you enjoyed the article!

Any feedback or constructive critique is warmly welcomed and appreciated, so please tell me what you think in the comments so I can better the quality ❤️.

Follow my blog and my [Twitter](https://twitter.com/yamanidev) for more!

Have a nice one!
