# PRD.md — Product Requirements

## Feature 1: Revenue Dashboard (MVP)
- **Input:** Monthly revenue data (from Airbnb CSV export or manual entry)
- **Process:** Calculate YTD totals, monthly averages, gap to $3,800 target, trend direction
- **Output:** Score cards (revenue, ADR, occupancy, booking rate, rating), revenue chart, month-over-month table
- **Done when:** Dashboard shows accurate current-month and YTD data with visual indicators (green/amber/red) relative to targets

## Feature 2: Pricing Calendar
- **Input:** PriceLabs pricing data, event calendar from dc_airbnb_playbook.md
- **Process:** Render a month-view calendar showing nightly prices, booked dates, event overlays, and min-stay indicators
- **Output:** Visual calendar with color-coded demand levels, event badges, and price vs. market-median comparison
- **Done when:** User can see any month's pricing at a glance and identify underpriced dates

## Feature 3: Booking Pipeline
- **Input:** Upcoming reservation data (guest name, dates, payout, status)
- **Process:** Sort by check-in date, calculate expected revenue for next 30/60/90 days
- **Output:** Table of upcoming bookings with revenue projections, gap analysis vs. target
- **Done when:** User sees every confirmed and pending booking with total expected income

## Feature 4: Action Center
- **Input:** Checklist items from dc_airbnb_playbook.md and pricelabs_setup_and_insights.html
- **Process:** Categorize by urgency (today, this week, this month), track completion state
- **Output:** Interactive checklist with progress bar, overdue highlighting, category filters
- **Done when:** User can check off items and see overall completion percentage

## Feature 5: Guest Toolkit
- **Input:** Message templates from playbook, check-in instructions, review response templates
- **Process:** Display templates with copy-to-clipboard functionality
- **Output:** Tabbed interface: Pre-booking messages, Check-in instructions, Mid-stay check, Checkout, Review responses
- **Done when:** User can copy any template in one click

## Feature 6: Market Intelligence
- **Input:** PriceLabs Revenue Estimator data, comp-set data, DC market benchmarks
- **Process:** Display market position (percentile), comp ADR/occupancy, seasonal trends
- **Output:** Cards showing: your ADR vs market, your occupancy vs market, revenue percentile, seasonal outlook
- **Done when:** User understands how they compare to the market without opening PriceLabs

## Feature 7: Monthly Report Generator
- **Input:** That month's revenue, bookings, reviews, pricing data
- **Process:** Auto-populate a monthly performance summary with key metrics and insights
- **Output:** Printable/exportable monthly report section
- **Done when:** User can generate a monthly snapshot by updating a few numbers

## Feature 8: Event & Seasonal Alerts
- **Input:** DC events calendar from playbook, current date
- **Process:** Identify upcoming events within 30/60/90 days, check if pricing overrides are set
- **Output:** Alert cards: "Pride is in 72 days — $265/night override is SET" or "Foo Fighters in 45 days — NO override set"
- **Done when:** No peak event pricing opportunity is missed
