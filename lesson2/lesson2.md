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



## Modify DOM elements


