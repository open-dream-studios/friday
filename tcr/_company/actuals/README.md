# `_company/actuals/` — harvested cross-job data

What actually happened on finished jobs, harvested into a queryable
form. Per-job-type duration baselines, common change-order reasons,
weather-day rates, etc. Cross-job learning fuel.

**P9 territory.** This folder is empty during P1–P8. Don't put anything
here yet; we'll design the schema once we have real finished-job data
to harvest from.

## What this becomes (sketch, not committed)

```
actuals/
  2026-Q2_addition_durations.json    ← finished-job task durations
  change_orders/                     ← what changed mid-job and why
  weather_days_2026.json             ← weather-day frequency by month
```

The contract isn't locked yet. We pick it when P9 starts.
