# Modal Close

Send when users manually close a modal, usually with an icon like an "X" or "close".

## Javascript Code

```js
// When:
// Send when users manually close a modal, usually with an icon like an "X" or "close".

// Code:
window.globalDataLayer = window.globalDataLayer || [];
globalDataLayer.push({ event_data: null });  // Clear the previous event_data object.
globalDataLayer.push({
  event: 'modal_close',
  event_data: {
    modal_name: "<modal_name>", // REQUIRED | string | ex. "Contact US"
    step_name: "<step_name>", // REQUIRED | string | ex. "Support Personalization"
    step_number: "<step_number>", // REQUIRED | integer | ex. 0
    brand: "<brand>", // REQUIRED | string | ex. "darzalex"
    person: "<person>", // REQUIRED | string | ex. "patient"
    prescription_status: "<prescription_status>", // contextual | string | ex. "not prescribed darzalex"
    condition: "<condition>", // contextual | string | ex. "Active Psoriatic Arthritis"
    pathway: "<pathway>" // contextual | string | ex. "personalSupport"
  }
});
globalDataLayer.push({ event_data: null });  // Clear the previous event_data object.
```

## Variable Definitions

| Field               | Type        | Required | Description                                                                                        | Example                           | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|---------------------|-------------|----------|----------------------------------------------------------------------------------------------------|-----------------------------------|---------|------------|------------|---------|---------|-------------|
| modal_name          | string      | required | The name of the modal being viewed                                                                 | "Contact US"                      |         |            |            |         |         |             |
| step_name           | string      | required | The name of the step users are interacting with                                                    | "Support Personalization"         |         |            |            |         |         |             |
| step_number         | integer     | required | Step number in a predefined form flow; should match the step number shown to users on the page     | 0                                 |         |            |            | 0       |         |             |
| brand               | string      | required | Prescription drug familiar to the patient                                                          | "darzalex"                        |         |            |            |         |         |             |
| person              | string      | required | Persona of the user, e.g., patient or caregiver                                                    | "patient"                         |         |            |            |         |         |             |
| prescription_status | contextual  | required | Current prescription status                                                                        | "not prescribed darzalex"         |         |            |            |         |         |             |
| condition           | contextual  | required | Medical condition the patient seeks help with                                                      | "Active Psoriatic Arthritis"      |         |            |            |         |         |             |
| pathway             | contextual  | required | Program pathway, e.g., Full Program, Cost Support Only, Guide Only                                 | "personalSupport"                 |         |            |            |         |         |             |
