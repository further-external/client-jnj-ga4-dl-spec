# Form View

Fire whenever a user is presented with a form on a page.

## Javascript Code

```js
// When:
// User is presented with a form on a page

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'custom_form_step_view',
  event_data: {
    form_name: "<form_name>", // REQUIRED | string | ex. "ecp_locator" or "free_trial"
    step_name: "<step_name>", // REQUIRED | string | ex. "contact" or "lead_generation"
    step_number: "<step_number>", // REQUIRED | integer | ex. 1
    brand: "<brand>", // REQUIRED | string | ex. "darzalex"
    person: "<person>", // REQUIRED | string | ex. "patient" or "caregiver"
    prescription_status: "<prescription_status>", // REQUIRED | string | ex. "currently prescribed darzalex"
    condition: "<condition>", // REQUIRED | string | ex. "Moderate to Severe Plaque Psoriasis"
    pathway: "<pathway>" // REQUIRED | string | ex. "dedicatedGuide" or "costSupport"
  }
});

```

## Variable Definitions

| Field               | Type    | Required | Description                                                                                       | Example                               | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|---------------------|---------|----------|---------------------------------------------------------------------------------------------------|---------------------------------------|---------|------------|------------|---------|---------|-------------|
| form_name           | string  | required | The form human-readable name for easy analyst identification; should be lowercase snake_case      | "ecp_locator" or "free_trial"         |         |            |            |         |         |             |
| step_name           | string  | required | The name of the step users are interacting with                                                   | "Support Personalization"             |         |            |            |         |         |             |
| step_number         | integer | required | Step number in a predefined form flow; should match the step number shown to users on the page    | 1, 2, 3                               |         |            |            | 1       |         |             |
| brand               | string  | required | Prescription drug familiar to the patient                                                         | "darzalex" or "erleada"               |         |            |            |         |         |             |
| person              | string  | required | Persona of the user, e.g., patient or caregiver                                                   | "patient" or "caregiver"              |         |            |            |         |         |             |
| prescription_status | string  | required | Current prescription status                                                                       | "currently prescribed darzalex"       |         |            |            |         |         |             |
| condition           | string  | required | Medical condition the patient seeks help with                                                     | "Moderate to Severe Plaque Psoriasis" |         |            |            |         |         |             |
| pathway             | string  | required | Program pathway, e.g., Full Program, Cost Support Only, Guide Only                                | "dedicatedGuide" or "costSupport"     |         |            |            |         |         |             |
