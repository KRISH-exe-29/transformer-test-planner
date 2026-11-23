# Transformer Test Planner

Plan the IEC 60076 tests for every power transformer unit in a work order, track each test from pending to completed, and give the test bay a ready-to-use Excel schedule.

**▶ [Open the app](https://transformer-test-planner.vercel.app)**

- Starts with 40 standard tests already listed, from ratio and winding resistance to tan delta, impulse, heat run and sound level. You can add, rename or remove tests.
- Each test gets a day, a shift (day or night), a unit and a type: routine, type or special.
- Mark each entry Pending, In Progress, Completed or Failed, and see progress per unit on the dashboards.
- One click exports the schedule to `Test_Schedule_<work order>_<date>.xlsx`.
- Everything is saved in your browser, with no login and no server.

## Quick start

```bash
git clone https://github.com/KRISH-exe-29/transformer-test-planner.git
cd transformer-test-planner
npm install && npm run dev
```

Open http://localhost:3000. Enter the work order details (number, customer, rating, voltage, cooling type), pick a day and a unit, add tests, then export to Excel.

## How to use it

1. **Job info.** Fill in work order number, customer, transformer rating, voltage level, cooling type and number of windings. They appear in the Excel header.
2. **Days and units.** The plan starts with Day 1 to Day 10 and Unit 1. Add or remove days and units as needed.
3. **Schedule.** Pick a day, then add tests with their unit, shift and test type.
4. **Track.** Update each entry's status as the test runs. The progress and unit status dashboards update right away.
5. **Export.** Download the schedule as Excel for the test bay.

Data is stored in `localStorage` (keys prefixed `ttp_`), so it stays in the browser you used. Clearing site data clears the plan.

## Tech stack

Next.js 16 · React 19 · TypeScript · Tailwind CSS · Recharts · SheetJS (`xlsx-js-style`) · Framer Motion. Deployed on Vercel.

## Project layout

```
app/          page and layout
components/   job form, day/unit selectors, schedule table, dashboards, Excel export
data/         default test list, test types, shifts and statuses
lib/store.tsx app state and localStorage persistence
```

## Scripts

| Command | What it does |
|---|---|
| `npm run dev` | Development server on port 3000 |
| `npm run build` | Production build |
| `npm start` | Serve the production build |
| `npm run lint` | ESLint |
