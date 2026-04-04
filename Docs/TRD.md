# TRD.md — Technical Requirements

## Stack
- **Format:** Single HTML file (no build step, no server, no dependencies to install)
- **JS Libraries:** Chart.js 4.4.x (CDN) for charts. No other external JS.
- **CSS:** Inline styles using CSS custom properties (design tokens). No Tailwind, no external CSS.
- **Data:** Embedded JSON objects in `<script>` tags. Updated manually or via scheduled task.
- **Target:** Opens in any modern browser. Works offline after first load (CDN scripts cached).

## Architecture
```
command_center.html          ← Single file, all code inline
├── <style>                  ← Design tokens + all CSS
├── <main>                   ← HTML structure (semantic, accessible)
├── <script> DATA            ← JSON data blocks (revenue, bookings, events, market)
└── <script> APP             ← Rendering logic, chart setup, interactivity
```

## Data Models

### MonthlyData
```javascript
{
  month: "2026-04",
  revenue: { paid: 0, upcoming: 2907.59, total: 2907.59 },
  adr: 145.53,
  occupancy: 0.80,
  bookings: 4,
  views: null,
  bookingRate: null,
  rating: 5.0,
  reviewCount: 22
}
```

### Booking
```javascript
{
  guest: "Pat",
  checkIn: "2026-04-02",
  checkOut: "2026-04-04",
  nights: 2,
  payout: 265.00,
  status: "confirmed" // confirmed | pending | completed | cancelled
}
```

### Event
```javascript
{
  name: "Capital Pride",
  startDate: "2026-06-12",
  endDate: "2026-06-21",
  pricingOverride: 265,
  overrideSet: true,
  category: "festival" // festival | holiday | concert | conference | sports
}
```

### MarketData
```javascript
{
  source: "PriceLabs Revenue Estimator Pro",
  date: "2026-04-03",
  annualRevenue: { p50: 22300, p25: 14000, p75: 30000 },
  monthlyRevenue: 1862,
  adr: 100,
  occupancy: 0.68,
  activeListings: 372,
  marketCategory: { midscale: 0.52, upscale: 0.27 }
}
```

## Design Token Source
Use the Airbnb-inspired tokens already defined in command_center.html (--rausch, --hof, --foggy, --spruce, --ondo, --arches, etc.). See DESIGN.md for full spec.

## Rules
- Do not introduce new CDN dependencies without approval
- All data lives in clearly labeled `<script>` blocks at the bottom of the file
- No fetch() calls — everything is local/embedded
- HTML must be semantic (sections, headings, nav, main)
- Minimum font size: 12px
- All interactive elements must have hover/focus states
- Keep total file size under 200KB
