# Expand Accordion

Fire whenever a user expands an accordion item.

## Javascript Code

```js
// When:
// User expands an accordion item.

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "accordion_expand",
  event_data: {
    link_text: "<link_text>", // REQUIRED | string | Text of the link interacted with, e.g., "FAQs"
    step_name: "<step_name>", // REQUIRED | string | Name of the step in the form flow, e.g., "Customize Your Call"
    step_number: "<step_number>", // REQUIRED | integer | Step number in the form flow, e.g., 1
    brand: "<brand>", // REQUIRED | string | Prescription drug familiar to the patient, e.g., "tecvayli"
    person: "<person>", // REQUIRED | string | Persona of the user, e.g., "patient" or "caregiver"
    prescription_status: "<prescription_status>", // REQUIRED | string | Prescription status, e.g., "Currently prescribed"
    condition: "<condition>", // REQUIRED | string | Medical condition, e.g., "Multiple myeloma"
    pathway: "<pathway>" // REQUIRED | string | Pathway used, e.g., "Full Program"
  }
});
```

## Variable Definitions

| Field               | Type    | Required | Description                                                            | Example               | Pattern | Min Length | Max Length | Minimum | Maximum | Multiple Of |
|---------------------|---------|----------|------------------------------------------------------------------------|-----------------------|---------|------------|------------|---------|---------|-------------|
| link_text           | string  | required | The text of the link interacted with                                   | "FAQs"                |         |            |            |         |         |             |
| step_name           | string  | required | The name of the step users are interacting with                        | "Customize Your Call" |         |            |            |         |         |             |
| step_number         | integer | required | Step number in a predefined form flow                                  | 1                     |         |            |            | 1       |         |             |
| brand               | string  | required | Prescription drug familiar to the patient                              | "tecvayli"            |         |            |            |         |         |             |
| person              | string  | required | Persona of user, e.g., "patient" or "caregiver"                        | "patient"             |         |            |            |         |         |             |
| prescription_status | string  | required | Whether the user is currently prescribed or not                        | "Currently prescribed"|         |            |            |         |         |             |
| condition           | string  | required | Medical condition the patient seeks help with                          | "Multiple myeloma"    |         |            |            |         |         |             |
| pathway             | string  | required | Pathway used in the program, e.g., "Full Program", "Guide Only"        | "Full Program"        |         |            |            |         |         |             |
