## Element Click

When a user clicks a element, other than defined oval buttons with a specific call-to-action, such as a radio or checkbox object.

## Javascript Code

```js

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'element_click',
  event_data: {
    link_url: "<link_url>", // REQUIRED | string | ex. "undefined"
    link_text: "<link_text>", // REQUIRED | string | ex. "Submit"
    element_name: "<element_name>", // REQUIRED | string | ex. "Email Field"
    module_name: "<module_name>", // REQUIRED | string | ex. "Contact Form"
    brand: "<brand>", // REQUIRED | string | ex. "darzalex"
    person: "<person>", // REQUIRED | string | ex. "patient"
    prescription_status: "<prescription_status>", // REQUIRED | string | ex. "not prescribed darzalex"
    file_name: "<file_name>", // REQUIRED | string | ex. "user_manual.pdf"
    condition: "<condition>", // REQUIRED | string | ex. "Active Psoriatic Arthritis"
    pathway: "<pathway>" // REQUIRED | string | ex. "personalSupport"
  }
});

```

| Field               | Type    | Required | Description                                               | Example                           | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|---------------------|---------|----------|-----------------------------------------------------------|-----------------------------------|---------|------------|------------|---------|---------|-------------|
| link_url            | string  | required | The HREF of the link interacted with                      | "undefined"                       |         |            |            |         |         |             |
| link_text           | string  | required | The text of the link interacted with                      | "Submit"                          |         |            |            |         |         |             |
| element_name        | string  | required | Name of the site element a user interacted with           | "Email Field"                     |         |            |            |         |         |             |
| module_name         | string  | required | Name of content module on the site                        | "Contact Form"                    |         |            |            |         |         |             |
| brand               | string  | required | Prescription drug that patients are familiar with         | "darzalex"                        |         |            |            |         |         |             |
| person              | string  | required | Persona of the user, e.g., patient or caregiver           | "patient"                         |         |            |            |         |         |             |
| prescription_status | string  | required | Current prescription status                               | "not prescribed darzalex"         |         |            |            |         |         |             |
| file_name           | string  | required | The name of the file interacted with                       | "user_manual.pdf"                |         |            |            |         |         |             |
| condition           | string  | required | Medical condition the patient seeks help with             | "Active Psoriatic Arthritis"      |         |            |            |         |         |             |
| pathway             | string  | required | Program pathway, e.g., Full Program, Cost Support Only    | "personalSupport"                 |         |            |            |         |         |             |
