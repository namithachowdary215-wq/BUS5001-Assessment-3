# Q3 — LLM-Based ESG Message Triage

## Objective
This exploratory experiment tests whether a large language model can convert short office and supplier sustainability messages into structured triage fields. Results are compared with a simple rule-based baseline. Three messages are not enough to establish general accuracy or production readiness.

## Model and environment
- Provider: Cohere API
- Model: `command-r-08-2024`
- Output: JSON-formatted triage results
- Environment: Google Colab
- API credential: Colab Secret named `COHERE_API_KEY`; do not hard-code or commit the secret.

The Hugging Face Inference API was also attempted, but the run returned a 402/no-credits response. The reported experiment used Cohere.

## Test messages
1. “There is a water leak in Building C that has been running all morning.”
2. “The accessible entrance near the main building has been blocked for two days.”
3. “One of our suppliers may not meet our sustainability policy. Please investigate.”

## Observed LLM classifications
| Message | Category | Urgency | Sentiment | Escalation | Team | Sensitivity |
|---|---|---|---|---|---|---|
| Water leak | `WATER` | `HIGH` | `NEGATIVE` | `Y` | `FACILITIES` | `LOW` |
| Blocked accessible entrance | `ACCESSIBILITY` | `HIGH` | `NEGATIVE` | `Y` | `ACCESSIBILITY` | `LOW` |
| Supplier sustainability concern | `SUPPLIER_SUSTAINABILITY` | `MEDIUM` | `NEGATIVE` | `Y` | `PROCUREMENT` | `LOW` |

Check this table against the final notebook and exported output files before submission.

## Baseline and validation
The rule-based baseline agreed with the LLM on category, urgency and assigned team for all three messages. The reported difference was the supplier message's sensitivity rating: LLM `LOW`; baseline `MEDIUM`.

Implemented checks covered JSON parsing, required fields and selected permitted values. These checks establish basic structural validity, not factual correctness or reliability on unseen messages.

## Limitations
- Only three test messages were used.
- The sample cannot establish broad accuracy or LLM superiority.
- Rule-based methods can miss paraphrases and context; LLM outputs can be inconsistent or incorrect.
- Sensitivity ratings and escalation decisions need clear policy definitions and human review.
- Real messages may contain personal, confidential or commercially sensitive information.
- Production use would require access controls, logging, privacy safeguards, monitoring, validation and human review.


## Reproduction checklist
1. Open the notebook in Google Colab.
2. Add the API key to Colab Secrets as `COHERE_API_KEY`.
3. Run cells in order.
4. Verify model, prompt and output schema.
5. Confirm output files match the table above.
6. Update the log if the final run differs.
