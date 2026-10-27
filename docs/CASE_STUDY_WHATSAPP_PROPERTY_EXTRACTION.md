# Case Study: WhatsApp Property Data Extraction

## Summary

**Domain:** Real-estate operations  
**Workflow platform:** n8n  
**Destination:** Google Sheets  
**Core capabilities:** message classification, AI-assisted extraction, field mapping, validation, and duplicate handling

This case study describes a workflow project using authorized existing WhatsApp property messages as input. The public repository is a sanitized description and reference package; it does not contain the client's private messages, credentials, or a directly importable production workflow.

## The problem

Property listings often arrive as informal messages with inconsistent spelling, abbreviations, mixed language, and different field order. Manually copying them into a spreadsheet makes it harder to search, compare, and maintain records.

## Workflow approach

1. Receive an incoming message event from the configured provider.
2. Normalize the event while preserving meaningful text, phone digits, plot identifiers, and units.
3. Classify whether the message contains a relevant property listing.
4. Extract source-supported fields into a structured record.
5. Validate the output and keep unknown or unsupported values empty.
6. Check for duplicates using the configured combination of block, plot number, and phone number when all key values are present.
7. Keep the more complete matching record and write the result to the configured sheet.
8. Route ambiguous or invalid records for review and log sanitized outcomes.

## Example fields

Society, phase, block, plot number, property type, size, demand, sale/rent, commercial status, corner, park-facing, road details, owner/dealer role, agency, contact number, and stated house features.

Only fields supported by the source message should be populated. A plot size must not be mistaken for a plot number, and a missing phone number or price must never be guessed.

## Processing boundary

- Incoming-message processing only.
- No automated replies or group messages.
- Access and processing must be authorized by the client and provider.
- Real message text and personal contact details are not included in this public case study.

## Outcome and measurement

The project was reported by the operator to process approximately **3,000–5,000 rows per day** during the described operating period. This is an operator-reported figure, not an independently audited benchmark. Actual throughput and accuracy depend on message quality, model configuration, provider limits, validation rules, and destination performance.

A rigorous production evaluation should track:
- Number of messages received and records accepted
- Extraction accuracy by field
- False-positive and missed-listing rates
- Duplicate detection precision
- Records routed for manual review
- Processing failures and retry outcomes
- Cost per accepted record

No accuracy percentage is claimed here because a labeled evaluation dataset and independently verified results are not published.

## Public implementation materials

The companion [WhatsApp AI Business Agent repository](https://github.com/AIwithsanaullah/whatsapp-ai-business-agent) includes a reference blueprint, extraction prompt, fictional examples, workflow design, and privacy guidance. The JSON blueprint is tool-agnostic and is **not** an import-ready n8n export.

## Next validation steps

1. Test a representative, consented, redacted sample.
2. Compare extracted fields against human-labeled expected values.
3. Test ambiguous plot/size combinations and missing duplicate keys.
4. Confirm no outgoing WhatsApp nodes or reply actions are present.
5. Review access permissions, retention, retry limits, and sanitized error logs.
6. Export a sanitized, actual n8n workflow only after removing credentials, webhook URLs, customer data, and other secrets.
