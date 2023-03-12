# [Simple but smart SLIDER](https://lebryere.github.io/simple_but_smart_slider/)

## Browser Support

![Chrome](https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png) | ![Edge](https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png) | ![Firefox](https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png) | ![Safari](https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png) | ![Opera](https://raw.githubusercontent.com/alrra/browser-logos/master/src/opera/opera_48x48.png) | ![Samsung Internet](https://raw.githubusercontent.com/alrra/browser-logos/master/src/samsung-internet/samsung-internet_48x48.png)
--- | --- | --- | --- | --- | --- |
88+ ✔ | 88+ ✔ | 84+ ✔ | 14+ ✔ | 75+ ✔ | 15+ ✔ |

## Preview

[![Resume Preview](https://github.com/LeBryere/simple_but_smart_slider/blob/master/preview.png)](https://lebryere.github.io/simple_but_smart_slider/)

**[View Live Preview](https://lebryere.github.io/simple_but_smart_slider/)**

## Status

[![GitHub license](https://img.shields.io/badge/license-MIT-green?&style=plastic)](https://github.com/LeBryere/simple_but_smart_slider/blob/master/LICENSE.txt)

## Usage

### Basic Inspiration

The general function of this code is to create a postcard effect in which the elements of a list can be navigated by paging or the system automatically advances through the list. The code includes the following:

* Selects and stores the list elements in the "items" variable.
* Stores the current element index in the "current" variable.
* The "autoUpdate" variable indicates whether the system pages automatically or not.
* The "timeTrans" variable stores the time used to perform automatic paging.
* Generates a "nav" element in the code that contains navigation arrows, a counter, a previous button, and a next button.
* The "counter" element displays the number of list items and the current element index.
* Assigns the appropriate class names to the list elements corresponding to the "items".
* Sets the "autoUpdate" variable to automatically page or not when the mouse enters or exits the postcard.
* The "navigate" function navigates to the previous or next element and updates the counter with the current element index.
* Calls the "navigate" function when clicking the previous or next button.
* In addition to clicking on list items or previous/next buttons, the left and right arrow keys on the keyboard can also be used for navigation.
* Touch support is set for the "item" element, where swiping left or right on the screen navigates through the elements.
* The code calls the "init" function on every element with the ".cd-slider" class, which initiates all functions.

Overall, the code is a simple but effective way to make pages more interactive and catch visitors' attention.

### Variables
```css
html{
   background-color: #222;
}
```
```js
<script>
   // We set the initial values.
	current = 0,
	autoUpdate = true,
	timeTrans = 5000;
</script>
```
### A little more detail

At the beginning of the function definition, we define an init() function that expects an item parameter. The function first selects all li elements within the item and sets some variables. These include the current variable that contains the current slide, the autoUpdate variable that holds a true value if automatic update is enabled, and a timeTrans variable that determines the interval for automatic update.

Next, we create a navigation menu that contains two buttons (prevbtn, nextbtn) and a counter. We add the menu to the item if there is more than one element. We set the current slide as the current class, and if there is more than one element, we set the last element as the prev_slide class.

Then, we define a navigate() function that performs navigation in the specified direction. We remove the current class of the current slide and determine the next or previous slide depending on the direction. Then, we set the appropriate classes for the elements and update the counter.

Next, we add the event handlers. We add the mouseenter and mouseleave event handlers to the item to stop automatic update when the mouse enters the element and restart it when the mouse leaves the element. The autoUpdate variable is true by default, and if automatic update is enabled, we set the timer with the setInterval() function, which calls the navigate() function at the specified interval.

We add event handlers for the prevbtn and nextbtn buttons, which perform navigation in the appropriate direction. We add a keyboard event handler that allows the user to navigate using the left and right arrows. Finally, we add touch event handlers.

Then, in the code snippet, we define the navigate function that is responsible for navigation. The function decides whether to flip left or right based on the value of the dir variable passed as a parameter. It also updates the value of the current variable accordingly. It sets the className values of the items in the list appropriately and updates the counter value.

Next, we add event handlers for mouse movement and touch screen events. When pointing to the item element, we set the value of the autoUpdate variable to false, so automatic flipping stops. When the cursor is removed, the autoUpdate value returns to true, and automatic flipping continues.

Then, we set up the timer responsible for automatic flipping, which navigates between slides according to the value of the timeTrans variable. When clicking on the prevbtn and nextbtn buttons, we call the navigate function, and we also handle navigation from the keyboard.

Finally, we add event handlers for touch screen devices, which respond to swiping left and right and navigate between slides accordingly.

Finally, the function calls the init function for all elements with the cd-slider class to initialize the slideshow on all appropriate elements.
```
 
```

## Copyright and License

Copyright 2023 Lebryere. Code released under the [MIT](https://github.com/LeBryere/simple_but_smart_slider/blob/master/LICENSE.txt) license.



