# Q1 — Office Sustainability Support Assistant

## Objective
This prototype uses Dialogflow ES to help employees describe office sustainability or facilities issues, provide a location, and confirm or cancel a report. It demonstrates conversation design, intent recognition, parameters, contexts, fallback handling and an escalation pathway. It does **not** create real tickets or send notifications.

## Functions
1. Report unnecessary energy use.
2. Report waste-management problems, such as contaminated recycling bins.
3. Report environmental concerns, such as unusual chemical odours.
4. Collect the affected building, floor, room or office location.
5. Confirm or cancel a report and provide a route to human assistance.

## Intents
| Intent | Purpose |
|---|---|
| `Report_Office_Issue` | Recognises office sustainability/facilities issue reports. |
| `Provide_Office_Location` | Captures the location. |
| `Confirm_Office_Report` | Confirms the report for demonstration purposes. |
| `Cancel_Office_Report` | Cancels the report in the conversation. |
| `Escalate_Office_Issue` | Provides a pathway to request human assistance. |
| `Default Welcome Intent` | Greets the user. |
| `Default Fallback Intent` | Handles unsupported or unrecognised input. |

## Entity and parameters
The custom entity `OFFICE_ISSUE_TYPE` groups common expressions into:
- `ENERGY_WASTE` — unnecessary energy use, lights left on, air conditioning running overnight.
- `WASTE_MANAGEMENT` — contaminated recycling and waste-disposal issues.
- `CHEMICAL_ODOR` — chemical smells, strange smells and strong odours.

The reporting intent uses the `OFFICE_ISSUE_TYPE` parameter. The location intent uses `office_location` with `@sys.any` to accept free text.

## Contexts and flow
- `Report_Office_Issue` outputs `awaiting_office_location`.
- `Provide_Office_Location` takes `awaiting_office_location` as input and outputs `awaiting_report_confirmation`.
- Confirmation and cancellation intents handle the user's decision.

## Test examples
| Test | Example input | Expected behaviour |
|---|---|---|
| Issue recognition | “I want to report unnecessary energy use.” | Matches `Report_Office_Issue`; category extraction depends on entity matching. |
| Location | “It happened in Building C.” | Matches `Provide_Office_Location` when the expected context is active. |
| Confirmation | “Yes, submit my office report.” | Shows the prototype confirmation response. |
| Cancellation | “No, cancel the report.” | Shows the cancellation response. |
| Fallback | “Tell me a joke.” | Explains the supported office-related requests. |
| Human assistance | “I need human help.” | Should match the escalation intent if training phrases and context are configured appropriately. |

Only describe a test as successful if the console shows the expected result. A confirmation response does not mean a real ticket or notification was created.

## Screenshot references in the report
-  Initial Dialogflow page.
-  Initial Intents page before regular intents were created.
-  List of created intents.
-  Location response and confirmation prompt.
-  Confirmation response.
-  Cancellation response.
-  Fallback response to an unsupported request.
-  Reporting intent training phrases and `OFFICE_ISSUE_TYPE` parameter.
-  `OFFICE_ISSUE_TYPE` entity configuration.

## Accessibility, privacy and governance
Multiple training phrases allow different ways to describe issues. A production system should support keyboard and screen-reader access, plain-language responses, language needs and alternative reporting channels. It should collect only necessary information, explain data use, restrict access to reports and provide human oversight for potentially hazardous issues.

## Limitations and future work
This is a Dialogflow ES prototype. It has no enterprise ticketing integration, live notifications, backend report storage or ESG analytics. Future work could connect it to a secure workflow with access controls, audit logs and human review.

## Demonstration video
**Microsoft Stream link:** Replace this line with the actual video URL before submission. The video must be under two minutes and accessible to the teaching team.

## Evidence checklist
- [ ] Confirm all custom intents are saved.
- [ ] Test confirmation, cancellation, fallback and escalation in the console.
- [ ] Insert the real video link in this README and the report.
- [ ] Do not claim live ticketing or notifications exist unless implemented and tested.
