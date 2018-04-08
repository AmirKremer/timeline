# Timeline

A vanilla JavaScript horizontal / vertical timeline.

[Horizontal timeline demo](https://squarechip.github.io/timeline/#horizontal-demo) | [Vertical timeline demo](https://squarechip.github.io/timeline/#vertical-demo)


* Responsive
* Configure settings using the API or through data attributes
* Built with performance in mind
* Small file size
* Library agnostic. If jQuery is present it will register itself as a plugin
* Written in ES6 and transpiled into ES5 via Babel
<br /><br />
## Usage

**Link the required files**

```html
<script src="/dist/js/timeline.min.js"></script>
<link href="/dist/css/timeline.min.css" rel="stylesheet" />
```

<br />

**HTML markup**

```html
<div class="timeline">
    <div class="timeline__wrap">
        <div class="timeline__items">
            <div class="timeline__item">
                <div class="timeline__content">
                    Content / markup here
                </div>
            </div>
            <div class="timeline__item">
                <div class="timeline__content">
                    Content / markup here
                </div>
            </div>
            <div class="timeline__item">
                <div class="timeline__content">
                    Content / markup here
                </div>
            </div>
            <div class="timeline__item">
                <div class="timeline__content">
                    Content / markup here
                </div>
            </div>
            <div class="timeline__item">
                <div class="timeline__content">
                    Content / markup here
                </div>
            </div>
        </div>
    </div>
</div>
```

<br />

**Initialize the plugin**

JavaScript

```javascript
timeline(document.querySelectorAll('.timeline'));
```

jQuery

```javascript
jQuery('.timeline').timeline();
```
<br /><br />
## Configuration options

Using data attributes will take priority over settings via the API.

<br />

**mode**

Choose whether the timeline should be vertical or horizontal

JavaScript/jQuery
```
default: 'vertical'
options: 'vertical', 'horizontal'
```

Data attribute

```html
<div class="timeline" data-mode="horizontal">
    ...
</div>
```
<br />

**visibleItems**

If using the timeline in horizontal mode, define how many items are visible in the viewport.

JavaScript/jQuery
```
default: 3
options: integer
```

Data attribute

```html
<div class="timeline" data-visible-items="3">
    ...
</div>
```
<br />

**verticalStartPosition**

When using the timeline in vertical mode, you can choose the alignment of the first item.

JavaScript/jQuery
```
default: 'left'
options: 'left', 'right'
```


Data attribute

```html
<div class="timeline" data-vertical-start-position="right">
    ...
</div>
```

<br />

**forceVerticalWidth**

When using the timeline in horizontal mode, define at which viewport width it should revert to vertical mode

JavaScript/jQuery
```
default: 600
options: integer
```

Data attribute

```html
<div class="timeline" data-force-vertical-width="600">
    ...
</div>
```
<br />

## Examples

### Horizontal timeline
With 4 items visible in the viewport and changes into vertical mode at a 800px breakpoint

[See demo](https://squarechip.github.io/timeline/#horizontal-demo)

**JavaScript**
```
timeline(document.querySelectorAll('.timeline'), {
    mode: 'horizontal',
    visibleItems: 4,
    forceVerticalWidth: 800
});
```
<br />

**jQuery**
```
jQuery('.timeline').timeline({
    mode: 'horizontal',
    visibleItems: 4,
    forceVerticalWidth: 800
});
```
<br />

**Data attributes**
```javascript
timeline(document.querySelectorAll('.timeline'));

Or

jQuery('.timeline').timeline();
```

And

```html
<div class="timeline" data-mode="horizontal" data-visible-items="4" data-force-vertical-width="800">
    ...
</div>
```
<br /><br />
### Vertical timeline
With the first item aligned to the right

[See demo](https://squarechip.github.io/timeline/#vertical-demo)
<br />

**JavaScript**
```javascript
timeline(document.querySelectorAll('.timeline'), {
    verticalStartPosition: 'right'
});
```
<br />

**jQuery**
```javascript
jQuery('.timeline').timeline({
    verticalStartPosition: 'right'
});
```
<br />

**Data attributes**
```javascript
timeline(document.querySelectorAll('.timeline'));

Or

jQuery('.timeline').timeline();
```

And

```html
<div class="timeline" data-vertical-start-position="right">
    ...
</div>
```
<br />

## Upcoming development

* Ability to choose how many items are visible at user defined breakpoints when using the timeline in horizontal mode
* Ability to set how many items slide at a time when navigating through the horizontal timeline
* Generate a tab menu to navigate to specific items
* Ability to change classes for the HTML elements
* Add various animation options for the vertical timeline (e.g. slide up/slide in/fade in)