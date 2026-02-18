# MEMORY.md - Ledger's Long-Term Memory

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
- Don't reverse-calculate gross from net - use the actual gross from Excel

### Math Calculations
- We pay bar based on **net** (not gross)
- Gross is for internal tracking only
- Viator: Use the CSV "TOTAL PAYMENT" as net ($2,659.30)
- Viator gross from Excel: $3,799.00 (but we only got $2,659.30 net)

### Required Data Per Booking
- Booking date (Sale date for Viator)
- Activity/Arrival date
- Guest count
- Guest name (if available)
- Gross rate
- Platform fee
- Net rate

### Commission Calculation
- 10% of net = bar's commission
- If total sales < $15k → apply $1,500 minimum
- Add liquor costs
- Total owed to bar

### Monthly Process
1. Get raw payout files from 4 platforms
2. Parse each platform's format:
   - Viator: Excel with customer names, use CSV for net total
   - Airbnb: CSV - filter "Experience" rows only (not Payout rows)
   - GetYourGuide: CSV - filter positive amounts only
   - Bokun: CSV - filter CONFIRMED/ARRIVED only
3. Sum all net revenue
4. Calculate 10% commission
5. Apply $1,500 minimum if under $15k
6. Add liquor costs
7. Create report in Google Sheets with:
   - Summary section with totals
   - Booking details section
   - Each platform separated with headers
   - Platform subtotals and grand total
   - Dollar signs on all money values
8. Save to Drive: Charleston Commission Reports > [Year] folder
9. Keep test versions in separate "Testing" folder

### Sheet Layout (Gospel Format - V5)
- Row 1: Title
- Row 3-9: Summary table (Platform, Gross, Fee, Net, Bookings, Guests)
- Row 11: TOTALS
- Row 13-18: Commission calculation
- Row 20+: Booking details
  - Platform header
  - Column headers: Booking Date, Arrival Date, Guests, Guest Name, Gross Rate, Fee, Net Rate
  - Individual bookings
  - Platform TOTAL row
- Grand TOTAL at very bottom

### Drive Organization
- Main folder: Charleston Commission Reports
- Year subfolders: Charleston_Commission_Reports_2023, 2024, 2025, 2026
- Testing subfolder: Jan Commission Report - Testing (for drafts)

### Key Learnings (Session 2026-02-18)
1. Always use the CSV payout for Viator net total, not calculated
2. Each platform has different date formats - normalize to MM/DD/YYYY
3. Don't assume fee % - verify from actual data (Airbnb is 20%, not 25%)
4. Keep test versions separate from official reports
5. Dollar signs important for readability
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
