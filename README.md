<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=32&pause=1000&color=2E8B57&center=true&vCenter=true&width=600&lines=AgroMart;Farm+to+Market%2C+Intelligently." alt="AgroMart" />
</div>
<br/>
<div align="center">
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Status](https://img.shields.io/badge/Status-Completed-2E8B57?style=for-the-badge)
</div>
---
## The Problem
Bangladesh runs on agriculture — but farmers don't know if their goods will arrive fresh, sell fairly, or reach the buyer at all. Buyers have no idea where their food came from or why the price changed overnight.
AgroMart tracks every shipment from farm to warehouse: real-time weather disruptions, cold-chain temperature breaches, automatic spoilage detection, and a full audit trail of every decision the system made.
---
## Screenshots
| Dashboard | Orders | Shipments |
|:-:|:-:|:-:|
| ![](screenshots/dashboard1.jpeg) | ![](screenshots/order.jpeg) | ![](screenshots/Shipment.jpeg) |
| Weather Events | Heat Monitor | Spoilage |
|:-:|:-:|:-:|
| ![](screenshots/weather.jpeg) | ![](screenshots/Heat.jpeg) | ![](screenshots/Spoilage.jpeg) |
| Price Audit | Provenance | Products |
|:-:|:-:|:-:|
| ![](screenshots/PriceAudit.jpeg) | ![](screenshots/Provenance.jpeg) | ![](screenshots/Product.jpeg) |
---
## Database
![Schema](screenshots/Schema.PNG)
14 tables across three layers — **core** (farmers, shipments, orders), **monitoring** (IoT sensors, weather, spoilage), and **audit** (price history, provenance events). Every update is traceable.
---
## How It Works
Shipment creation triggers validation — bad data never enters the system. During transit, IoT sensors watch temperature; a breach auto-logs a provenance event. A flood in Sylhet? The system calculates delay hours and price impact by severity, and updates every affected shipment automatically. Spoilage on arrival adjusts price, deducts stock, and records the loss — all inside a single trigger.
Everything ends up in `PROVENANCE_EVENT`. Pull any shipment and see the full story.
---
## Triggers
| Trigger | Purpose |
|---|---|
| `trg_weather_before` | Calculates price impact from a weather event |
| `trg_weather_after` | Updates all shipments disrupted by that event |
| `trg_shipment_validate` | Rejects invalid inserts before they land |
| `trg_food_spoilage_calc` | Computes loss, adjusts price, deducts stock |
| `trg_order_status` | Audits every order status change |
---
## Provenance Queries
Five queries for tracing the supply chain end-to-end — full shipment timelines, critical incidents in the last 30 days, weather delay cost analysis, product spoilage patterns, and farmer-level incident reports.
---
## Team
Nuran Farhana Prova · Shakibul Hassan · Wasimul Bari Rahat
# @babel/core
> Babel compiler core.
See our website [@babel/core](https://babeljs.io/docs/babel-core) for more information or the [issues](https://github.com/babel/babel/issues?utf8=%E2%9C%93&q=is%3Aissue+label%3A%22pkg%3A%20core%22+is%3Aopen) associated with this package.
## Install
Using npm:
```sh
npm install --save-dev @babel/core
```
or using yarn:
```sh
yarn add @babel/core --dev
```
