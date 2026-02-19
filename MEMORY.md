# MEMORY.md - Ledger's Long-Term Memory

## Important Rules (from user)

### Google Sheets
- **NEVER ask the user to add things to Google Sheets manually** - that's Ledger's job
- I must authenticate gog and manage all spreadsheet updates myself
- If gog isn't working, I need to fix it - not ask user to do manual work

---

## Financial Organization Project

### Current Status (Feb 18, 2026)
- Local folder structure created for financial files
- Viator payment file parsed ($604.52 for Jan 2026)
- Google Drive folders set up (need gog auth to continue)
- Cron job running every 2 hours to continue work

### Local Financial Files
**Location:** `workspace-ledger/financial-files/`
- viator/ - Viator payout files
- airbnb/ - Airbnb payout files
- stripe/ - Stripe transaction exports
- bokun/ - Bokun direct booking exports
- getyourguide/ - GetYourGuide payout files
- bank-statements/ - Bank statement PDFs
- receipts/ - Expense receipts
- invoices/ - Vendor invoices

### Recent Viator Payout (Feb 6, 2026)
- **Total:** $604.52
- **Period:** January 2026 arrivals
- **Bookings:** 8 reservations
- **File:** viator_payment.xlsx (now organized)

### Receipts Saved
- Calabria Brick Oven Pizzeria - $9.64 (Feb 18, 2026) - needs to be added to Google Sheet

---

## Commission Report Process

### Platform Fees
- Viator: 30%
- Airbnb: 20% (not 25% - confirmed from data)
- GetYourGuide: 25%
- Bokun (Direct): 0% (no platform fee)

### Data Sources
- Viator: Excel file with bookings → "Supplier NET price" is what we get paid
- Airbnb: CSV export → "Gross earnings" + "Service fee" = gross
- GetYourGuide: CSV export → "Retail Price" - "Commission Amount" = net
- Bokun: CSV export → "Supplier NET price" is what we get paid (no fee)

### IMPORTANT: Viator Nuance
- Viator Excel shows FULL gross (what guest paid)
- Viator CSV payout shows NET after their 30% cut
- The CSV "TOTAL PAYMENT" is the actual cash deposited
- Don't reverse-calculate gross from net - use the actual gross if needed

## Parsing Tips
1. Always extract ALL numeric values first, then identify which are fees/commissions
2. Platform fees are on GROSS, not NET - so multiply net by (1/(1-fee)) to get gross
3. Look for "NET", "TOTAL", "PAYOUT", "COMMISSION" keywords
4. Check for multiple tabs/sheets in Excel files
5. Sign signs important for readability
6. Separate platforms clearly with headers and subtotals
7. Guest names not available in GetYourGuide export
8. Bokun bookings sometimes span Dec-Jan - filter by activity date

## Locations

### Faculty Lounge (Old - Nayda)
- 2022-2024
- naydamf@gmail.com

### Frontier Lounge (Current - Neil)
- Nov 2024-present
- neilwlykins@gmail.com

## Google Accounts
- Sip History: tommy@siphistory.co
- Alchemix: tommy@alchemix.co

## gog CLI Authentication
- **IMPORTANT:** I must maintain gog authentication so I can access Google Sheets
- If authentication fails, I need to fix it - NOT ask user to do manual work
- Never ask user to manually add data to spreadsheets - that's my job

### Current Status (Feb 18, 2026)
- gog has `GOG_KEYRING_PASSWORD=test` working for keyring bypass
- Token exists for tommy@alchemix.co but only has gmail (no sheets/drive)
- **NEED TO RE-AUTH** with full permissions

### Auth Command (when user at computer)
```bash
export GOG_KEYRING_PASSWORD=test
gog auth add tommy@alchemix.co --services gmail,drive,sheets
```

### Long-term Solution
- Set up service account for agent (no browser needed)
- Or create dedicated Google Workspace account
