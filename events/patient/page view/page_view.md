# Page View

Fire whenever a user loads in a new page, whether that is done synchronously or asynchronously.

This event should be the first pushed into the data layer on each page. Given many 3rd party scripts push events to the data layer, this event push should be placed in the page `<head>` and should be the first `<script>` tag on the page to ensure it is the first event.

There is no longer a concept of virtual page view, so this event should be fired whenever a virtual page view would have been fired in the past, such as when a new screen is loaded asyncronously within an angular, react, or vue app/embed.

## Javascript Code

```js
// When:
// User loads a new page (synchronously or asynchronously)
// Should be the first push into dataLayer, placed in the <head> and ideally first <script> on page.

// Code
window.dataLayer = window.dataLayer || [];
dataLayer.push({ page_data: null, user_data: null });  // Clear the previous attributes.
dataLayer.push({
  event: 'page_view',
  page_data: {
    page_name: 'registration', // REQUIRED | string | ex. registration
    page_category: 'sign_up', // REQUIRED | string | ex. sign_up
    page_location: 'https://janssencarepath--sit.sandbox.my.site.com/JanssenPatient/darzalex-withme/account/sign-up', // REQUIRED | string | ex. https://example.com
    page_title: 'One Program', // REQUIRED | string | ex. One Program
    page_referrer: 'https://janssencarepath--sit.sandbox.my.site.com/', // REQUIRED | string | ex. https://example.com
    page_path: '/JanssenPatient/darzalex-withme/account/sign-up', // REQUIRED | string | ex. /path/to/page
    brand: 'darzalex', // REQUIRED | string | ex. darzalex
    content_type: 'user_registration', // REQUIRED | string | ex. user_registration
    user_id: 'undefined', // OPTIONAL | string | ex. 12345
    user_login_state: 'Guest user', // OPTIONAL | string | ex. Guest user
  }
});

```
## Variable Definitions

| Field              | Type    | Required | Description                                                                         | Example                                                                                       | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|--------------------|---------|----------|-------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|---------|------------|------------|---------|---------|-------------|
| page_name          | string  | required | The name of the current page.                                                      | registration                                                                                 |         |            |            |         |         |             |
| page_category      | string  | required | Used for grouping pages (or screens) into high-level categories.                   | sign_up                                                                                      |         |            |            |         |         |             |
| page_location      | string  | required | The full URL of the page currently being viewed.                                   | https://janssencarepath--sit.sandbox.my.site.com/JanssenPatient/darzalex-withme/account/sign-up |         |            |            |         |         |             |
| page_title         | string  | required | The title of the page currently being viewed, generally available in `<title>`.   | One Program                                                                                  |         |            |            |         |         |             |
| page_referrer      | string  | required | The previous page URL, generally available in `document.referrer`.                 | https://janssencarepath--sit.sandbox.my.site.com/                                          |         |            |            |         |         |             |
| page_path          | string  | required | Page path without query parameters.                                                 | /JanssenPatient/darzalex-withme/account/sign-up                                             |         |            |            |         |         |             |
| brand              | string  | required | Prescription drug that patients are familiar with.                                  | darzalex                                                                                     |         |            |            |         |         |             |
| content_type       | string  | required | Additional content breakout.                                                         | user_registration                                                                            |         |            |            |         |         |             |
| user_id            | string  | optional | A unique identifier that is consistent across browsers/devices.                     | 465465465                                                                                     |         |            |            |         |         |             |
| user_login_state   | string  | optional | Set on all events with the authentication status of the visitor.                   | Guest user                                                                                   |         |            |            |         |         |             |

