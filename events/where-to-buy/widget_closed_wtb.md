# Close WTB Widget

Fire whenever a user successfully closes the WTb widget. 

## Javascript Code

```js
// When:
// User successfully closes the WTB tool.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null, user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "widget_closed_wtb"
});
```

## Variable Definitions

This event has no parameters.
