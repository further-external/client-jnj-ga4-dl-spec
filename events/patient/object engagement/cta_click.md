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
    step_name: "<step_name>", // REQUIRED | string | ex. "Support Personalization"
    step_number: "<step_number>", // REQUIRED | integer | ex. 1
    link_url: "<link_url>", // REQUIRED | string | ex. "undefined"
    link_text: "<link_text>", // REQUIRED | string | ex. "Learn More"
    module_name: "<module_name>", // REQUIRED | string | ex. "Product Information"
    brand: "<brand>", // REQUIRED | string | ex. "darzalex"
    person: "<person>", // REQUIRED | string | ex. "patient"
    prescription_status: "<prescription_status>", // REQUIRED | string | ex. "currently prescribed darzalex"
    condition: "<condition>", // REQUIRED | string | ex. "Moderate to Severe Plaque Psoriasis"
    pathway: "<pathway>" // REQUIRED | string | ex. "dedicatedGuide"
  }
});
```

## Variable Definitions

| Field               | Type    | Required | Description                                               | Example                               | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|---------------------|---------|----------|-----------------------------------------------------------|---------------------------------------|---------|------------|------------|---------|---------|-------------|
| step_name           | string  | required | The name of the step users are interacting with           | "Support Personalization"             |         |            |            |         |         |             |
| step_number         | integer | required | Step number in a predefined form flow                     | 1, 2, 3                               |         |            |            |         |         |             |
| link_url            | string  | required | The HREF of the link interacted with                      | "undefined"                           |         |            |            |         |         |             |
| link_text           | string  | required | The text of the link interacted with                      | "Learn More"                          |         |            |            |         |         |             |
| module_name         | string  | required | Name of content module on the site                        | "Product Information"                 |         |            |            |         |         |             |
| brand               | string  | required | Prescription drug familiar to the patient                 | "darzalex"                            |         |            |            |         |         |             |
| person              | string  | required | Persona of the user, e.g., patient or caregiver           | "patient"                             |         |            |            |         |         |             |
| prescription_status | string  | required | Current prescription status                               | "currently prescribed darzalex"       |         |            |            |         |         |             |
| condition           | string  | required | Medical condition the patient seeks help with             | "Moderate to Severe Plaque Psoriasis" |         |            |            |         |         |             |
| pathway             | string  | required | Program pathway, e.g., Full Program, Cost Support Only    | "dedicatedGuide"                      |         |            |            |         |         |             |
