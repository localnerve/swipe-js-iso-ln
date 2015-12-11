# Swipe

> swipe-js-iso-ln is a fork of `swipe-js-iso` by dmitri.voronianski@gmail.com, which itself is a fork of the original [Swipe](https://github.com/thebird/Swipe) by Brad Birdsall.

_Hint: Use this with [react-swipe](https://github.com/localnerve/react-swipe) component and [React](https://facebook.github.io/react) for isomorphic/universal apps._

## Why This Fork Exists
This fork contains bug fixes and updates, because the `swipe-js-iso` repo by [voronianski](https://github.com/voronianski) was not found.

Effort was put into maintaining this because it is:
* simple
* small
* no-dependencies

Maybe the smallest swipe library around (AFAICT). Works great with [react-swipe](https://github.com/localnerve/react-swipe).

This library is ~5k minified.

## Where This Fork Is Used
This fork, used with [react-swipe](https://github.com/localnerve/react-swipe) can be seen in action in this [live example](http://flux-react-example.herokuapp.com).

-------------------------------------------------------
## Usage

Swipe only needs to follow a simple pattern. Here is an example:

``` html
<div id='slider' class='swipe'>
  <div class='swipe-wrap'>
    <div></div>
    <div></div>
    <div></div>
  </div>
</div>
```

Above is the initial required structure– a series of elements wrapped in two containers. Place any content you want within the items. The containing div will need to be passed to the Swipe function like so:

``` js
window.mySwipe = Swipe(document.getElementById('slider'));
```

I always place this at the bottom of the page, externally, to verify the page is ready.

Also Swipe needs just a few styles added to your stylesheet:

``` css
.swipe {
  overflow: hidden;
  visibility: hidden;
  position: relative;
}
.swipe-wrap {
  overflow: hidden;
  position: relative;
}
.swipe-wrap > div {
  float:left;
  width:100%;
  position: relative;
}
```

## Config Options

Swipe can take an optional second parameter– an object of key/value settings:

- **startSlide** Integer *(default:0)* - index position Swipe should start at

-	**speed** Integer *(default:300)* - speed of prev and next transitions in milliseconds.

- **auto** Integer - begin with auto slideshow (time in milliseconds between slides)

- **continuous** Boolean *(default:true)* - create an infinite feel with no endpoints

- **disableScroll** Boolean *(default:false)* - stop any touches on this container from scrolling the page

- **stopPropagation** Boolean *(default:false)* - stop event propagation

-	**callback** Function - runs at slide change.

- **transitionEnd** Function - runs at the end slide transition.

### Example

``` js

window.mySwipe = new Swipe(document.getElementById('slider'), {
  startSlide: 2,
  speed: 400,
  auto: 3000,
  continuous: true,
  disableScroll: false,
  stopPropagation: false,
  callback: function(index, elem) {},
  transitionEnd: function(index, elem) {}
});

```

## Swipe API

Swipe exposes a few functions that can be useful for script control of your slider.

`prev()` slide to prev

`next()` slide to next

`getPos()` returns current slide index position

`getNumSlides()` returns the total amount of slides

`slide(index, duration)` slide to set index position (duration: speed of transition in milliseconds)

## Browser Support

Swipe is now compatible with all browsers, including IE7+. Swipe works best on devices that support CSS transforms and touch, but can be used without these as well. A few helper methods determine touch and CSS transition support and choose the proper animation methods accordingly.

## Who's using Swipe

(taken from the original readme)
* cnn
* airbnb
* nhl
* htc
* thinkgeek
* snapguide

## License

Copyright (c) 2013-2015 Brad Birdsall Licensed under the [The MIT License (MIT)](http://opensource.org/licenses/MIT).
