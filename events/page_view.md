# Page View

Fire whenever a user loads in a new page, whether that is done synchronously or asynchronously.

This event should be the first pushed into the data layer on each page. Given many 3rd party scripts push events to the data layer, this event push should be placed in the page `<head>` and should be the first `<script>` tag on the page to ensure it is the first event.

There is no longer a concept of virtual page view, so this event should be fired whenever a virtual page view would have been fired in the past, such as when a new screen is loaded asyncronously within an angular, react, or vue app/embed.

## Javascript Code

```js
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  event: 'page_view',
  brand: 'brand',
  country: 'country',
  language: 'language',
  page_title: 'page_title',
  page_type: 'page_type',
  region: 'region',
  site_section: 'site_section',
  site_section2: 'site_section2',
  site_section3: 'site_section3',
  user_id: 'user_id',
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|brand|string|required|The brand the site is associated with.|neutrogena|
|country|string|required|The country the site is associated with.|us|
|language|string|required|The language of the current page, usually pulled from the `<html>` tag `lang` attribute.|en|
|page_location|string|required|The url of the page currently being viewed.|https://www.neutrogena.com|
|page_referrer|string|required|The previous page URL, generally available in `document.referrer`|https://www.neutrogena.com|
|page_title|string|required|The title of the page currently being viewed, generally available in `<title>`.|https://www.neutrogena.com|
|region|string|required|The region the site is associated with.|EMEA|
|site_section|string|recommended|The section of the site that the current page resides in.|products|
|user_id|string|contextual|The id of the user currently logged in to the site, if the site offers authentication and the user is authenticated.|123456|

## Notes
- This is the first version with baseline parameters. There will be many additional parameters coming over time as more and more sites are added with differing requirements.