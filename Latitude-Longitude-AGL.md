# Repeater Location and Elevation Accuracy

Amateur Repeater Directory strives to provide the most accurate repeater information possible. Because information like Latitude, Longitude, and AboveGroundLevel are not commonly found, our system uses several intelligent techniques to estimate or refine repeater positions and heights when exact values are not available. 

The Amateur Repeater Directory does not use data from RepeaterBook or Artsci Publishing, DO NOT take repeater information from those sites and enter the data into the Amateur Repeater Directory site. This could get you banned.

---

## 📍 Repeater Location (Latitude & Longitude)

Each repeater record includes a set of coordinates that represent its estimated position.

### How Locations Are Determined
-  When actual Latitude and Longitude coordinates can be found, we use them, these are what we call a precise latitude and longitude, we use those values as-is.  
- **City-based approximation** – If a repeater’s exact location is unknown, we start with the latitude and longitude of its **nearest city** from our **Demographics** table.  
- We then **spread repeaters out** slightly around that city center using a small random offset.  
  This avoids “stacking” multiple repeaters on the exact same point and makes them individually clickable on the map.

### Accuracy Indicators
- **`IsLatLongPrecise = true`**  
  The coordinates were provided directly and with enough decimal precision to be trusted as accurate. 
  
- **`HasLatLongError = true`**  
  The true coordinates are **unknown**. The system generated an estimated position using city data from the Demographics table.

---

## 🗻 Above-Ground Level (AGL) Data

Each repeater also has an **above-ground level** (AGL) value — the height of the antenna above local ground level.

### How AGL Is Determined
- When a verified AGL height is published, we store it exactly and mark the record as precise.
- When no value is available, we assign a **default of 150 feet**.

### Accuracy Indicators
- **`IsAboveGroundLevelPrecise = true`**  
  The true height above ground was provided and verified.
- **`IsAboveGroundLevelPrecise = false`**  
  The AGL value was estimated using the default (150 ft).

---

## Summary

| Field | Meaning |
|:------|:---------|
| `IsLatLongPrecise` | True if lat/long was supplied with sufficient precision |
| `HasLatLongError` | True if coordinates were estimated from city demographics |
| `IsAboveGroundLevelPrecise` | True if a verified AGL value was provided |
| Default AGL | 150 ft when unknown |

---

### Why This Matters
These indicators help you understand the confidence level of each repeater’s data. Even when the exact location isn’t known, our approach ensures that map visualizations remain usable and that every repeater appears in its most likely region — without misleading pinpoint accuracy claims.

---

## 🔧 Learn More & Contribute

Amateur Repeater Directory is a **100% free, open-source** project maintained by volunteers.  
If you notice an error, missing data, or want to help improve accuracy:

- 📖 Visit the project: [AmateurRepeaterDirectory.org](https://amateurrepeaterdirectory.org)  
- 💾 Explore the code: [GitHub – Amateur-Repeater-Directory](https://github.com/Amateur-Repeater-Directory)  
- 🗣 Submit updates or corrections through our [Change Request System](https://amateurrepeaterdirectory.org/submit)  

Your contributions help keep this database open, transparent, and community-maintained for everyone.
