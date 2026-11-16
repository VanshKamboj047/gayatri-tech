GAYATRI TECH RIDER — FINAL FORM-ANALYSED UI PROTOTYPE
====================================================

Open index.html in Chrome / Edge. No build step required.

This version deepens the data-entry forms using the supplied 37-page
"Manufacturing ERP – Final Technical Blueprint".

Detailed forms included:
- Customer / Supplier master
- Sales Order with repeatable specification line items and totals
- Purchase Order with repeatable material lines
- GRN with ordered / previously received / received / accepted / rejected quantities,
  supplier invoice, unit cost, batch and QC posting status
- Manual Stock Adjustment with category, direction, reason, batch, warehouse,
  location, quantity, unit, evidence and approval fields
- Specification-wise BOM with version/effective dates and repeatable BOM items
- Production Job Card
- Daily Production Entry with output, actual batch consumption, material returns,
  scrap/process loss, operator allocations, rate snapshots and reconciliation
- QC Inspection with parameter measurements and accepted/rejected/rework disposition
- Dispatch with repeatable finished-batch lines and delivery confirmation
- Labour Rate Card with operator + machine + specification + effective dates
- Labour advance/payment with separate transaction types
- Invoice with line items and tax fields
- Payment receipt/payment with invoice allocations
- Machine, user/role, scrap and scrap sale forms

Design / business rules represented:
- Master records should be selected/reused across modules.
- Standard consumption lives in BOM; actual consumption is entered in Production.
- Material issue reduces raw stock; material return increases raw stock.
- GRN accepted quantity is batch tracked; rejected quantity remains separate.
- Finished stock becomes dispatchable only after finished goods QC approval.
- Labour earnings are based on approved allocated production quantity and historical rate.
- Stock adjustment requires reason, source evidence and approval.
- Payment allocation cannot exceed payment amount.
- Posted GRN, Production and Dispatch are corrected by reversal/adjustment, not silent edit/delete.
- Stock balances are updated together with stock ledger within a database transaction.
- Audit log records user, action, module, record and old/new values.

IMPORTANT
- This is a front-end design prototype with illustrative data only.
- It is NOT connected to Laravel REST APIs or MySQL.
- Dynamic forms, line add/remove and browser required-field checks are demo interactions;
  nothing is persisted and no actual stock/ledger posting happens.
- Server-side validation, permissions, calculations, database transactions,
  unique document numbering and audit logging must be implemented in Laravel.
- Carding Wire finished unit and the other technical decisions on blueprint page 37
  remain to be confirmed before implementation.
- Any extra UI field beyond the schema is labelled as an operational form field,
  not claimed to be a finalized database column.
