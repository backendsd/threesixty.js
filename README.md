# ThreeSixty.js

### Usage
Link from dist folder

```html
<script src="path_to_js/threesixty/dist/threesixty.js"></script>

<div class="container_class" id="threesixty">
  <img src="path_to_image" class="my_image_class" loading="lazy" >
  <img src="path_to_image" class="my_image_class" loading="lazy" >
  <img src="path_to_image" class="my_image_class" loading="lazy" >
  <img src="path_to_image" class="my_image_class" loading="lazy" >
  <img src="path_to_image" class="my_image_class" loading="lazy" >
  <img src="path_to_image" class="my_image_class" loading="lazy" >
  <img src="path_to_image" class="my_image_class" loading="lazy" >
  <img src="path_to_image" class="my_image_class" loading="lazy" >
  <img src="path_to_image" class="my_image_class" loading="lazy" >
  <img src="path_to_image" class="my_image_class" loading="lazy" >
</div>
<div class="container_class_button">
  <button id="prev">Prev</button>
  <button id="next">Next</button>
</div>
```


### Dependencies
No dependacies! Written in plain javascript.

### Example

```js
const threesixty = new ThreeSixty(document.getElementById('threesixty'), {
  imageClass: 'my_image_class',
  prev: document.getElementById('prev'),
  next: document.getElementById('next')
});

threesixty.play();
```
### Options

```js
{
  // Source image class
  imageClass: 'my_image_class', 

  // Navigation
  prev: document.getElementById('prev'), // Previous button element. Default: null
  next: document.getElementById('next'), // Next button element. Default: null
  keys: true,         // Rotate image on arrow keys. Default: true
  draggable: true,    // Rotate image by dragging. Default: true
  swipeable: true,    // Rotate image by swiping on mobile screens. Default: true
  dragTolerance: 10,  // Rotation speed when dragging. Default: 10
  swipeTolerance: 10, // Rotation speed when swiping. Default: 10
  swipeTarget: document.getElementById('wrapper'), // Element which will listen for drag/swipe events. Default: Image container

  // Rotation settings
  speed: 100,     // Rotation speed during 'play' mode. Default: 10
  inverted: false // Inverts rotation direction
}
```


### Methods

Single frame rotation:
```js
threesixty.next(); 
threesixty.prev(); 
```

Focus *n-th* frame:
```js
threesixty.goto(index);

threesixty.goto(0); // Reset position
threesixty.goto(1); // Focus 1st frame
threesixty.goto(-1); // Focus last frame
```

Image rotation:
```js
// Start rotation
threesixty.play();

// Rotate in oposite direction
threesixty.play(true);

// Stop rotation
threesixty.stop();

// Play/Stop rotation
threesixty.toggle();
```

Clean up registered events:
```js
threesixty.destroy();
```

### Licence

Licensed under the MIT license.
