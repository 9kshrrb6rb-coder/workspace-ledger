# Financial Data Index - Both Businesses

## Alchemix Financial Records

### Drive Folder Structure
- Root: Alchemix Financial Records
  - Bank Statements
  - Receipts
  - Invoices
  - Orders
  - Profit & Loss
  - Tax Documents
  - Commission Reports
  - Agreements

### Key Files Found
- Orders exports (multiple CSVs - 2025)
- Bank statements (StatementImage PDFs)
- Receipts (PDF)
- Invoices from various vendors
- MSA agreements
- Tax documents (W9 forms)

### Links
- Receipt Upload Sheet: https://docs.google.com/spreadsheets/d/1Q4pL4tUVXhBCYNm01AGtjY5rzONJQO2bEMnypUvxbco/edit

## Sip History Financial Records

### Drive Folder Structure
- Root: Sip History Financial Records
  - Bank Statements
  - Receipts
  - Invoices
  - Orders
  - Profit & Loss
  - Tax Documents
  - Commission Reports
  - Agreements
  - Inventory

### Key Files Found
- Commission Reports: 2024-2025 monthly
- Pay Period Reports: CHS (Charleston), NSH (Nashville)
- Weekly Inventory: Multiple weeks
- Bank Statements: Viator payouts (GIS files)
- Budget 2026

### Links
- Receipt Upload Sheet: https://docs.google.com/spreadsheets/d/1w3IeI0F9KSfO21kAV-f96QGleB_T6t8zg1BpYeopdmA/edit
- Commission Reports Folder: Charleston Commission Reports > 2026

## Receipt Upload System
Both sheets have:
- Date column
- Vendor column
- Category column (with dropdown options)
- Amount column
- Description column
- Receipt Link column (for Drive links)
- Business Purpose column
- Notes column

Categories include:
- Operating: Inventory/Supplies, Labor/Payroll, Rent/Utilities, Marketing, Equipment, Travel, Professional Services, Insurance, Licenses
- COGS: Ingredients, Packaging
- Other: Miscellaneous

## Cron Job
- Night session: Every 2 hours to continue organizing
- Job ID: 3fa23c12-b5b5-4e0f-a4ab-7177c3539993

## Next Steps
1. Move historical files to organized folders
2. Parse bank statements
3. Create expense tracking sheets
4. Automate receipt parsing
