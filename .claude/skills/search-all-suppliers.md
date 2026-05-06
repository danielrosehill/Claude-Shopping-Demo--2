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

1. Launch the **research-agent** with scope `all` and the provided product query.
2. The agent will:
   - Browse every supplier from `whitelist.md` (local and international) using Playwright
   - Capture screenshots of product pages
   - Write a dated recommendation to `recommendations/YYYY-MM-DD-<slug>.md`
3. Once the research agent completes, launch the **report-agent** to generate a PDF from the recommendation.
4. Report back with the recommendation summary and the path to the PDF in `outputs/`.
