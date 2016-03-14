#Animation in JQuery

##Objectives
* Understand the jQuery Animation Process
* Use the `animate()` method to animate
* Explore and use animation shortcut methods

So far we've used the jQuery library to manipulate elements in the DOM. We've also figured out how jQuery helps our page respond to user events with even listeners. Another big advantage of the jQuery library is how easy it is to add animations to a page by using some of jQuerys built-in methods.

##Animation with jQuery and CSS
One of the cooler features of jQuery is animation. First, selectors are using  to indicate which DOM elements to animate. A target CSS style is set. jQuery automatically calculates the intermediate styles at each millisecond to make sure the selected elements transform gradually from their original style.

## Animation using the animate() Method
The animate() method is the most flexible method. The full syntax for the animate() method is below:

`$(selector).animate({params},speed,callback);`

* *params* - defines the CSS properties to be animated, must be numerical properties
* *speed* (optional) - specifies the duration of the effect "slow", "fast", or milliseconds
* *callback* (optional) - the function to be executed after the animation completes.

Here's an example:
```js
$('p').animate(
    {fontSize: 24},
    1500
)
```
Here we are changing the style of each paragraph to a font size of 24 (the params) over a period of 1500 ms (the speed). Note that as a parameter of animate(), the CSS properties must be camelCase (fontSize instead of font-size)

You can include multiple CSS properties separated with commas.
```js
$("#cat").click(function(){
    $("#cat").animate({
                       height: 200,
                       width: 200
                })
              });
```

###Changing Position and Relative Values
Remember, the CSS  position default for all elements is static. Therefore, any jQuery animation that moves an object will not work unless you set the CSS position to one of the other values: relative, absolute or fixed.

To move an element left, right up and down, the simplest way is by changing either the top, bottom, left or right properties. These can be absolute or relative

```javascript
$("button").click(function(){
        $("#img1").animate({top: '200px'}, "fast");
        $("#img2").animate({left: '+=20px'}, "slow");
    });

```

In the above function, the click of the button triggers two events. The element with the id #img1 moves so that it's top edge is 200px below it's nearest ancestor. The element with the id #img2 moves so that it's left edge is 20px further right than it used to be.

## Animation Shortcuts
There are also some convenient shortcut methods for common animations developers use all the time:
* .slideUp()/ .slideDown() - hide an element that hides the element via sliding
* .fadeIn()/.fadeOut() - show/remove an element with a slow fade


Animation powers a multitude of web experiences - when a page has satisfying button clicks, when elements fade or slide (or both!) nicely onto and off the page - all excellent animation. Animation can be bad too - when the sliding is too slow, or the fades and slides in and out look cartoonish and silly.

##Resources

As with color, font, position, whitespace, and design generally, there is far more depth to animation than we are going to cover. You can check out [this tutorial](http://www.sitepoint.com/guide-jquery-animate-method/) to learn more. As always, getting good takes practice.

Check the [documentation](https://api.jquery.com/category/effects/) for more examples and explanations.
