# draw.swg.js
Small pure JS SVG library

### About
This library provides simple interface for manipulating SVG elements.

### Installation

 Install `draw.swg.js` file from `src/` directory and attach it to your view file:
```html
<script src="draw.svg.js"></script>
```

 Create your `<svg>` element:

```html
<svg id="svg-id"></svg>
```

Use drawSVG to initialize it:
```js
drawSVG.init('svg-id');
```

##### That's it! Now you are ready to use all *draw.swg.js* features.

### Docs

> All code is commented and easy to understand.

To create a `<path>` element use:
```js
drawSVG.createElement('element-id').path();
```
>Every 'create' method  resets `PathHelper.itemId` property, you can change it if you want to manipulate another object.

After execution of this command your `<svg>` element will get the new empty `<path>` element in it:
```html
<path class="svg-element" id="element-id" style="stroke-width: 4px;" fill="none" stroke="green"></path>
```
Now you have object that can be manipulated by JS.

##### Low Level methods
You can now use simple pre-made method to draw lines using `PathHelper`:
```js
PathHelper.moveTo(10,10);
PathHelper.lineTo(20,10);
```
You can also use cunstructions like this one:
```js
PathHelper.moveTo(10,10).lineTo(20,10);
```
There is also a method to close your path:
```js
PathHelper.closePath();
```
The code above will create horizontal line (10px in length).(<img width=40px src="http://i.imgur.com/fQUxYFA.jpg">)
##### Pre-sets of basic figures
You can also use pre-made logic for:
<ul>
<li>Arrow</li>
<li>Rectangle(path)</li>
<li>Ellipse</li>
<li>Generatable line (used to generate long paths)</li>
</ul>
Example for Arrow:
```js
drawSVG.createElement('arrow-id').path();
drawSVG.drawObject('arrow-id').arrow(10,10,50,50); 
/* 
 You could use 'drawSVG.drawObject().arrow(10,10,50,50)'
 because create method has assigned 'PathHelper.itemId'
*/
```
<img src="http://i.imgur.com/3Zuyp5K.png">
The code above will create arrow, pointing from (10;10) to (50;50).
