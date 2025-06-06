![GrowCube HA](https://img.shields.io/badge/GrowCube-Automated-green?style=flat-square&logo=home-assistant)[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg?style=flat-square)](https://hacs.xyz)

# 🌱 GrowCube Home Assistant Automation with extra UI Views etc.

This package provides complete automation, dashboards, alerts, and manual controls for GrowCube irrigation systems inside Home Assistant.

## ✅ Features
- Automatic watering per plant (A–D) with pause and moisture check
- Manual watering dashboard with per-plant buttons
- Central watering control (pause, cycle count)
- Moisture history graphs
- Alerts for low moisture and empty water tank
- Fully mobile-optimized dashboard layout
- Blueprint & script-based design for easy reuse

---

## 📁 Included

- `blueprints/automation/growcube_auto_water.yaml` – Reusable automation blueprint
- `scripts/water_growcube_plant_on_demand.yaml` – Manual watering script
- `dashboards/growcube_dashboard.yaml` – Full UI dashboard with controls and graphs
- `dashboards/growcube_alerts.yaml` – Alerts-only view for mobile/critical status
- `README.md` – This file

---

## 🔧 Setup Instructions

### 1. Prerequisites

- Home Assistant (latest version)
- HACS installed with:
  - Mini Graph Card (`kalkih/mini-graph-card`)
  - Expander Card (`custom-cards/expander-card`)
  - Elecrow GrowCube integration for Home Assistant (`https://github.com/jonnybergdahl/HomeAssistant_Growcube_Integration`)

### 2. Clone or Copy Files

Copy the contents of this repository into your Home Assistant config directory:

```
/config/
│
├── blueprints/automation/growcube/growcube_auto_water.yaml
├── scripts/water_growcube_plant_on_demand.yaml
├── dashboards/growcube_dashboard.yaml
├── dashboards/growcube_alerts.yaml
└── README.md
```

### 3. Import Blueprint

- Go to **Settings → Automations → Blueprints → Import Blueprint**
- Browse to `growcube_auto_water.yaml` and load it

### 4. Load Script

- In **Settings → Scripts → Edit in YAML**, paste contents of `water_growcube_plant_on_demand.yaml`

### 5. Add Dashboards

- Add views to your UI using `growcube_dashboard.yaml` and `growcube_alerts.yaml`
- Use **Raw Editor** or **Storage mode** and paste each view YAML

### 6. Create Helpers

In **Settings → Helpers**, create:

- `input_number.watering_pause_minutes` (1–10, default 2)
- `input_number.watering_max_cycles` (1–30, default 20)
- `input_number.watering_low_threshold` (1–100)
- `input_number.watering_high_threshold` (1–100)
---

## 🧪 Test It

1. Simulate dry soil (manually lower a moisture sensor reading)
2. Use dashboard to trigger watering
3. Check for notification, moisture rise, graph update

---

## ❤️ Credits

Built with 💧 by the Home Assistant + GrowCube community.

---

## ☕ Support This Project

If you found this useful, you can support future work here:

<a href="https://buymeacoffee.com/dstasiak" target="_blank">
  <img src="https://img.shields.io/badge/Buy%20me%20a%20coffee-%23FFDD00.svg?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me A Coffee">
</a>

---
