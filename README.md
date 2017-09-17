# cubic-scroll

Extremely lightweight modern implementation of scroll with easing effect based on cubic function and rendering based on requestAnimationFrame

## Installation
Using `npm`
```sh
$ npm install cubic-scroll --save-dev 
```
or `yarn`
```sh
$ yarn add cubic-scroll
```

## Basic usage
When there is scrollable view on the page
```html
<div class="menu">
  <a href="#section-0"
    onclick="fluidScroll.handleLinkClick(event, {scrollView: document.querySelector('.content')})">Link 0</a>
  <a href="#section-1"
    onclick="fluidScroll.handleLinkClick(event, {scrollView: document.querySelector('.content')})">Link 1</a>
  <a href="#section-2"
    onclick="fluidScroll.handleLinkClick(event, {scrollView: document.querySelector('.content')})">Link 2</a>
</div>
<div class="content">
  <div id="section-0">Section 0</div>
  <div id="section-1">Section 1</div>
  <div id="section-2">Section 2</div>
</div>
```
[Here you can find full example of scrollable view](https://github.com/jolly-roger/cubic-scroll/blob/master/tests/pages/scroll-view.html),
and for case when whole page is scrollable see [Scrollable page](https://github.com/jolly-roger/cubic-scroll/blob/master/tests/pages/document.html)

## API

### handleLinkClick
Scroll to anchor, that is linked to event target. It has following parameters:
* **e** - DOM click event
* **opts** - configuration options
  * **scrollView** - scrollable view on the page, by default document body is used
  * **marginTop** - margin from the top of the scroll view, it is useful if you have sticky top menu
  * **accelerateFactor** - this parameter influences on the initial speed of scroll according to the formula `speed = cbrt(y * accelerateFactor)`

### scrollTo
Scroll to passed anchor on the page. It has following parameters:
* **targetEl** - Target anchor DOM element
* **opts** - options, the same as for `handleLinkClick`