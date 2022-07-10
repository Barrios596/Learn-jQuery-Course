# Animations and Effects

## Hide and show elements

```
$('#my-element').hide(
    1000,   // time in miliseconds
    'swing',    // how the speed varies (another one is 'linear')
    function() {
        console.log('finished hiding!');
    }
);

$('#my-element').show(
    1000,
    'swing',
    function() {
        console.log('finished hiding!');
    }
)

$('#my-element').toggle()
```

## Animate CSS attributes

### animate function

It can only animate "numeric attributes".
```
$('#my-element').animate(
    { maxWidth: '400px' }   // camelCase, not kebab-case,
    1000,
    'swing',
    function() {...}
)
```

### delay function

```
$('#my-element')
.animate({width: '400px'})
.delay(1000)
.animate({height: '500px'});
```

### stop function

```
.stop() // pauses the animation
.stop(true) // clears all scheduled animations
.stop(true, true)   // clears all scheduled animations and jumps to the end
```

## Shortcut methods

### Fade methods

```
$('#my-element').fadeOut("slow")
$('#my-element').fadeIn(1000)
$('#my-element').fadeToggle()
$('#my-element').fadeTo("fast", 0.5)    // speed and opacity
```

### Slide methods

```
$('#my-element').slideUp("fast")
$('#my-element').slideDown()
$('#my-element').slideToggle()
```

## Get dimensions of DOM elements

These methods only work on one single element. If we select multiple elements, it will return the dimensions of the first element.

```
$('#my-element').height()   // 700
$('#my-element').width()    // 1200

$('#my-element').innerHeight()  // 800, includes the element's padding
$('#my-element').innerWidth()  //

$('#my-element').outerHeight(true)  // true: includes the element's margin
$('#my-element').outerWidth(false)  // false (default): includes the content, padding and border.
```