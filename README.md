<div align="center">

# 🌾 AgroMart
### *Farm to Market, Intelligently.*

[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)](https://supabase.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Status](https://img.shields.io/badge/Status-Completed-2E8B57?style=for-the-badge)](#)

*A supply chain intelligence platform for Bangladesh's agricultural sector — tracking every shipment from field to buyer with real-time monitoring, spoilage detection, and a tamper-proof audit trail.*

</div>



## 📌 The Problem

Bangladesh runs on agriculture — yet farmers have no visibility into whether their goods will arrive fresh, sell at a fair price, or reach buyers at all. On the other side, buyers have no way to know where their food came from or why prices shifted overnight.

**AgroMart** closes that gap. It tracks every shipment from farm to warehouse, capturing real-time weather disruptions, cold-chain temperature breaches, and automatic spoilage detection — with a full, immutable audit trail of every system decision.


## 🖼️ Screenshots

| Dashboard | Orders | Shipments |
|:-:|:-:|:-:|
| ![Dashboard](screenshots/dashboard1.jpeg) | ![Orders](screenshots/order.jpeg) | ![Shipments](screenshots/Shipment.jpeg) |

| Weather Events | Heat Monitor | Spoilage Detection |
|:-:|:-:|:-:|
| ![Weather](screenshots/weather.jpeg) | ![Heat](screenshots/Heat.jpeg) | ![Spoilage](screenshots/Spoilage.jpeg) |

| Price Audit | Provenance Trail | Products |
|:-:|:-:|:-:|
| ![Price Audit](screenshots/PriceAudit.jpeg) | ![Provenance](screenshots/Provenance.jpeg) | ![Products](screenshots/Product.jpeg) |



## 🗄️ Database Architecture

![Schema](screenshots/Schema.PNG)

**14 tables** organized across three responsibility layers:

| Layer | Tables | Purpose |
|---|---|---|
| **Core** | `FARMER`, `PRODUCT`, `SHIPMENT`, `ORDER`, `WAREHOUSE` | Entities and transactions |
| **Monitoring** | `IOT_SENSOR`, `SENSOR_READING`, `WEATHER_EVENT`, `FOOD_SPOILAGE` | Real-time event capture |
| **Audit** | `PRICE_HISTORY`, `PROVENANCE_EVENT`, `ORDER_AUDIT` | Immutable decision logs |

Every state change is traceable. Nothing is ever silently overwritten.



## ⚙️ How It Works

### Shipment Lifecycle


Shipment Created → Validated by trigger → In Transit
       ↓                                      ↓
  Bad data rejected               IoT sensors watch temperature
                                          ↓
                              Breach detected → Provenance event logged
                                          ↓
                              Weather event (e.g. Sylhet flood)
                                          ↓
                         Delay hours + price impact calculated
                         All affected shipments auto-updated
                                          ↓
                              Arrival: Spoilage detected?
                                   ↙         ↘
                                 Yes           No
                                  ↓
                     Price adjusted · Stock deducted
                     Loss recorded · Provenance updated


Every action — automated or manual — ends up in `PROVENANCE_EVENT`. Pull any shipment ID and get its full story.



## 🔁 Triggers

| Trigger | Fires | Purpose |
|---|---|---|
| `trg_weather_before` | `BEFORE INSERT` on `WEATHER_EVENT` | Calculates price impact from event severity |
| `trg_weather_after` | `AFTER INSERT` on `WEATHER_EVENT` | Updates all shipments disrupted by the event |
| `trg_shipment_validate` | `BEFORE INSERT` on `SHIPMENT` | Rejects malformed or invalid inserts |
| `trg_food_spoilage_calc` | `AFTER INSERT` on `FOOD_SPOILAGE` | Computes loss, adjusts price, deducts stock |
| `trg_order_status` | `AFTER UPDATE` on `ORDER` | Audits every order status transition |


## 🔍 Provenance Queries

Five analytical queries for end-to-end supply chain tracing:

1. **Full Shipment Timeline** — every event for a given shipment, ordered chronologically
2. **Critical Incidents (Last 30 Days)** — high-severity disruptions across all active shipments
3. **Weather Delay Cost Analysis** — financial impact broken down by event type and region
4. **Product Spoilage Patterns** — which products spoil most, at which warehouses, and why
5. **Farmer Incident Reports** — per-farmer breakdown of disruptions, losses, and recoveries



## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [Supabase](https://supabase.com/) account (or a local PostgreSQL instance)

### Setup

```bash
# Clone the repository
git clone https://github.com/your-org/agromart.git
cd agromart

# Install dependencies
npm install

# Configure environment
cp .env.example .env
# Add your Supabase URL and anon key to .env

# Run database migrations
npm run db:migrate

# Seed sample data (optional)
npm run db:seed

# Start the development server
npm run dev

##  Team

| Name | Role |
|---|---|
| **Nuran Farhana Prova** | Database Design · Monitoring Layer |
| **Shakibul Hassan** | Core Schema · Trigger Logic |
| **Wasimul Bari Rahat** | Audit System · Provenance Queries |



## 📄 License

This project was developed as an academic database systems project. Contact the team for usage permissions.



<div align="center">
  <sub>Built with 🌱 for Bangladeshi farmers and the buyers who depend on them.</sub>
</div>
