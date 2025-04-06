# Kerala Dam Water Levels Dataset

This repository contains historical water level data for Kerala dams, collecting from the KSEB (Kerala State Electricity Board) website.

## Data Structure

The data is organized by year and month in the following structure:

```
data/
├── YYYY/ # Year folder (e.g., 2024)
│ ├── MM/ # Month folder (01-12)
│ │ ├── YYYY-MM-DD.json # Daily data file
│ │ └── ...
│ └── ...
└── ...
```

## File Format

Each daily file (`YYYY-MM-DD.json`) contains the following JSON structure:

```json
{
  "metadata": {
    "caption": "Water level as on DD.MM.YYYY at 7.00 AM",
    "source": "URL of source page",
    "scraped_at": "ISO timestamp of collection"
  },
  "data": [
    {
      "Sl. No.": "1",
      "Name of Dam / Reservoir": "IDUKKI",
      "District": "IDK",
      "MWL (metre)": "2408.5 ft",
      "FRL (metre)": "2403 ft",
      "Spillway Crest Level (metre)": "2373 ft",
      "Live Storage at FRL (MCM)": "1459.49",
      "Rule level(metre)": "2403.00 ft",
      "Blue level(metre)": "2395.00",
      "Orange level(metre)": "2401.00",
      "Red Level(metre)": "2402.00",
      "Today's Water level (metre)": "2350.68",
      "Today's Live Storage(MCM)": "677.681",
      "% Storage w.r.t Live Storage at FRL": "46.43%",
      "Same day previous year Water level (metre)": "2346.94",
      "Same day previous year Live Storage (MCM)": "631.747",
      "Inflow (cumecs)": "9.57",
      "Power House Discharge(cumecs)": "32.84",
      "Spillway release (cumecs)": "0.00",
      "Total Outflow (cumecs)": "32.84",
      "Rainfall (mm)": "27.80",
      "Remarks": null
    },
    // ... other dams
  ]
}
```

## 📋 Data Fields Description

### Basic Information
| Field | Description | Unit/Format | Example |
|-------|-------------|------------|---------|
| `Sl. No.` | Serial number | Integer | "1" |
| `Name of Dam / Reservoir` | Official name of the dam | String | "IDUKKI" |
| `District` | District where dam is located | 3-letter code | "IDK" |

### Level Measurements
| Field | Description | Unit | Example |
|-------|-------------|------|---------|
| `MWL (metre)` | Maximum Water Level | m/ft | "2408.5 ft" |
| `FRL (metre)` | Full Reservoir Level | m/ft | "2403 ft" |
| `Spillway Crest Level (metre)` | Spillway activation level | m/ft | "2373 ft" |
| `Today's Water level (metre)` | Current water level | m/ft | "2350.68" |
| `Same day previous year Water level (metre)` | Previous year comparison | m/ft | "2346.94" |

### Storage Data
| Field | Description | Unit | Example |
|-------|-------------|------|---------|
| `Live Storage at FRL (MCM)` | Total capacity at FRL | Million m³ | "1459.49" |
| `Today's Live Storage(MCM)` | Current storage volume | Million m³ | "677.681" |
| `% Storage w.r.t Live Storage at FRL` | Capacity percentage | % | "46.43%" |
| `Same day previous year Live Storage (MCM)` | Previous year comparison | Million m³ | "631.747" |

### Water Flow Metrics
| Field | Description | Unit | Example |
|-------|-------------|------|---------|
| `Inflow (cumecs)` | Water entering reservoir | m³/s | "9.57" |
| `Power House Discharge(cumecs)` | Water through turbines | m³/s | "32.84" |
| `Spillway release (cumecs)` | Spillway discharge | m³/s | "0.00" |
| `Total Outflow (cumecs)` | Combined water leaving | m³/s | "32.84" |

### Additional Data
| Field | Description | Unit | Example |
|-------|-------------|------|---------|
| `Rainfall (mm)` | Daily precipitation | mm | "27.80" |
| `Remarks` | Special notes | String/null | "Tunnel maintenance" |

## Update Frequency
Data is updated daily at 8:00 AM IST (2:30 AM UTC).

