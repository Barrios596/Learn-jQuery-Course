# Basic DOM manipulation

## Insert DOM elements into a page

This allows us to:

- Add data oaded from a server
- Reflect a user's input

Before inserting elements, we need to select one or more elements. There are 3 types of insertion:

- "inside" insertion
- "outside" insertion
- "around" insertion

### Inside Insertion

```
$("p").append("The end!")
$("p").append("<button>click me!</button>")

$("p").prepend("First of all,")
```

### Outside Insertion

```
$("p").before("<h1>Heading</h1>")
$("p").after("<div>...</div>")
```

### Around Insertion

```
$("p").wrap("<div></div>")
$("p").wrap("<div><div></div></div>")
```

### Insert on selected elements

```
$("p").before($("#my-favorite-heading"))
```

### Reverse insertion methods

```
$("p").append("The end!")
$("The end!").appendTo("p") // these two are the same

.append() -> .appendTo()
.prepend() -> prependTo()
.before() -> insertBefore()
.after() -> insertAfter()
```

## Remove and replace DOM elements

### Rmove

```
$("h1").remove();
```

### Detach

Allows us to re-insert elements elsewhere

```
$("#my-heading").detach()
                .insertBefore("p:eq(3)");

```

### Empty

Deletes all the content from the selected element(s)

```
$("#my-paragraph").empty();
```

### Unwrap

Removes whatever element is surrounding the selected element(s) 

```
$("#wrapped-paragraph").unwrap()
$("#wrapped-paragraph").unwrap(".wrapper")  // jquery ensures that the wrapping element matches the selector ".wrapper"
```

### Replace with

```
$("h1").replaceWith("<h1>Hello</h1>");
$("<h1>Hello</h1>").replaceAll("h1");
```

## Modify DOM elements

### Attribute method

Get or change the value of an attribute for the selected element

```
$("#my-checkbox").attr("checked");
$("a").attr("href", "google.com");
```

### Property method

There is a 1 on 1 correspondence between Attributes and Properties

```
# These two are the same, because the ID does not change:
$("#first-name").attr("id", "hello");
$("#first-name").prop("id", "hello");

# These two may not be the same, because a value can change (the user can change an input, for instance):
$("#first-name").attr("value", "hello");
$("#first-name").prop("value", "hello");
```

### Remove Attribute and Remove Property

```
$("#first-name").removeAttr("id");
$("#first-name").removeProp("id");
```

### Modifying styles

```
$("p").css("color", "red");
```
