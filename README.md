# DealDrop — NearbyDeals Hack

A responsive hyperlocal flash-deal platform built to match the supplied 3-page college problem brief.

## Features implemented
- Customer deal discovery feed with 16 seeded offers across Dining, Wellness, Fitness, Entertainment and Services.
- Search, category tabs and 1 km / 3 km / 5 km radius filters.
- Live expiry countdowns driven by server timestamps.
- One-click voucher claims with unique alphanumeric tokens, copy action and a simulated QR display.
- Voucher quota decrementing and two-hour claim holds. Expired held claims are returned to the public quota when the API is next accessed.
- Merchant publishing dashboard with Happy Hour, Buy One Get One and Flat Discount templates.
- Merchant metrics for views, claimed vouchers, estimated walk-ins and active offers.
- Happy-hour demo toggle, OpenStreetMap map pins and voucher sharing.
- Responsive desktop and mobile layouts.

## Requirements
- Node.js 18+ and npm
- Internet connection for Google Fonts, Leaflet and OpenStreetMap tiles (the app itself runs locally).

## Run locally
1. Extract the project folder.
2. Open a terminal in the `dealdrop` folder.
3. Run `npm install`.
4. Run `npm start`.
5. Open `http://localhost:3000` in your browser.

The server creates `data/db.json` automatically on first run. This file stores deals and claims. Delete it to reset to the original 16 demo deals (stop the server first).

## Demo flow
1. On Discover, search for coffee, select a category and change the distance radius.
2. Claim a voucher. The remaining quota decreases and a voucher modal displays the generated code and simulated QR.
3. Open My vouchers to view held/expired claims.
4. Open Merchant studio to see performance counters and publish a new offer.
5. Turn on the Happy Hour toggle to apply the demo dining promotion.
6. Open Explore map to see merchant pins on the neighborhood map.

## Notes
- The brief's example districts are represented by sample Hyderabad localities (Kompally, Suchitra, Miyapur and Maisammaguda). Distances and map pins are demo data, not live GPS measurements.
- Voucher redemption is simulated for the hackathon demo; there is no cashier scanning or customer authentication service.
- The QR is a visual demo code, not a standards-compliant payment or redemption QR.
- The server uses a lightweight JSON file store. The brief allows SQLite / LocalStorage; this keeps setup simple for a local college demo.
- The Happy Hour switch is a demonstrator control. A production deployment should use a scheduled server job and merchant-configured quiet hours.
