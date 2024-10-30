# Nav Click

Send when a user clicks on navigation elements (such as Top Nav or Footer)

## Javascript Code

```js
// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'nav_click',
  event_data: {   
    link_url: "<link_url>", // REQUIRED | string | ex. "undefined"
    link_text: "<link_text>", // REQUIRED | string | ex. "Sign In"
    element_name: "<element_name>", // REQUIRED | string | ex. "Header"
    brand: "<brand>", // REQUIRED | string | ex. "darzalex"
    person: "<person>", // REQUIRED | string | ex. "patient"
    prescription_status: "<prescription_status>", // contextual | string | ex. "not prescribed darzalex"
    condition: "<condition>", // contextual | string | ex. "Active Psoriatic Arthritis"
    pathway: "<pathway>" // contextual | string | ex. "personalSupport"
  }
});
```

## Variable Definitions

| Field               | Type    | Required   | Description                                                        | Example                       | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|---------------------|---------|------------|--------------------------------------------------------------------|-------------------------------|---------|------------|------------|---------|---------|-------------|
| link_url            | string  | required   | The HREF of the link interacted with                               | "undefined"                   |         |            |            |         |         |             |
| link_text           | string  | required   | The text of the link interacted with                               | "Sign In"                     |         |            |            |         |         |             |
| element_name        | string  | required   | Name of the site element a user interacted with                    | "Header"                      |         |            |            |         |         |             |
| brand               | string  | required   | Prescription drug familiar to the patient                          | "darzalex"                    |         |            |            |         |         |             |
| person              | string  | required   | Persona of the user, e.g., patient or caregiver                    | "patient"                     |         |            |            |         |         |             |
| prescription_status | string  | contextual | Current prescription status                                        | "not prescribed darzalex"     |         |            |            |         |         |             |
| condition           | string  | contextual | Medical condition the patient seeks help with                      | "Active Psoriatic Arthritis"  |         |            |            |         |         |             |
| pathway             | string  | contextual | Program pathway, e.g., Full Program, Cost Support Only, Guide Only | "personalSupport"             |         |            |            |         |         |             |
