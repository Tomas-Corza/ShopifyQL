# ShopifyQL Query Library

**Prepared by Tomas Corza** · Reusable Shopify Analytics / ShopifyQL reporting queries.

This library archives ShopifyQL queries from earlier reporting and auditing work (September–October 2026), organized by purpose. It contains **30 queries**.

## Quick start

1. In Shopify Admin, open **Analytics → Reports** and choose a report supporting ShopifyQL / the query editor.
2. Open the query editor and paste the contents of one `.shopifyql` file.
3. Update the `SINCE` and `UNTIL` dates and adjust `LIMIT` as required.
4. Run the query, check the fields and totals, then export from Shopify if needed.

> **Compatibility notice:** These are archived queries, not a tested guarantee of current ShopifyQL syntax. The dataset, metric, dimension, attribution syntax and report permissions can change. If Shopify rejects a query, inspect the specific error and adapt to the current ShopifyQL reference. Historical queries may have been exploratory or unsuccessful. `recovered` means recovered from previous conversation text, *not* independently confirmed executable today. `adapted` means reconstructed from a truncated historical excerpt.

## Folders

| Folder | Purpose |
|---|---|
| `sales/` | Daily/monthly revenue, profitability, orders, comparisons |
| `customers/` | New vs. returning customers and acquisition sources |
| `attribution/` | Channel and UTM reporting, campaign performance |
| `inventory/` | Product/SKU sales, availability and stock trends |
| `checkout/` | Sessions, conversion and checkout troubleshooting |
| `reversals/` | Sales reversals, cancellations-related reporting |

## Provenance

See [`manifest.json`](manifest.json) for the conversation date and recovery status of every file. Original dates have deliberately been retained for auditability. These files contain **queries only**, no exported business data, credentials or access tokens.

## Important interpretation notes

- **Sales ≠ payments:** Shopify sales metrics do not necessarily reconcile to payment settlement records.
- **Sales reversals ≠ a complete refund/cancellation timeline:** For individual order events, use an authorized Shopify Admin order export or the Admin GraphQL API; do not infer the exact reason/date from aggregated ShopifyQL alone.
- **Attribution ≠ causation:** A last-click revenue report is not the same as incremental lift or ad-platform ROAS. Compare attribution models carefully.
- **New customers ≠ all customers:** First-order/returning distinctions vary by metric and report.
- **Gross profit depends on cost data:** Check that product costs were recorded for the relevant period.
- **Inventory counts are historical snapshots/availability indicators:** They are not a substitute for a true stock-ledger audit. Some historical fields may not be supported for all stores.
- **Limits can truncate exports:** Split date ranges if a result hits its query limit.
- **Privacy:** Keep real order-level exports, customer information, API credentials and private store data out of public repositories.

## Updating the library

Use one query per file. For a new query, add a matching entry in `manifest.json`, including its origin and date. Test against a Shopify report before marking it as validated.

## License

MIT; see [`LICENSE`](LICENSE).
