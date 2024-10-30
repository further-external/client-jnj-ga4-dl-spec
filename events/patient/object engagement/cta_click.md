# Cta Click

When a user clicks a CTA, defined as oval buttons with a specific call-to-action, except for CONTINUE buttons to complete a step.

## Javascript Code

```js
// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'cta_click',
  event_data: {
    step_name: "<step_name>", // contextual | string | ex. "Support Personalization"
    step_number: "<step_number>", // contextual | integer | ex. 1
    link_url: "<link_url>", // contextual | string | ex. "undefined"
    link_text: "<link_text>", // contextual | string | ex. "Sign In"
    module_name: "<module_name>", // REQUIRED | string | ex. "Product Information"
    brand: "<brand>", // REQUIRED | string | ex. "darzalex"
    person: "<person>", // REQUIRED | string | ex. "patient"
    prescription_status: "<prescription_status>", // contextual | string | ex. "not prescribed darzalex"
    condition: "<condition>", // contextual | string | ex. "Active Psoriatic Arthritis"
    pathway: "<pathway>" // contextual | string | ex. "personalSupport"
  }
});
```

## Variable Definitions

| Field               | Type    | Required   | Description                                               | Example                               | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|---------------------|---------|------------|-----------------------------------------------------------|---------------------------------------|---------|------------|------------|---------|---------|-------------|
| step_name           | string  | contextual | The name of the step users are interacting with           | "Support Personalization"             |         |            |            |         |         |             |
| step_number         | integer | contextual | Step number in a predefined form flow                     | 1, 2, 3                               |         |            |            |         |         |             |
| link_url            | string  | contextual | The HREF of the link interacted with                               | "undefined"                   |         |            |            |         |         |             |
| link_text           | string  | contextual | The text of the link interacted with                               | "Sign In"                     |         |            |            |         |         |             |
| module_name         | string  | required   | Name of content module on the site                        | "Product Information"                 |         |            |            |         |         |             |
| brand               | string  | required   | Prescription drug familiar to the patient                          | "darzalex"                    |         |            |            |         |         |             |
| person              | string  | required   | Persona of the user, e.g., patient or caregiver                    | "patient"                     |         |            |            |         |         |             |
| prescription_status | string  | contextual | Current prescription status                                        | "not prescribed darzalex"     |         |            |            |         |         |             |
| condition           | string  | contextual | Medical condition the patient seeks help with                      | "Active Psoriatic Arthritis"  |         |            |            |         |         |             |
| pathway             | string  | contextual | Program pathway, e.g., Full Program, Cost Support Only, Guide Only | "personalSupport"             |         |            |            |         |         |             |
