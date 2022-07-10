# DOM Traversal

What are an element's children/parents/siblings/etc?

## Basic methods

```
$('.todo-list').find('li')
$('#info-div').children()
$('#my-element').parent()
$('#my-element').parents()
$('#some-heading').siblings()
$.each($('h3'), function(i, element) {
    console.log($(element).text());
})
$('input').filter(function(i, element) {
    return $(element).val().length === 0;
}).css('border', '1px solid red');
$('div').has('h3')
$('button').click(function() {
    if ($(this).is(':even')) {
        console.log("I'm even!");
    } else {
        console.log("I'm odd!");
    }
})
```