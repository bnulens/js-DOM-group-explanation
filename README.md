# js-DOM-group-explanation

# Javascript DOMs  
<b><em>The 'HTML DOM' is a standard for how to get, change, add, or delete HTML elements. </em></b>

---
#### Ben S.
## What is **DOM**?

The DOM (Document Object Model) is an interface that represents how your HTML and XML documents are read by the browser. It allows a language (JavaScript) to manipulate, structure, and style your website. After the browser reads your HTML document, it creates a representational tree called the Document Object Model and defines how that tree can be accessed.

![DOM tree](https://cdn-media-1.freecodecamp.org/images/3n6SPcMH0mmG6cFeB3SJBEA-9Yyfgp3xYZ7u)

In the image above, we can see the representational tree and how it is created by the browser. In this example, we have four important elements that you’re gonna see a lot:

1. **Document**: It treats all the HTML documents.
2. **Elements**: All the tags that are inside your HTML or XML turn into a DOM element.
3. **Text**: All the tags’ content.
4. **Attributes**: All the attributes from a specific HTML element. In the image, the attribute class=”hero” is an attribute from the `<p>` element.

By manipulating the DOM, you have infinite possibilities. You can create applications that update the data of the page without needing a refresh. Also, you can create applications that are customizable by the user and then change the layout of the page without a refresh. You can drag, move, and delete elements.


## DOM Methods

The HTML DOM can be accessed with JavaScript (and with other programming languages).
In the DOM, all HTML elements are defined as **objects**.
The programming interface is the properties and methods of each object.
A **property** is a value that you can get or set (like changing the content of an HTML element).
A **method** is an action you can do (like add or deleting an HTML element).

The DOM has a lot of methods. They are the connection between our nodes (elements) and events. We are going to go over a few of the most important methods. If you want to read about all of the methods click [here](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction).

---
#### Brecht
## Elements 

If we would like to manipulate HTML elements, first we have to **find** them by:  

* ID
* tag name 
* class name
* CSS selector(s)
* HTML Object Collections

  * ## by ID
    Most straightforward way of selecting elements inside the DOM.   
    Using the HTML 'ID'.

    >`var x = document.getElementById("element");`

    Returns an **object**, if not found it returns `null`.  

    ID's have to be ***unique*** however, because of the multiple features the 'ID'  
    has within the document:  
    -  As a style sheet selector.  
    -  As a target anchor for hypertext links.  
    -  As a means to reference a particular element from a script.  
    -  As the name of a declared **OBJECT** element.  
    -  For general purpose processing by user agents (e.g. for identifying   fields when extracting data from HTML pages into a database, translating HTML documents into other formats, etc.).  

  * ## by Tag name 
    **Any HTML** tag can be used to address elements inside the DOM.

    >`var x = document.getElementsByTagName("p");`  

    Notice how it is "Element(**s**)" and not "Element".   
    Small mistakes like these can result in a syntax error, with a lot of headache later on.

    You can also get an element within a selected Element:

    >`var x = document.getElementById("main");` 

    >`var y = x.getElementsByTagName("p");`

    (replacing the `document` with the ID `x` and selecting within the `x` to find another `tag`)

  * ## by Class name 
    Same thing as selecting by 'ID', `class` can be used to select all elements belonging to a particular class. 

    >`var x = document.getElementsByClassName("intro");`

    Element(**s**) NOT Element_ !

    In comparison to the 'ID' selector, the 'class' selector has less features within the DOM: 

    - As a style sheet selector (when an author wishes to assign style information to a set of elements).  
    - For general purpose processing by user agents.  

  * ## by CSS selectors
    For selecting elements that match a specified CSS selector you can use:

    >`document.querySelectorAll();`  

    >`var x = document.querySelectorAll("p.intro");`

    (selecting all the `p` within the `class` "intro")

  * ## by HTML Object Collection 
    An HTMLCollection object is an array-like list of HTML elements.  


[A list of methods and properties you can use within the DOM to select elements](https://www.w3schools.com/jsref/dom_obj_all.asp)  

## HTML DOM

"The HTML DOM allows JavaScript to change the content of HTML elements."

Dynamic changes can be made with:
- `document.write();`  
       to write directly into the **output stream**.  

- `.innerHTML`   
        to change the **content** of an element, but beware. Any HTML inside the selected element will be overwritten ! 
- you can change the `attribute` of an element by selecting it and overwriting it's property.

     ```javascript
    <!DOCTYPE html>
    <html>
         <body>

         <img id="myImage" src="smiley.gif">

        <script>
        document.getElementById("myImage").src = "landscape.jpg";  
        </script>

        </body>
     </html>
    ```
        
(This example changes the value of the src attribute of an `img` element.)

## DOM CSS
The DOM lets Javascript change the style of HTML elements.

```javascript
<html>
    <body>

    <p id="p2">Hello World!</p>

    <script>
    document.getElementById("p2").style.color = "blue";
    </script>

    <p>The paragraph above was changed by a script.</p>

    </body>
</html>
```
(This example changes the style of a `p` element)

You can even use `events` to change HTML elements when:  

- An element is clicked on.  
  (`onclick`)
- The page has loaded.  
  (`onload`)
- Input fields are changed.  
  (`onchange`)

[Basic DOM exercises from W3schools, check these out !](https://www.w3schools.com/js/exercise_js.asp?filename=exercise_js_dom_html1)

---
#### Birthe
# DOM Events  
#### (Short version. For a full version look at the events-topic of Xandra, Caroline and Ben.)  
  
Events can include anything from a click to hovering a mouse over an element to a webpage loading or being refreshed.  
The property name for event handlers always starts with ‘on’ and ends with the event appended afterwards.  
  
The most common event types:  
  
* Mouse events (MouseEvent):  
mousedown, mouseup, click, dblclick, mousemove, mouseover, mousewheel, mouseout, contextmenu.  
-Clicking a button, hover over a link,...  
  
* Touch events (TouchEvent):  
touchstart, touchmove, touchend, touchcancel.  
-Anything touchable on mobile.  
  
* Keyboard events (KeyboardEvent):  
keydown, keypress, keyup.  
-[example](https://birthelambrechts.github.io/extra-s/1.drumkit/drum.html)
  
* Form events:  
focus, blur, change, submit.  
-When a form is submitted ,when the element loses focus,...  
  
* window events:  
scroll, resize, onoffline, load, unload.  
-Script to be run when srolled, resized,... For example the offline dino game.  
  
# DOM EventListener  
  
We can tell our code to listen for an event to fire using the .addEventListener() method.  
  
```javascript  
document.getElementById('test').onclick = function(e) {  
alert('Element clicked!');  
};  
```  
To tell the code to stop listening for that event to fire, we can use the .removeEventListener() method.  
  
# DOM Navigation  
  
With the HTML DOM, you can navigate the node tree using node relationships.  
Everything in an HTML document is a node.  
New nodes can be created, and all nodes can be modified or deleted.  
  
![alt text](https://www.w3schools.com/js/pic_htmltree.gif)
  
Navigate up, down, and sideways in the DOM tree using JavaScript to access a child, parent or sibling element.  
  
### Accessing the Child Nodes  
  
The **children** of a node are the nodes that are one level below it. Any nodes beyond one level of nesting are usually referred to as descendants.  
  
You can use the `firstChild` and `lastChild` properties of the DOM node to access the first and last direct _child node_ of a node. If the node doesn't have any child element, it returns `null`.  
  
```javascript  
<div id="main">  
<h1 id="title">My Heading</h1>  
<p id="hint"><span>This is some text.</span></p>  
</div>  
  
<script>  
var main = document.getElementById("main");  
console.log(main.firstChild.nodeName);  
hint = document.getElementById("hint");  
console.log(hint.firstChild.nodeName);  
</script>  
```  
This will print #text for the first console.log and SPAN for the second one. This is because the `nodeName` is a read-only property that returns the name of the current node as a string. For example, `#text` for text node, `#comment`for comment node, `#document` for document node, and so on.  
  
To avoid the issue with `firstChild` and `` lastChild`` returning #text or #comment nodes, you could alternatively use the `firstElementChild` and `lastElementChild` properties to return only the first and last _element node_.  
```javascript  
<div id="main">  
<h1 id="title">My Heading</h1>  
<p id="hint"><span>This is some text.</span></p>  
</div>  
  
<script>  
var main = document.getElementById("main");  
// First check that the element has child nodes  
if(main.hasChildNodes()) { var nodes = main.childNodes;  
// Loop through node list and display node name  
for(var i = 0; i < nodes.length; i++) {  
alert(nodes[i].nodeName); } }  
</script>  
```  
Now this will print H1 for the first and P for the second one.  
  
### Accessing the Parent Nodes  
  
The **parent** of any node is the node that is one level above it, or closer to the `document` in the DOM hierarchy.  
  
You can use the `parentNode` property to access the parent of the specified node in the DOM tree.  
The `parentNode` will always return `null` for document node, since it doesn't have a parent.  
If you want to get only element nodes you can use the `parentElement`, like this:  
```javascript  
<div id="main">  
<h1 id="title">My Heading</h1>  
<p id="hint"><span>This is some text.</span></p>  
</div>  
<script>  
var hint = document.getElementById("hint");  
alert(hint.parentNode.nodeName); // Outputs: DIV  
hint.parentNode.style.backgroundColor = "yellow";  
</script>  
```  
### Accessing the Siblings Nodes  
  
The **siblings** of a node are any node on the same tree level in the DOM.  
Siblings do not have to be the same type of node. Text, element, and comment nodes can all be siblings.  
  
You can use the `previousSibling` and `nextSibling` properties to access the previous and next node in the DOM tree. Here's an example:  
```javascript  
<div id="main">  
<h1 id="title">My Heading</h1>  
<p id="hint"><span>This is some text.</span></p>  
</div>  
<script>  
var hint = document.getElementById("hint");  
alert(hint.previousElementSibling.nodeName); // Outputs: H1  
alert(hint.previousElementSibling.textContent); // Outputs: My Heading  
var title = document.getElementById("title");  
alert(title.nextElementSibling.nodeName); // Outputs: P  
alert(title.nextElementSibling.textContent); // Outputs: This is some text.  
</script>  
```  
Alternatively, you can use the `previousElementSibling` and `nextElementSibling` to get the previous and next sibling element skipping any whitespace text nodes. All these properties returns `null` if there is no such sibling.  
  
[Great tutorial learning the navigation and accessing the DOM-elements](https://www.digitalocean.com/community/tutorials/how-to-traverse-the-dom)

---
#### Jal 
## Nodes  
<b>"Node"</b> stands for <em>'HTML element'.</em>  
<em>Important:</em> To use a node, once it's been created, you must refer to an existing HTML element in order to link it to an existing location in the HTML itself.  
 
In the following steps we will add a <em>line of text</em> in JS to an existing HTML `<div>`:
- Step 1, we first will have to create a `<p>paragraph</p>` for our <em>text</em> to be nested in. 
- Step 2, will be the creation of the <em>text</em> itself.
- Step 3, after this we will link the <em>text</em> to our earlier created `<p>paragraph</p>`.
- Step 4, is needed to refer to an existing `<div>HTML element</div>` which we will need to place our earlier created <em>text</em> into.
- Step 5, finally, we will link our `<p>paragraph</p>`-wrapped <em>text</em> into our desired `<div>HTML element</div>` which we appointed in "Step 4".
 
#### Step 1,  creating a `<p>` element:   
```javascript
let ourParagraph = document.createElement("p");
```

#### Step 2, creating our content <em>(text)</em>:
```javascript
let ourText = document.createTextNode("This is text that will go into our paragraph.");
```

#### Step 3,  linking our content (text) to our `<p>` element:
```javascript
ourParagraph.appendChild(ourText);
```

#### Step 4,  referring to an existing HTML `<div>` element:
```javascript
let ourDesiredHTMLElement = document.getElementById("IdOfOurDiv");
```
#### Step 5, linking our created content (text) and element (< p >) to the already existing HTML element (< div >) referred to in Step 4:
```javascript
ourDesiredHTMLElement.appendChild(ourParagraph);
```
---

### Deleting an existing HTML element.
<em>Important:</em> to remove an element, you need to know and refer to the parent of said element.  

<em>In the following example we will delete the HTML element with</em> `id="ourChildParagraph"`.

<b> HTML sample: </b>
```
<div id="ourParentDiv">  
<p id="ourChildParagraph">This child must be removed!</p>   
</div>
```
- Step 1, as mentioned before, we need to first address the element's parent.
- Step 2, we will then refer to the child element we want to remove.
- Step 3, lastly we remove the child from its parent.

#### Step 1,  addressing the parent element:   
```javascript
let ourParentElement = document.getElementById("ourParentDiv");
```

#### Step 2, addressing the child element we want to remove:
```javascript
let ourChildElement = document.getElementById("ourChildParagraph");
```

#### Step 3, finally, we remove the child element:
```javascript
ourParentElement.removeChild(ourChildElement);
```
---
## Nodes: HTML Collections

<em><b>An 'HTML collection' is a list (a collection) of HTML elements.</b></em>

<b>Example 1:</b> To select all `<p>paragraph</p>` elements in an HTML file you can use the following line of code:
```javascript
let allParagraphElements = document.getElementsByTagName("p");
```
<b>Example 2:</b> Similarly, if you'd want to select all `<div>DIV</div>` elements in an HTML file you can use the code as such:
```javascript
let allDivElements = document.getElementsByTagName("div");
```
And so on.

If you'd want to access f.e. the 3rd paragraph in the <em>Example 1</em> collection, you'd do this as such:
```javascript
x = allParagraphElements[2];
```
<em><sub>! Keep in mind that such as with arrays, you start counting from 0 and <b>not</b> from 1. Hence, the 3rd item here would be connected to the number 2.
Also note that HTML collections are <b>NOT</b> arrays. They're mere lists but cannot be edited such as arrays can with f.e. `push()`, `join()`, `pop()`, etc. !</sub></em>

---
## Nodes: Node lists
<em><b>A 'Node list' is a list (a collection) of nodes that are taken from a document.</b></em>

<b>Example 1:</b> To select all `<p>paragraph</p>` elements in a document you can use the following line of code:
```javascript
let allParagraphElements = document.querySelectorAll("p");
```
<b>Example 2:</b> Similarly, if you'd want to select all `<div>DIV</div>` elements in a document you can use the code as such:
```javascript
let allDivElements = document.querySelectorAll("div");
```
And so on.

If you'd want to access f.e. the 3rd paragraph in the <em>Example 1</em> list, you'd do this as such:
```javascript
x = allParagraphElements[2];
```
<em><sub>! Keep in mind that such as with arrays, you start counting from 0 and <b>not</b> from 1. Hence, the 3rd item here would be connected to the number 2.
Also note that Node lists are <b>NOT</b> arrays. They're mere lists but cannot be edited such as arrays can with f.e. `push()`, `join()`, `pop()`, etc. !</sub></em>

---
