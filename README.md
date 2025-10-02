# status-interface-standard
A draft standard for a unified process status interface that allows public authorities to communicate process updates to citizens and organizations, including deadlines, required actions, and consequences of inaction.

\# Public Service Status Interface Standard (Draft)



Author: Riikka Jääskä  

Date: October 2025  



This repository contains a draft proposal for a \*\*standardized interface\*\* that allows public authorities to communicate the status of ongoing processes to citizens and organizations.



\## Motivation

Citizens and organizations often do not know:

\- Whether their application or notification has been received

\- Whether the addressed authority is processing their case

\- Whether further action is expected from them

\- What the deadline is and what happens if they do nothing

\- Which messages relate to which process



This standard defines a structured API and vocabulary to solve these problems.



\## Contents

\- `status\_interface\_standard.docx` – The full draft document (narrative, context, research references)

\- `status\_interface\_spec.yaml` – OpenAPI 3.0 specification of the interface

\- `examples/` – Example JSON payloads



\## How to Contribute

Feedback and issues are welcome! Please use the \*\*Issues\*\* tab in this repository to comment or propose improvements.



\## License

MIT License (or Creative Commons Attribution 4.0, if you prefer)

\## Citizen Perspective

Without a standardized status interface, citizens often face uncertainty:
- Was my application received?
- Do I need to respond to a request, and what happens if I do not?
- Which messages relate to which process?

With this standard, a citizen’s digital dashboard can show clear updates´, for example:

- **Passport Application** – Received by Police Authority. Awaiting appointment booking.  
- **Tax Clarification** – Awaiting user response. Response required by 15 Nov. If no action, estimated taxation will apply.  
- **Library Loan** – Awaiting user response. Overdue. Late fees will be charged.  

This way, the citizen always knows whether action is required, optional, or informational, across all services and authorities.

\### Example JSON Message - User has submitted an application for a passport

```json
{
  "authority_id": "001008",
  "authority_name": "Police Authority",
  "service_id": "002599",
  "service_name": "Passport Application",
  "case_id": "PA-2025-000123",
  "user_id": "05111999A9555",
  "status_type": "received_by_authority",
  "status_detail": "Your passport application has been received.",
  "process_type": "application_process",
  "response_type": "informational",
  "expected_action": "Wait for an invitation to book an appointment",
  "deadline": "",
  "consequence_if_no_action": "",
  "notification_channel": "online_service_ui",
  "response_channel": ("online_service_ui", "paper_mail"),
  "notification_id": "0345834343",
  "appeal_available": "false"
  "timestamp": "2025-10-01T12:30:00Z",
  "source_system": "passport_service"
}
```
