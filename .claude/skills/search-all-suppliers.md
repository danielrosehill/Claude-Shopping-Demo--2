---
name: search-all-suppliers
description: Search all suppliers (local + international) for a product
user_invocable: true
---

# Search All Suppliers

Search all suppliers — local Israeli stores plus international sources (AliExpress, Amazon) — for a specific product.

## Usage

```
/search-all-suppliers <product query>
```

## Behavior

1. Generate a random UUID for this run (the `run_id`).
2. Clean up the user's request into a concise product query.
3. Save the prompt to `inputs/prompts/<run_id>.md` with content:
   ```
   # Product Search

   **Run ID:** <run_id>
   **Date:** YYYY-MM-DD
   **Scope:** all
   **Query:** <cleaned-up product query>
   **Raw input:** <original user message>
   ```
4. Launch **research-agent** with the `run_id`, product query, and scope `all`.
5. Once research completes, launch **report-agent** with the same `run_id`.
6. Update `metadata.json` at the repo root — append an entry:
   ```json
   {
     "run_id": "<run_id>",
     "date": "YYYY-MM-DD",
     "query": "<cleaned-up product query>",
     "scope": "all",
     "prompt": "inputs/prompts/<run_id>.md",
     "output_dir": "outputs/<run_id>/",
     "report_md": "outputs/<run_id>/<run_id>.md",
     "report_pdf": "outputs/<run_id>/<run_id>.pdf"
   }
   ```
7. Report back with the recommendation summary and the path to the PDF.
