# Form Step Complete

Send when a user completes the form step (at button click).

## Javascript Code

```js
// When:
// Fire when a user completes a step within a form by clicking a button.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'custom_form_step_complete',
  event_data: {
    form_name: "<form_name>", // REQUIRED | string | ex. "Digital Enrollment Form"
    step_name: "<step_name>", // REQUIRED | string | ex. "Support Personalization"
    step_number: "<step_number>", // REQUIRED | integer | ex. 1
    insurance_coverage: "<insurance_coverage>", // REQUIRED | string | ex. "Medicare"
    insurance_assistance: "<insurance_assistance>", // REQUIRED | string | ex. "Yes"
    has_savings_card: "<has_savings_card>", // REQUIRED | string | ex. "No"
    brand: "<brand>", // REQUIRED | string | ex. "darzalex"
    person: "<person>", // REQUIRED | string | ex. "patient"
    prescription_status: "<prescription_status>", // REQUIRED | string | ex. "currently prescribed darzalex"
    condition: "<condition>", // REQUIRED | string | ex. "Moderate to Severe Plaque Psoriasis"
    pathway: "<pathway>" // REQUIRED | string | ex. "dedicatedGuide"
  }
});
```

## Variable Definitions

| Field               | Type    | Required | Description                                                         | Example                               | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|---------------------|---------|----------|---------------------------------------------------------------------|---------------------------------------|---------|------------|------------|---------|---------|-------------|
| form_name           | string  | required | Used with "form_complete" or "form_error" events; returns form name | "Digital Enrollment Form"             |         |            |            |         |         |             |
| step_name           | string  | required | The name of the step users are interacting with                     | "Support Personalization"             |         |            |            |         |         |             |
| step_number         | integer | required | Step number in a predefined form flow                               | 1                                     |         |            |            | 1       |         |             |
| insurance_coverage  | string  | required | The type of insurance coverage for the patient                      | "Medicare"                            |         |            |            |         |         |             |
| insurance_assistance| string  | required | Insurance assistance selection for the patient                      | "Yes"                                 |         |            |            |         |         |             |
| has_savings_card    | string  | required | Indicates whether the patient already has a savings card            | "No"                                  |         |            |            |         |         |             |
| brand               | string  | required | Prescription drug familiar to the patient                           | "darzalex"                            |         |            |            |         |         |             |
| person              | string  | required | Persona of the user, e.g., patient or caregiver                     | "patient"                             |         |            |            |         |         |             |
| prescription_status | string  | required | Current prescription status                                         | "currently prescribed darzalex"       |         |            |            |         |         |             |
| condition           | string  | required | Medical condition the patient seeks help with                       | "Moderate to Severe Plaque Psoriasis" |         |            |            |         |         |             |
| pathway             | string  | required | Program pathway, e.g., Full Program, Cost Support Only, Guide Only  | "dedicatedGuide"                      |         |            |            |         |         |             |

