---
name: generate-report
description: Generate a PDF report from an existing research run
user_invocable: true
---

# Generate Report

Convert an existing research run's recommendation into a formatted Typst PDF.

## Usage

```
/generate-report <run_id>
```

## Behavior

1. Look up the `run_id` in `metadata.json` to confirm it exists, or locate `outputs/<run_id>/<run_id>.md` directly.
2. Launch **report-agent** with the `run_id`.
3. Once the PDF is generated, update the `report_pdf` field in `metadata.json` if not already set.
4. Report back with the path to the generated PDF.
