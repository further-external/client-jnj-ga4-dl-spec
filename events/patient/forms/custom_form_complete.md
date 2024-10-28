# Form Complete

Fire whenever a user successfully completes a form.

This event is fired when form input is successfully received and processed. This is in contrast to `form_error`, which occurs when a submission is attempted but an error occurs and the form input is not received and processed.

## Javascript Code

```js
// When:
// Fire when a user successfully completes a form.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'custom_form_complete',
  event_data: {
    form_name: "<form_name>", // REQUIRED | string | Name of the form, e.g., "Digital Enrollment Form"
    eligibility_outcome: "<eligibility_outcome>", // REQUIRED | string | Outcome of eligibility check, e.g., "Not eligible"
    support_program_options: "<support_program_options>", // REQUIRED | string | Options chosen for support programs, e.g., "dedicatedGuide"
    brand: "<brand>", // REQUIRED | string | Prescription drug familiar to the patient, e.g., "darzalex"
    person: "<person>", // REQUIRED | string | Persona of the user, e.g., "patient" or "caregiver"
    prescription_status: "<prescription_status>", // REQUIRED | string | Prescription status, e.g., "currently prescribed darzalex"
    condition: "<condition>", // REQUIRED | string | Medical condition, e.g., "Moderate to Severe Plaque Psoriasis"
    pathway: "<pathway>" // REQUIRED | string | Pathway used, e.g., "dedicatedGuide"
  }
});

```

## Variable Definitions

| Field                  | Type    | Required | Description                                                | Example                                    | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|------------------------|---------|----------|------------------------------------------------------------|--------------------------------------------|---------|------------|------------|---------|---------|-------------|
| form_name              | string  | required | Used with the "form_complete" or "form_error" events. Returns the form name.| "Digital Enrollment Form" |         |            |            |         |         |             |
| eligibility_outcome    | string  | required | Indicates if the user is eligible or not for the program    | "Not eligible"                            |         |            |            |         |         |             |
| support_program_options| string  | required | Support program options selected by the user                | "dedicatedGuide"                          |         |            |            |         |         |             |
| brand                  | string  | required | Prescription drug familiar to the patient                   | "darzalex"                                |         |            |            |         |         |             |
| person                 | string  | required | Persona of the user, e.g., "patient" or "caregiver"         | "patient"                                 |         |            |            |         |         |             |
| prescription_status    | string  | required | Indicates whether the user is currently prescribed          | "currently prescribed darzalex"           |         |            |            |         |         |             |
| condition              | string  | required | Medical condition for which the user seeks assistance       | "Moderate to Severe Plaque Psoriasis"     |         |            |            |         |         |             |
| pathway                | string  | required | Pathway used in the program, e.g., "Full Program", "Guide Only"| "dedicatedGuide"                       |         |            |            |         |         |             |

