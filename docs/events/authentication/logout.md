# Logout

Fire whenever a user logs out of an account.

## Javascript Code

```js
// When:
// User logs out of an account

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ user_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "logout",
  page_data: {
    user_login_state: '<user_login_state>', // optional | string | ex. anonymous
  },
  user_data: {
    user_id: "<user_id>", // recommended | string | ex. 1234567890
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|user_id|string|recommended|The user identifier|1234567890|
|user_login_state|string|contextual|Set on all events with the authentication status of the visitor.|anonymous|
