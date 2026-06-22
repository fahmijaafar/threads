# Financial Reports Module

## Objective

Create a new **Financial Reports** section for the bookkeeping system.

The section should be available under the main navigation menu and should allow users to view financial reports for the currently selected company.

The page must contain **three tabs**:

1. Profit & Loss
2. Balance Sheet
3. Cash Flow Statement

All reports must support:

* Company selection (current company context)
* Date range filtering
* Export to PDF (placeholder implementation acceptable)
* Responsive layout
* Dark mode support
* Currency formatting consistent with the rest of the application

---

# Tab 1: Profit & Loss

## Purpose

Provide a summary of business performance for the selected period.

## Structure

### Revenue

Display revenue grouped by sales channel.

Sales channels are dynamic and must be retrieved from the channels created by the user.

Examples:

* Shopee
* Lazada
* TikTok Shop
* Direct Sales
* Website
* Any custom channel created by the user

Display:

| Sales Channel | Amount |
| ------------- | ------ |
| Shopee        | RM X   |
| Lazada        | RM X   |

### Total Revenue

Display the sum of all sales channels.

---

### Expenses

Display expenses grouped by expense category.

Expense categories must use the predefined categories available in the system.

Examples:

* Inventory Purchases
* Marketing
* Utilities
* Internet
* Software Subscription
* Transportation
* Salary
* Rental
* Miscellaneous

Display:

| Expense Category | Amount |
| ---------------- | ------ |
| Marketing        | RM X   |
| Utilities        | RM X   |

### Total Expenses

Display the sum of all expense categories.

---

### Net Profit / Loss

Formula:

Net Profit/Loss = Total Revenue - Total Expenses

Display prominently using a summary card.

---

# Tab 2: Balance Sheet

## Purpose

Provide a snapshot of the company's financial position.

## Structure

### Assets

#### Cash & Bank

Calculate using current balances from all company bank accounts.

Formula:

Sum(Current Bank Account Balances)

Display individual bank accounts and total.

Example:

| Account          | Balance |
| ---------------- | ------- |
| Maybank Business | RM X    |
| CIMB Current     | RM X    |

Total Cash & Bank = Sum of all balances

---

#### Accounts Receivable (AR)

Calculate from unpaid customer invoices.

Include invoices with statuses:

* Pending
* Partially Paid
* Overdue

Formula:

Sum(Remaining Outstanding Amount)

---

#### Inventory

Calculate inventory value using:

Cost Price × Current Stock Quantity

Formula:

Inventory Value = Σ(Product Cost Price × Current Quantity)

---

### Total Assets

Formula:

Cash & Bank + Accounts Receivable + Inventory

---

### Liabilities

#### Accounts Payable (AP)

Calculate from supplier bills.

Include bills with statuses:

* Pending
* Partially Paid
* Overdue

Formula:

Sum(Remaining Outstanding Amount)

---

### Total Liabilities

Currently equal to Accounts Payable.

Structure should allow future liability categories to be added.

---

### Equity

#### Current Period Profit

Use Net Profit/Loss from the selected reporting period.

Formula:

Equity = Current Period Net Profit/Loss

---

### Total Liabilities & Equity

Formula:

Accounts Payable + Current Period Profit

Display side-by-side with Total Assets.

---

# Tab 3: Cash Flow Statement

## Purpose

Show actual cash movement during the selected period.

Use only completed and paid transactions.

Do not use unpaid invoices or unpaid bills.

---

### Cash Inflows

Include:

* Paid Sales
* Customer Payments
* Other Income

Display grouped by source.

Example:

| Source       | Amount |
| ------------ | ------ |
| Shopee Sales | RM X   |
| Direct Sales | RM X   |

---

### Total Cash Inflows

Formula:

Sum(All Cash Inflows)

---

### Cash Outflows

Include:

* Supplier Payments
* Inventory Purchases
* Operating Expenses
* Salary
* Utilities
* Internet
* Software Subscription
* Rental
* Transportation
* Miscellaneous Expenses

Display grouped by category.

---

### Total Cash Outflows

Formula:

Sum(All Cash Outflows)

---

### Net Cash Flow

Formula:

Total Cash Inflows - Total Cash Outflows

---

### Opening Balance

Use total bank account balance at the beginning of the selected date range.

---

### Closing Balance

Formula:

Opening Balance + Net Cash Flow

Display prominently.

---

# UI Requirements

## Summary Cards

Each report tab should contain summary cards at the top.

Examples:

Profit & Loss:

* Total Revenue
* Total Expenses
* Net Profit/Loss

Balance Sheet:

* Total Assets
* Total Liabilities
* Equity

Cash Flow:

* Total Inflows
* Total Outflows
* Closing Balance

---

## Tables

Use consistent table styling throughout all reports.

Requirements:

* Sortable columns
* Currency formatting
* Empty-state handling
* Loading state
* Error state

---

## Future Extensibility

Design the implementation so additional report types can be added later, including:

* Trial Balance
* General Ledger
* Account Ledger
* Tax Reports
* SST Reports

Avoid hardcoding report tabs or report data structures.
