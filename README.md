# StatWharf B2B Software Vendor Dataset

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22959030.svg)](https://doi.org/10.5281/zenodo.22959030)

This dataset lists the B2B software vendors on the StatWharf [category pages](https://statwharf.com/best/). Each row records one vendor in one category, with the buyer fit, the dated pricing note and the source that StatWharf checked.

Snapshot: 2026-09-25. 176 categories, 1,700 vendor rows, 1,438 distinct vendors.

## Files

- `data/categories.csv`: one row per category page.
- `data/vendors.csv`: one row per vendor in a category. A vendor that appears in several categories has one row for each category.

## Fields

`categories.csv`

| Field | Meaning |
|---|---|
| `category_slug` | The category phrase, hyphenated. It is also the page path. |
| `category` | The category name. |
| `page_url` | The StatWharf comparison page for the category. |
| `published` | The date that the page was first published. |
| `updated` | The date of the last content change to the page. |
| `vendor_count` | The number of vendors on the page. |

`vendors.csv`

| Field | Meaning |
|---|---|
| `category_slug` | The category. Joins to `categories.csv`. |
| `vendor` | The vendor or product name. |
| `vendor_url` | The vendor's product page. |
| `segment` | The buyer segment: `enterprise`, `mid-market`, `smb`, `specialist` or `open-source`. |
| `consider_for` | The buyer fit that the vendor's documentation supports. It is not an endorsement. |
| `pricing_note` | The pricing as published by the vendor, with the month of the check. |
| `billing_terms` | The billing cadence from the pricing source, or "Not recorded". |
| `source_status` | `source-checked`: StatWharf read the vendor source on the date given. `source-review-needed`: StatWharf did not read it. |
| `source_checked_on` | The date of the source check. |
| `pricing_source_url` | The pricing page that StatWharf read. An empty cell means that the vendor has no pricing page. |
| `documentation_url` | The documentation page that StatWharf read. An empty cell means that StatWharf used no documentation page. |
| `vendor_confirmed` | `yes`: the vendor approved its record. `no`: the vendor did not. |

## Method

StatWharf Editorial selects 5 to 12 vendors for each category. The selection uses the vendors that buyers name for the category and the vendors whose public documentation covers it. An editor reads each vendor's product, documentation and pricing pages, and records the date of that check.

Vendors did not supply the data. No vendor approved its record in this snapshot. A vendor can pay for inclusion or for a row position on a StatWharf page. Each page discloses that row position can reflect a paid placement.

The rows are sorted alphabetically within each category. The dataset has no score or rank. The order of vendors on a StatWharf page is not a quality ranking, so this dataset leaves it out.

## Limits

- Pricing changes often. Each note is correct only for the month of its check.
- `consider_for` is an editorial summary of vendor documentation. StatWharf did not test the products hands-on.
- A category lists a selection of vendors, not every vendor in the market.

## License

The data is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Credit "StatWharf Editorial" and link to the category page or to this dataset.

## Citation

```
StatWharf Editorial. (2026). StatWharf B2B Software Vendor Dataset (2026-09-25) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.22959030
```

## Corrections

Send corrections to editorial@statwharf.com. The live category pages carry the current data.
