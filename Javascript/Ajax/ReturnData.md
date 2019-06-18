# How to return data from async Ajax request

### First step : Pass a callback function to the Ajax function

```javascript
ajax_function( function( return_value ) {
    // do stuff with return_value
});
```

### Second step : Return the value by calling the callback function

```javascript
function ajax_function ( callback )
{
    $.ajax(
    {
        url: "ajax_landing",
        success: function(result)
        {
            callback( result );
        }
    });
}
```
