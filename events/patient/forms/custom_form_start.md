# Form Start

Fire whenever a user starts filling out a form. 

This event is generally fired after user input in the first form field. Historically, this has been done via an HTMLElement `change` event on a form field, though it could be done via an HTMLElement `focus` event on a form field if that proves easier to implement. It should only be fired once per form. If that is too technically complicated to implement, it can be limited on the GTM side instead.

## Javascript Code

```js
// When:
// Fire when a user starts to fill out a form. Event fires after user input into the first form field 
// and should only fire once. onchange(), onfocus(), and GTM may be helpful.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'custom_form_start',
  event_data: {
    form_name: "<form_name>", // REQUIRED | string | Name of the form, e.g., "Digital Enrollment Form"
    eligibility_outcome: "<eligibility_outcome>", // contextual | string | Outcome of eligibility check, e.g., "Not eligible"
    support_program_options: "<support_program_options>", // contextual | string | Options chosen for support programs, e.g., "dedicatedGuide"
    brand: "<brand>", // REQUIRED | string | Prescription drug familiar to the patient, e.g., "darzalex"
    person: "<person>", // REQUIRED | string | Persona of the user, e.g., "patient" or "caregiver"
    prescription_status: "<prescription_status>", // contextual | string | Prescription status, e.g., "currently prescribed darzalex"
    condition: "<condition>", // contextual | string | Medical condition, e.g., "Moderate to Severe Plaque Psoriasis"
    pathway: "<pathway>" // contextual | string | Pathway used, e.g., "dedicatedGuide"
  }
});

```

## Variable Definitions

| Field                  | Type    | Required   | Description                                                                 | Example                                   | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|------------------------|---------|------------|-----------------------------------------------------------------------------|-------------------------------------------|---------|------------|------------|---------|---------|-------------|
| form_name              | string  | required   | Used with the "form_complete" or "form_error" events. Returns the form name.| "Digital Enrollment Form"                 |         |            |            |         |         |             |
| eligibility_outcome    | string  | contextual | Indicates if the user is eligible or not for the program                    | "Not eligible"                            |         |            |            |         |         |             |
| support_program_options| string  | contextual | Support program options selected by the user                                | "dedicatedGuide"                          |         |            |            |         |         |             |
| brand                  | string  | required   | Prescription drug familiar to the patient                                   | "darzalex"                                |         |            |            |         |         |             |
| person                 | string  | required   | Persona of the user, e.g., "patient" or "caregiver"                         | "patient"                                 |         |            |            |         |         |             |
| prescription_status    | string  | contextual | Indicates whether the user is currently prescribed                          | "currently prescribed darzalex"           |         |            |            |         |         |             |
| condition              | string  | contextual | Medical condition for which the user seeks assistance                       | "Moderate to Severe Plaque Psoriasis"     |         |            |            |         |         |             |
| pathway                | string  | contextual | Pathway used in the program, e.g., "Full Program", "Guide Only"             | "dedicatedGuide"                          |         |            |            |         |         |             |
