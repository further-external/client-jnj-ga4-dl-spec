 # Form Error

Fire when a user is shown an error while filling out a form.

## Javascript Code

```js
// When:
// Fire when a user is shown an error while filling out a form.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'custom_form_error',
  event_data: {
    form_name: "<form_name>", // REQUIRED | string | Used with the "form_complete" or "form_error" events. Returns the form name, e.g., "Digital Enrollment Form"
    step_name: "<step_name>", // REQUIRED | string | The name of the step users are interacting with, e.g., "Support Personalization"
    step_number: "<step_number>", // REQUIRED | integer | Step number in a predefined form flow, e.g., 1
    insurance_coverage: "<insurance_coverage>", // contextual | string | ex. "Medicare"
    insurance_assistance: "<insurance_assistance>", // contextual | string | ex. "Yes"
    has_savings_card: "<has_savings_card>", // contextual | string | ex. "No"
    brand: "<brand>", // REQUIRED | string | Prescription drug that patients are familiar with, e.g., "darzalex"
    person: "<person>", // REQUIRED | string | Persona of user, e.g., "patient" or "caregiver"
    prescription_status: "<prescription_status>", // contextual | string | Currently prescribed or not, e.g., "currently prescribed darzalex"
    condition: "<condition>", // contextual | string | Medical condition the patient seeks help with, e.g., "Moderate to Severe Plaque Psoriasis"
    pathway: "<pathway>", // contextual | string | Pathway used, e.g., "Full Program"
    error_message: "<error_message>", // REQUIRED | string | error message e.g., "Enter a valid email address"
    error_type: "<error_type>" // REQUIRED | string | error type e.g., "Validation"
  }
});
```

## Variable Definitions

| Field               | Type    | Required   | Description                                                                             | Example                                | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|---------------------|---------|------------|-----------------------------------------------------------------------------------------|----------------------------------------|---------|------------|------------|---------|---------|-------------|
| form_name           | string  | required   | Used with the "form_complete" or "form_error" events. Returns the form name.            | "Digital Enrollment Form"              |         |            |            |         |         |             |
| step_name           | string  | required   | The name of the step users are interacting with                                         | "Support Personalization"              |         |            |            |         |         |             |
| step_number         | integer | required   | Step number in a predefined form flow, should match step number shown to users on page. | 1,2,3                                  |         |            |            | 1       |         |             |
| insurance_coverage  | string  | contextual | The type of insurance coverage for the patient                                          | "Medicare"                             |         |            |            |         |         |             |
| insurance_assistance| string  | contextual | Insurance assistance selection for the patient                                          | "Yes"                                  |         |            |            |         |         |             |
| has_savings_card    | string  | contextual | Indicates whether the patient already has a savings card                                | "No"                                   |         |            |            |         |         |             |
| brand               | string  | required   | Prescription drug that patients are familiar with                                       | "darzalex", "erleada"                  |         |            |            |         |         |             |
| person              | string  | required   | Persona of user, e.g., "patient" or "caregiver"                                         | "patient", "caregiver"                 |         |            |            |         |         |             |
| prescription_status | string  | contextual | Currently prescribed or not currently prescribed                                        | "currently prescribed darzalex"        |         |            |            |         |         |             |
| condition           | string  | contextual | Medical condition the patient seeks help with                                           | "Moderate to Severe Plaque Psoriasis"  |         |            |            |         |         |             |
| pathway             | string  | contextual | Pathway used, e.g., "Full Program", "Cost Support Only", "Guide Only"                   | "dedicatedGuide", "costSupport"        |         |            |            |         |         |             |
| error_message       | string  | required   | The message that is shown to the users when the error occurs.                           | "Enter a valid email address"          |         |            |            |         |         |             |
| error_type          | string  | required   | The type/categorization of the error being shown to the user.                           | "Validation"                           |         |            |            |         |         |             |
