# Reconciliation methodology

## 1. Sign convention

All differences use:

`Difference = Company A amount − Company B amount`

A negative result means Company B recorded more than Company A.

## 2. Comparable period

The comparison ends at the earlier reliable cut-off supported by both workbooks. Transactions after that date are disclosed separately as non-comparable items.

## 3. Amount normalisation

The workflow keeps separate fields for gross amount, actual settlement amount, discount, refund, fee, tax, weight variance, payable or receivable occurrence, and payment or receipt.

Where a workbook explicitly calculates an actual settlement amount, that amount is preferred over the gross amount.

## 4. Matching hierarchy

1. Order, invoice, or bank reference
2. Exact amount
3. Exact date
4. Counterparty or business description

Multiple product lines may be aggregated only when they belong to the same business document. Unrelated transactions are not combined to force a match.

## 5. Variance layers

The cumulative difference is decomposed into:

`opening carryover + cross-period correction + current-period new variance`

This prevents timing differences from being mistaken for permanent accounting differences.

## 6. Explanation standard

Each exception records:

- date and document reference;
- Company A and Company B amounts;
- formula-driven difference;
- each party's calculation;
- the exact cause supported by the source rows;
- recommended evidence or corrective action;
- reconciliation status.

## 7. Precision

Source precision is retained throughout the analysis. The report distinguishes exact results, source-summary truncation, and the final amount rounded to two decimal places.

## 8. Verification

The final result is checked through three independent routes whenever balances are available:

1. difference between occurrence totals;
2. period bridge from opening to closing;
3. same-cut-off ending-balance difference.
