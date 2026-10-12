# Q3 Experiment Log

## Purpose

Test whether a large language model (LLM) can classify three short
ESG-related messages into a JSON schema and compare its output with a
simple rule-based baseline.

## Environment

-   Google Colab
-   Large language model (LLM) used for ESG-message classification
-   JSON-formatted responses
-   Keep any credentials or access tokens private; do not record secret
    values in this log.

## Run notes

1.  Prepared three ESG-related test messages: a water leak, a blocked
    accessible entrance, and a supplier sustainability concern.
2.  Submitted the messages to the LLM for structured classification.
3.  Checked JSON parsing, required fields, and selected permitted
    values.
4.  Compared the LLM output with the rule-based baseline.

## Observations recorded in the report

-   Category, urgency, and assigned team matched the baseline for all
    three messages.
-   Supplier-message sensitivity differed: the LLM classified it as
    `LOW`, while the baseline classified it as `MEDIUM`.
-   All three responses passed the implemented structural and
    selected-value checks.
-   These checks establish basic structural validity; they do not prove
    that every classification is factually correct.
-   The sample is too small to make broad claims about accuracy or
    superiority.
