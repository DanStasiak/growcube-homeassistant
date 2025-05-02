# GrowCube Home Assistant Integration

This project brings full GrowCube smart plant watering automation and dashboarding into Home Assistant, with multi-plant support, soil moisture tracking, manual triggers, visual dashboards, and intelligent notifications.

---

## Features

- ✨ Supports 4 plants (A–D)
- 📉 Historical moisture graphs (per plant)
- ⏳ Adaptive watering (until moisture ≥ 40%, with pause/cycle control)
- 🛠️ Input sliders for watering delay & retry limit
- 📣 Voice or push alerts on dry soil, empty tank, or missed improvements
- 🏠 Mobile-friendly dashboards with on-demand watering buttons
- 🔴 Critical alert view (low moisture, empty tank, failures)

---

## Requirements

### Hardware
- GrowCube controller (via Bluetooth to Home Assistant)

### Home Assistant Add-ons
- [HACS](https://hacs.xyz/) (Home Assistant Community Store)
- Bluetooth support (via ESPHome, USB dongle, or system)

### HACS Custom Cards (Frontend)
- [Mini Graph Card](https://github.com/kalkih/mini-graph-card)
- [Expander Card](https://github.com/custom-cards/expander-card) *(optional)*

---

## Installation

### 1. Add Helpers
In **Settings → Devices & Services → Helpers**, create:

- `input_number.watering_pause_minutes`
  - Min: 1, Max: 10, Step: 1, Initial: 2
- `input_number.watering_max_cycles`
  - Min: 1, Max: 30, Step: 1, Initial: 20

---

### 2. Import Script: `Water GrowCube Plant On Demand`

Go to **Settings → Automations & Scenes → Scripts → Add Script → Edit in YAML** and paste:

```yaml
# See scripts/water_growcube_plant_on_demand.yaml
```

---

### 3. Import Automation Blueprint
Place this file into:
```
/config/blueprints/automation/growcube/growcube_auto_water.yaml
```
Use the blueprint to auto-water each plant when dry.

---

### 4. Add Dashboards

#### GrowCube Summary View
Includes:
- Moisture graphs
- Manual watering
- Input sliders
- Water tank warning
- Last moisture update

#### GrowCube Alerts View
Includes:
- Tank empty alert
- Low soil moisture
- Warning logbook
- Moisture recovery tracking

Use the `dashboards/growcube-summary.yaml` and `dashboards/growcube-alerts.yaml` YAML files.

---

## Configuration Example

- **Moisture sensors:** `sensor.growcube_c75b31_moisture_a` ... `_d`
- **Water buttons:** `button.growcube_c75b31_water_plant_a` ... `_d`
- **Water warning:** `binary_sensor.growcube_c75b31_water_warning`

Each plant can be watered manually via button or automatically via automation.

---

## License
MIT

---

## Credits
- Developed with OpenAI's ChatGPT and Home Assistant Community tools.
- Inspired by the GrowCube ecosystem and plant automation needs.

---

## Screenshots
*Coming soon: Example dashboards with moisture tracking and buttons.*

---

Enjoy automated, reliable, and beautiful plant care with GrowCube and Home Assistant! 🌿
