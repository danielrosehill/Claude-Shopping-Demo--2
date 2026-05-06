---
name: search-local-suppliers
description: Search Israeli suppliers for a product
user_invocable: true
---

# Search Local Suppliers

Search all local (Israel-based) suppliers from the whitelist for a specific product.

## Usage

```
/search-local-suppliers <product query>
```

## Behavior

1. Launch the **research-agent** with scope `local` and the provided product query.
2. The agent will:
   - Browse each Israeli supplier from `whitelist.md` using Playwright
   - Capture screenshots of product pages
   - Write a dated recommendation to `recommendations/YYYY-MM-DD-<slug>.md`
3. Once the research agent completes, launch the **report-agent** to generate a PDF from the recommendation.
4. Report back with the recommendation summary and the path to the PDF in `outputs/`.
