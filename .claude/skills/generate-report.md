---
name: generate-report
description: Generate a PDF report from an existing recommendation
user_invocable: true
---

# Generate Report

Convert an existing recommendation file into a formatted Typst PDF.

## Usage

```
/generate-report <date-slug or filename>
```

Examples:
- `/generate-report 2026-05-06-edding-780-paint-marker`
- `/generate-report recommendations/2026-05-06-edding-780-paint-marker.md`

## Behavior

1. Locate the recommendation file in `recommendations/`.
2. Launch the **report-agent** with the path to that file.
3. The agent will generate a Typst `.typ` file and compile it to PDF in `outputs/`.
4. Report back with the path to the generated PDF.
