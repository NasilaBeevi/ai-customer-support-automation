# AI-Powered Customer Support Email Classification and Routing

## Project Overview

This project demonstrates an AI-powered customer support email automation workflow built using n8n, Claude AI, Gmail, and Google Sheets.

The workflow analyzes incoming customer support emails, generates a concise issue summary, identifies the appropriate support department, extracts order numbers when available, and determines whether an email can proceed or requires human review.

## Objectives

- Automate the initial classification of customer support emails.
- Reduce manual effort in sorting customer inquiries.
- Extract relevant information from email messages.
- Route unclear inquiries for human review.
- Maintain a structured record of classification results.

## Technologies Used

- **n8n** — workflow automation
- **Claude AI** — natural-language email classification
- **Gmail** — email trigger and message retrieval
- **Google Sheets** — classification results and tracking
- **JavaScript** — data parsing, validation, and processing
- **JSON** — structured AI output

## Workflow Architecture

Gmail Trigger → Get Email Message → Edit Fields → Claude AI Classification → JavaScript Processing → IF Condition → Google Sheets

### Workflow Steps

1. **Email Trigger:** Detects incoming emails through Gmail.
2. **Email Processing:** Prepares the available email content for analysis.
3. **AI Classification:** Uses Claude AI to summarize the issue, suggest a department, extract the order number, and assess whether human review is required.
4. **Data Validation:** Parses and validates the structured JSON response using JavaScript.
5. **Conditional Routing:** Routes emails according to the human-review decision.
6. **Results Tracking:** Appends the classification results to Google Sheets.

## Classification Categories

- Delivery
- Billing
- Technical Support
- General Support

## Human Review Logic

The workflow flags an email for human review when the issue is unclear or a delivery inquiry is missing its order number.

Other test cases can proceed to the ready-for-processing path when the classification rules are satisfied.

## Testing and Validation

The workflow was tested using sample customer support emails.

| Test Scenario | Expected Outcome | Result |
|---|---|---|
| Delivery inquiry with an order number | Ready for Processing | Passed |
| Unclear customer issue | Needs Human Review | Passed |

The workflow successfully routed the tested emails and recorded their classification results in Google Sheets.

## Key Skills Demonstrated

- Workflow automation
- AI service integration
- Email processing
- JavaScript data handling
- JSON parsing and validation
- Conditional logic and routing
- Human-in-the-loop review
- Google Sheets integration
- Workflow testing and debugging

## Limitations and Future Improvements

- Retrieve the complete email body instead of relying on Gmail snippets.
- Add duplicate-email prevention.
- Improve error handling and retry mechanisms.
- Add notifications for emails requiring human review.
- Introduce logging and monitoring for workflow failures.
- Evaluate classification accuracy using a broader set of test emails.

## Security Considerations

This repository is intended as a learning and portfolio project. Credentials, API keys, private customer information, and OAuth tokens should never be committed to the repository.

## Project Status

Working prototype tested with sample emails. Further improvements are planned before production use.
