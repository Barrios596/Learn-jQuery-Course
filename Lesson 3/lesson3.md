# Using Event Handling

## Basic Handler syntax

### 'on' method

```
.on("event", callback);
```

```
function sayHi() {
    console.log("Hello!");
}

$("p").on("click", sayHi);
$("p").on("click", function() {
    console.log("Hello!");
});

$("p").on("click", function() {
    $(this).css("color", "red");    // 'this' represents the element, YOU HAVE TO USE THE function() syntax, no arrow functions
});

.on("mouseenter mouseleave", callback); // you can enter more that one element separated by spaces
```

### 'trigger' method

```
$("button").trigger("click");   // clicks a button programatically
$("#some-element").trigger("mouseenter");
```

### 'off' method

```
$("p").off();    // removes all handlers
$("p").off('click');    // no longer reacts to clicks

function sayHi() {
    console.log("Hello!");
}
$("p").off('click', sayHi); // remove only one function
```

## Event propagation

If an element is inside another element, the events will propagate upstream. Eg: a paragraph is inside a card, both have a handler so when you click the paragraph both handlers are activated. To prevent this, use stopPropagation:

```
$('p').on('click', function(e) {
    console.log('clicked p');
    e.stopPropagation();
});
```

## Basic Browser and Document Events

### 'ready' event

Until this event fires, it's not safe to manipulate the DOM

```
$(document).ready(function() {
    console.log("DOM is ready!");
});

$(callback);    // this also works
```

### 'resize' and 'scroll'

```
$(window).resize(function() {
    console.log("window resized!");
});

$(window).scroll(function() {
    console.log(window scrolled!);
});
```

## Mouse events

### 'click' event

### 'dblclick' event

### 'mouseenter' and 'mouseleave' events

## Keyboard events

### 'keydown' method

This one works with all keys

Only works with 'selected elements'
```
$('input').keydown(...) // this works
$('p').keydown  // doesn't work
```

### 'keyup' method

### 'keypress' method

This one only responds to alphanumeric keys

### How to know which key was pressed?

```
$('#my-element').keydown(function(event) {
    event.keyCode;  // -> 98
    event.key;  // -> "b"
})
```

## The Event Object

JQuery creates an 'event' object each time it is triggered.

```
const myEvent = jQuery.Event('myEvent');
```

### Target

The target is the element that a given event is happening to. Eg: if the user is typing into an input, the target is the input.

### pageX and pageY

Where on the page a given envent occurs. Usually helpful with mouse events.

### Timestamp

Unix timestamp of when a given event occurs. It doesn't work correctly on Firefox.

### Which

It tells us which of the possible keys caused the event.

### stopPropagation

Method to prevent a given event to move up to the upstream elements.

## Forms

### focus event

```
$('#my-input').focus(function() {
    console.log('element gained focus!');
})
```

### change event

```
$('#my-input').change(function(e) {
    cons newValue = e.target.value;
    if (newValue.length > 5) {
        $(e.target).val(newValue.substring(0, 5));
    }
})
```

### val event

```
$('#my-input').val();
$('#my-input').val("Hi!");
```

### select

It just works with the input element and the text area element

```
$('#my-input').select(function() {
    console.log(window.getSelection().toString());  // the select element does not include the selected text
})
```

### blur
The opposite of the focus method
```
$('#my-input').blur(function() {
    console.log('Element lost focus');
})
```

### submit