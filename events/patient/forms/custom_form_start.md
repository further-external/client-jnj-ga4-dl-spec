# Form Start

Fire whenever a user starts filling out a form. 

This event is generally fired after user input in the first form field. Historically, this has been done via an HTMLElement `change` event on a form field, though it could be done via an HTMLElement `focus` event on a form field if that proves easier to implement. It should only be fired once per form. If that is too technically complicated to implement, it can be limited on the GTM side instead.

## Javascript Code

```js
// When:
// Fire when a user starts to fill out a form. Event fires after user input into the first form field 
// and should only fire once. onchange(), onfocus(), and GTM may be helpful.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'custom_form_start',
  event_data: {
    form_name: "<form_name>", // REQUIRED | string | The form name, e.g., "Digital Enrollment Form"
    step_name: "<step_name>", // REQUIRED | string | The name of the step users are interacting with, e.g., "Support Personalization"
    step_number: "<step_number>", // REQUIRED | integer | The current step number in a predefined form flow, e.g., 1
    brand: "<brand>" // REQUIRED | string | The prescription drug familiar to the patient, e.g., "darzalex"
  }
});

```

## Variable Definitions

| Field      | Type    | Required | Description                                                                 | Example                        | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|------------|---------|----------|-----------------------------------------------------------------------------|--------------------------------|---------|------------|------------|---------|---------|-------------|
| form_name  | string  | required | Used with the "form_complete" or "form_error" events, returns the form name | "Digital Enrollment Form"      |         |            |            |         |         |             |
| step_name  | string  | required | The name of the step users are interacting with                             | "Support Personalization"      |         |            |            |         |         |             |
| step_number| integer | required | Step number in a predefined form flow, should match the step shown to users | 1, 2, 3                        |         |            |            | 1       |         |             |
| brand      | string  | required | Prescription drug familiar to the patient                                   | "darzalex", "erleada"          |         |            |            |         |         |             |
