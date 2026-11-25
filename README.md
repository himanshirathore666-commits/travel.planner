# WanderPlan AI Frontend

A modern, responsive React.js frontend for the **AI Travel Itinerary Planner**, connected to the FastAPI backend running at `http://127.0.0.1:8000`.

---

## Features

- **Intuitive Planning Form**:
  - Destination input with quick-select popular destination presets (Tokyo, Paris, Rome, Bali, Kyoto, etc.).
  - Trip duration selector (1 to 30 days).
  - Estimated budget input with tier presets (`$800 Budget`, `$2000 Moderate`, `$4500 Luxury`).
  - Travel style cards (Cultural & Historic, Foodie & Culinary, Adventure & Outdoors, Relaxed & Leisure, Luxury & Wellness, Budget Backpacker).
  - Multi-select interactive interest tags + custom interest input to add personalized tags.
- **Budget Breakdown Cards**:
  - Total estimated trip cost with currency badge.
  - Category breakdown cards for Accommodation, Food & Dining, Activities & Tours, Local Transportation, and Miscellaneous Buffer.
  - Percentage distribution & allocated cost for each category.
  - Insider cost-saving recommendations.
- **Day-Wise Itinerary Cards**:
  - Interactive day selector pills ("Day 1", "Day 2", ... or "View All Days").
  - Day theme title and daily narrative overview.
  - Daily estimated spend badge.
  - Recommended meals breakdown (Breakfast, Lunch, Dinner spots).
  - Chronological activity cards (Morning, Afternoon, Evening) with specific locations, cost estimates, and insider tips.
  - Packing checklist and essential travel advice.
- **Saved Trips Drawer**:
  - Directly queries `http://127.0.0.1:8000/saved-trips` to display previous itineraries persisted in Supabase.
  - Real-time refresh button.
  - "Load Plan" button on any trip card to instantly load that itinerary into the active view.
- **Live Health Indicator**:
  - Pings `http://127.0.0.1:8000/health` to show real-time backend connection status.

---

## Getting Started

### Option 1: Instant Browser Preview (Zero Installation)

If Node.js is not yet installed on your system, you can run the application immediately using the included standalone React build:

1. Double-click or open [frontend/standalone.html](file:///c:/Users/rohit/OneDrive/Desktop/travel-itinerary-planner/frontend/standalone.html) in your browser (Chrome, Edge, Firefox, Brave).
2. Or serve it locally with Python:
   ```bash
   cd frontend
   python -m http.server 3000
   ```
   Then open `http://localhost:3000/standalone.html` in your browser.

---

### Option 2: Standard Vite Development Server (with Node.js)

When Node.js is installed on your system:

```bash
cd frontend
npm install
npm run dev
```

The application will be accessible at:
```
http://localhost:5173
```

---

## Component Architecture

- `src/App.jsx`: Main state coordinator (manages active itinerary, saved trips list, notifications, and scroll behavior).
- `src/services/api.js`: Fetch client connected to `http://127.0.0.1:8000/generate-itinerary` and `/saved-trips`.
- `src/components/Navbar.jsx`: Top navigation, backend online/offline ping badge, and saved trips drawer toggle with counter.
- `src/components/ItineraryForm.jsx`: Interactive travel form with destination presets, budget tiers, and interest pills.
- `src/components/BudgetCards.jsx`: 5-column breakdown of travel budget allocations and savings tips.
- `src/components/DayWisePlan.jsx`: Day tabs, chronological activities timeline, meal suggestions, and insider tips.
- `src/components/SavedTrips.jsx`: Slide-over drawer listing all saved itineraries from Supabase with one-click reload.
