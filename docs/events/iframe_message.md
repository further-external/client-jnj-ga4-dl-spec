# iFrame message

Fire whenever an iframe emits a message using the `window.postMessage` method. 

This will be automatically collected and fired through GTM for now, but the HTML data attributes should still be added if possible to help with identification.

## HTML Data Attributes

```html
<iframe src="<page_location>"
  data-layer-category="<category>"
  data-layer-category2="<category2>"
  data-layer-identifier="<identifier>"
  data-layer-name="<name>"
>
```

## Javascript Code

```js
// When:
// Iframe emits a message using window.postMessage method

// Code
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'iframe_post_message',
  event_data: {
    category: "<category>", // recommended | string | ex. audio, where to buy, video
    category2: "<category2>", // optional | string | ex. audio, where to buy, video
    data: "<data>", // REQUIRED | variable | ex. {event: 'play', videoName: 'my video', videoProvider: 'vimeo'}
    html_classes: "<classes>", // optional | string | ex. audio-embed
    html_element: "<element>", // REQUIRED | HTMLIFrameElement | ex. <iframe src="sample.com/iframe" ...>
    html_id: "<id>", // optional | string | ex. hero-video
    identifier: "<identifier>", // optional | string | ex. vidyard-video-embed
    name: "<name>", // optional | string | ex. vidyard video embed
    page_hostname: "<page_hostname>", // REQUIRED | string | ex. vimeo.com
    page_location: "<page_location>", // REQUIRED | string | ex. https://www.example.com
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|category|string|recommended|A category added to the iframe via data attributes that can be used to represent what type of component/tool/widget is embedded via the iframe|audio, where to buy, video|
|category2|string|contextual|Categories 2 - 5 can be used to further categorize the iframe|audio, where to buy, video|
|data|variable|required|The data payload sent from the iframe|`{event: 'play', videoName: 'this is a video', videoProvider: 'vimeo'}`|
|html_classes|string|contextual|The iFrame CSS classes.|`audio-embed`|
|html_element|[HTMLIFrameElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)|required|The iFrame HTML element.|`<iframe src="neutrogena.com/iframe" ...>`|
|html_id|string|contextual|The iFrame HTML ID attribute.|`hero-video`|
|identifier|string|contextual|An ID added to the iframe via data attributes that can be used to identify which iframe sent the message|`vidyard-video-embed`|
|name|string|contextual|A name added to the iframe via data attributes that can be used to identify which iframe sent the message|`vidyard video embed`|
|page_hostname|string|required|The hostname of the iFrame source.|`vimeo.com`|
|page_location|string|required|The full URL of the iFrame source.|`where-to-buy.co/example`|
