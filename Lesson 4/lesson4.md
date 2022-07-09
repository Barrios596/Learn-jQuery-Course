# Making network requests with AJAX

## Basic AJAX syntax

```
$.ajax({
    url: 'api.my-site.com/path',
    success: function(result) {
        // do something
    },
    error: function(jqXHR, textStatus, errorThrown) {
        // handle the error
    },
    type: 'POST',    // 'GET' if not specified
    data: JSON.stringify({ ... }),
    contentType: 'application/json', 
});
```

Shortcuts:
```
$.get(
    'api.my-site.com',
    function(result) {
        // do something
    }
)
$.post(
    'api.my-site.com',
    { a: 1, b: 2},
    function(results) {
        // do something
    }
)

$.ajax({})
 .done(...)
 .fail(...)
 .always(...)
```

## Load data from an API

