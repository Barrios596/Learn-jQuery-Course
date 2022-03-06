# jQuery

## Why use jQuery?

*"Write less, do more"* - jQuery

Without JQuery, code to do simple tasks is usually verbose:

- Manipulating the DOM
- Adding/Removing Styles
- Making Network Requests
- Document Traversal
- Etc

## Selecting elements in jQuery

Returns a jQuery object, with all DOM elements that match the selector
```
jQuery("selector")
```

A shorter way of using it is just a dollar sign instead of the "jQuery"
```
$("selector")
```

There are many similarities between CSS selectors and jQuery selector strings

### 'All' selector
```
$("*")
```
- Selects **all** elements in the page
- It usually is very slow, not recommended.

### The element selector
```
$("h1")
$("p")
$("button")
```
- Select all elements that match the element in the string that we pass

### Class selector
```
$(".my-class")
```
- Select all elements that match with the class name in the string that we pass
- Can also be mixed with the element selector to select all elements with certain class
```
$("p.my-class")
```

### ID Selector
```
$("#id")
```
- Select all elements with a specific id

### Multiple selector
```
$("p, .my-class, #my-favorite-element")
```

### Complex selectors

There are man times where we need our selections to be more specific

```
:first
:last
:eq(n)
:gt(x)
:lt(x)
:even
:odd
:contains()
:not
```

```
$("p:eq(3)")
$("h1:gt(2)")
$("table td:even")
$("p:contains('Hello')")
$("p:not(.selected)")
$("p:not(:eq(2))")
```

### Element atributes

- Sometimes we need to select elements by the value of their atributes
- Attribute selectors allow us to select alements based on the values of their attributes
```
[attr="value"]
[attr!="value"]
[attr]
[attr*="value"] // contains "value"
[attr^="value"] // starts with "value"
[attr$="value"] // finishes with "value"
[attr1="value1][attr2="value2"]

$('a[href="google.com"]')
$('button[onClick]')
$('a[href*="google.com"')
$('a[href^="https"]')
$('a[href$=".html"]')
$('input[type="text"][onchange]')
$('input[type="text"], input[onchange]') // this is an OR
$('[onChange]') // all elements with attribute 'onChange', regardless of the element type 
```
