# Temperature & Furnace Activity Dashboard

A multi-room temperature chart with heating/cooling activity displayed as background shading.

## Features

- Line graphs for multiple room temperatures
- Orange background shading when furnace is heating
- Blue background shading when AC is cooling
- Target temperature setpoint line
- 6-hour time span (configurable)

## Preview

![Temperature Dashboard](preview.png)

## Requirements

### HACS Components
- [ApexCharts Card](https://github.com/RomRider/apexcharts-card)

### Entities

Update the following entities to match your setup:

| Entity | Purpose |
|--------|---------|
| `climate.dining_room` | Nest thermostat (hvac_action, temperature, current_temperature) |
| `sensor.office_hygro_temperature` | Office temperature sensor |
| `sensor.living_room_hygro_temperature` | Living room temperature sensor |
| `sensor.family_room_hygro_temperature` | Family room temperature sensor |
| `sensor.laundry_hygro_temperature` | Laundry room temperature sensor |
| `sensor.bedroom_temperature` | Bedroom temperature sensor |

## Installation

1. Install ApexCharts Card via HACS
2. Open your HA dashboard
3. Click "Edit Dashboard" (pencil icon)
4. Click "Add Card" → "Manual"
5. Paste the contents of `card.yaml` (starting from `type:`)

> **Note:** The card is wrapped in a `grid` container. This is required for proper width scaling in Section-based dashboards. Without the grid wrapper, the chart won't expand to fill the section width.

## Customization

### Colors

| Room | Color | Hex |
|------|-------|-----|
| Target | White | `#FFFFFF` |
| Dining Room | Pink | `#E91E63` |
| Office | Blue | `#2196F3` |
| Living Room | Green | `#4CAF50` |
| Family Room | Purple | `#9C27B0` |
| Laundry Room | Cyan | `#00BCD4` |
| Bedroom | Orange | `#FF5722` |
| Heating | Orange (30% opacity) | `rgba(255, 165, 0, 0.3)` |
| Cooling | Blue (30% opacity) | `rgba(66, 165, 245, 0.3)` |

### Time Span

Change `graph_span` to adjust the time window:
- `6h` - 6 hours (default)
- `12h` - 12 hours
- `24h` - 24 hours
- `7d` - 7 days
