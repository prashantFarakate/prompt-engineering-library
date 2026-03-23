# RTCOS — Role + Task + Context + Output + Style

Structured prompt with 5 components. Eliminates ambiguity — no role means the model picks a generic persona, no output format means inconsistent structure every run.

Use when I need consistent, predictable output I can version-control and hand to engineering.

---

**Template**
```
ROLE:    You are a [title] with expertise in [domain]
TASK:    [single action] — [deliverable]
CONTEXT: product / user / background / constraints
OUTPUT:  format + structure
STYLE:   tone / length / audience
```

---

**Example — IDP field extraction from invoice**

This is the kind of prompt I use when defining how the LLM should extract structured data from scanned invoice documents in our IDP pipeline.

```
ROLE:
You are an expert in document processing working on an Intelligent Document Processing system
for accounts payable automation.

TASK:
Extract all structured fields from the following invoice text.

CONTEXT:
- Pipeline: OCR → LLM extraction → ERP posting
- Document type: Vendor tax invoice (Indian GST format)
- Downstream use: Extracted JSON is validated and posted to SAP
- Known issues: Vendor names vary (short vs full legal name), amounts may include
  commas or currency symbols, PO references sometimes missing

OUTPUT:
Return as JSON with exactly these fields:
{
  "vendor_name": "",
  "invoice_number": "",
  "invoice_date": "",        // ISO format: YYYY-MM-DD
  "due_date": "",            // ISO format, null if not present
  "line_items": [
    { "description": "", "quantity": 0, "unit_price": 0, "amount": 0 }
  ],
  "subtotal": 0,
  "tax_amount": 0,
  "total_amount": 0,
  "currency": "",            // ISO 4217: INR, USD, EUR
  "po_reference": "",        // null if not present
  "gstin": ""                // null if not present
}
If a field cannot be extracted, return null — do not guess.

STYLE:
- Return JSON only — no explanation, no markdown wrapper
- Strict field names — no extras, no renaming
```

---

**Example — Writing a user story for human-review feature**

```
ROLE:
You are a senior BA on an AI-powered invoice processing product.

TASK:
Write a user story for a feature that lets Finance Managers approve or reject
AI-extracted invoice data before ERP posting.

CONTEXT:
- Product: IDP system for mid-market B2B companies
- User: Finance Manager — non-technical, reviews 50–100 invoices/day
- Background: Extraction accuracy ~92%. Errors need human review before posting.
- Constraints: UI must work on tablet and desktop

OUTPUT:
1. User story — As a / I want / So that
2. Acceptance criteria — minimum 3 Given/When/Then scenarios
3. Definition of Done — 5 items

STYLE:
- Concise, plain English
- Audience: dev team sprint backlog
- Max 400 words
```

---

— [Cheat Sheet](../CHEAT-SHEET.md) · [README](../README.md)
