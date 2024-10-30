# Modal View

Send when users view a modal prompting them to complete additional information.

## Javascript Code

```js
// When:
// Fire when a user views a modal prompting them for additional information.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'modal_view',
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
