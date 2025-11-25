
# **Data Dictionary**

## **Farms Dataset**

| Column Name          | Type        | Unit     | Description                     | Constraints                        |
| -------------------- | ----------- | -------- | ------------------------------- | ---------------------------------- |
| `farm_id`            | Integer      | —        | Unique identifier for each farm | Required, unique                   |
| `rainfall_mm`    | Float       | `mm` | Annual average rainfall         | Required, Range: `1000`–`3000`             |
| `temperature_celsius` | Float       | `celsius` | Annual average temperature      | Required, Range: `15`–`30`             |
| `elevation_m`    | Float       | `m` | Elevation above sea level       | Required, Range: `0`–`2963`             |
| `ph`                 | Float       | pH units | Soil acidity/alkalinity         | Required, Range: `4.0`–`8.5`             |
| `soil_texture`          | Categorical | —        | Dominant soil texture              | Required, Allowed: `sand, loamy sand, sandy loam, loam, silt loam, silt, sandy clay loam, clay loam, silty clay loam, sandy clay, silty clay, clay`    |
| `latitude`           | Float       | degrees  | Geographic latitude             | Range: -90 to 90                   |
| `longitude`          | Float       | degrees  | Geographic longitude            | Range: -180 to 180                 |

***

## **Species Dataset**

| Column Name               | Type   | Unit     | Description                              | Constraints                        |
| ------------------------- | ------ | -------- | ---------------------------------------- | ---------------------------------- |
| `species_id`              | Integer | —        | Unique identifier for each species       | Required, unique                   |
| `species_name`            | String | —        | Scientific name of the species | Required                           |
| `species_common_name`            | String | —        | Common name of the species | Required                           |
| `rainfall_mm_min`            | Float  | `mm` | Minimum preferred annual rainfall        | Required, Range: `200`–`5000`             |
| `rainfall_mm_max`            | Float  | `mm` | Maximum preferred annual rainfall        | Required, Range: `200`–`5000`             |
| `temperature_celsius_min`         | Float  | `celsius` | Minimum preferred temperature            | Required, Range: `10`–`40`             |
| `temperature_celsius_max`         | Float  | `celsius` | Maximum preferred temperature            | Required, Range: `10`–`40`             |
| `altitude_m_min`            | Float  | `m` | Minimum preferred altitude               | Required, Range: `0`–`3000`             |
| `altitude_m_max`            | Float  | `m` | Maximum preferred altitude               | Required, Range: `0`–`3000`             |
| `ph_min`                  | Float  | pH units | Minimum preferred soil pH                | Required, Range: `4.0`–`7.0`             |
| `ph_max`                  | Float  | pH units | Maximum preferred soil pH                | Required, Range: `7.0`–`8.5`             |
| `preferred_soil_types`    | List   | —        | List of compatible soil types            | Required, Allowed: `sand, loamy sand, sandy loam, loam, silt loam, silt, sandy clay loam, clay loam, silty clay loam, sandy clay, silty clay, clay`    |

***

## **Notes**

*   **Ranges must be ordered**: For species, `*_min` ≤ `*_max`.
*   **Units normalization**: All numeric values should be converted to standard units (e.g., mm/year for rainfall, °C for temperature).
*   **Categorical normalization**: Use canonical names (e.g., "Loam" not "loamy soil").
*   **Missing values**: TBD if any missing values are allowed.

***

## **Example Row (Farms)**

    farm_id: <FARM_ID>
    rainfall_mm: <value>
    temperature_celsius: <value>
    altitude_m: <value>
    ph: <value>
    soil_type: <soil type>
    latitude: <value>
    longitude: <value>

## **Example Row (Species)**

    species_id: <SPECIES_ID>
    species_name: <Species Name>
    rainfall_mm_min: <value>
    rainfall_mm_max: <value>
    temperature_celsius_min: <value>
    temperature_celsius_max: <value>
    altitude_m_min: <value>
    altitude_m_max: <value>
    ph_min: <value>
    ph_max: <value>
    preferred_soil_types: [<soil type 1>, <soil type 2>]