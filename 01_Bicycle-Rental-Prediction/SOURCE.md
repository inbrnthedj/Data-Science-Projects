# Data Source

## Origin

The datasets used in this project were obtained from Kaggle:

> **[Bike Sharing in Washington D.C. Dataset](https://www.kaggle.com/datasets/marklvl/bike-sharing-dataset/data)**
> — uploaded by Mark Kaghazgarian

The dataset contains the hourly and daily count of rental bikes between **2011** and **2012** in the [Capital Bikeshare](https://www.capitalbikeshare.com/system-data) system in **Washington, D.C.**, along with corresponding weather and seasonal information.

---

## Tables & Data Structure

Two aggregated CSV files are provided:

| File | Granularity | Records | Columns |
|---|---|---:|---:|
| `hour.csv` | Hourly | 17 379 | 17 |
| `day.csv` | Daily | 731 | 16 |

Both files share the same schema, except that `hour.csv` includes an additional `hr` column.

---

### `hour.csv` — Hourly Aggregation

| # | Column | Type | Description |
|--:|--------|------|-------------|
| 1 | `instant` | int | Record index |
| 2 | `dteday` | str | Date (`YYYY-MM-DD`) |
| 3 | `season` | int | Season — `1`: Spring, `2`: Summer, `3`: Fall, `4`: Winter |
| 4 | `yr` | int | Year — `0`: 2011, `1`: 2012 |
| 5 | `mnth` | int | Month (`1`–`12`) |
| 6 | `hr` | int | Hour (`0`–`23`) |
| 7 | `holiday` | int | Whether the day is a public holiday — `0`: No, `1`: Yes |
| 8 | `weekday` | int | Day of the week (`0`–`6`) |
| 9 | `workingday` | int | `1` if the day is neither weekend nor holiday, `0` otherwise |
| 10 | `weathersit` | int | Weather situation (see [Weather Categories](#weather-categories) below) |
| 11 | `temp` | float | Normalized temperature in Celsius: `(t − t_min) / (t_max − t_min)`, where `t_min = −8`, `t_max = +39` |
| 12 | `atemp` | float | Normalized feeling temperature in Celsius: `(t − t_min) / (t_max − t_min)`, where `t_min = −16`, `t_max = +50` |
| 13 | `hum` | float | Normalized humidity (values divided by 100) |
| 14 | `windspeed` | float | Normalized wind speed (values divided by 67) |
| 15 | `casual` | int | Count of casual (non-registered) users |
| 16 | `registered` | int | Count of registered users |
| 17 | `cnt` | int | Total rental count (`casual + registered`) |

---

### `day.csv` — Daily Aggregation

| # | Column | Type | Description |
|--:|--------|------|-------------|
| 1 | `instant` | int | Record index |
| 2 | `dteday` | str | Date (`YYYY-MM-DD`) |
| 3 | `season` | int | Season — `1`: Spring, `2`: Summer, `3`: Fall, `4`: Winter |
| 4 | `yr` | int | Year — `0`: 2011, `1`: 2012 |
| 5 | `mnth` | int | Month (`1`–`12`) |
| 6 | `holiday` | int | Whether the day is a public holiday — `0`: No, `1`: Yes |
| 7 | `weekday` | int | Day of the week (`0`–`6`) |
| 8 | `workingday` | int | `1` if the day is neither weekend nor holiday, `0` otherwise |
| 9 | `weathersit` | int | Weather situation (see [Weather Categories](#weather-categories) below) |
| 10 | `temp` | float | Normalized temperature in Celsius: `(t − t_min) / (t_max − t_min)`, where `t_min = −8`, `t_max = +39` |
| 11 | `atemp` | float | Normalized feeling temperature in Celsius: `(t − t_min) / (t_max − t_min)`, where `t_min = −16`, `t_max = +50` |
| 12 | `hum` | float | Normalized humidity (values divided by 100) |
| 13 | `windspeed` | float | Normalized wind speed (values divided by 67) |
| 14 | `casual` | int | Count of casual (non-registered) users |
| 15 | `registered` | int | Count of registered users |
| 16 | `cnt` | int | Total rental count (`casual + registered`) |

> **Note:** The `hr` column is absent from `day.csv` since counts are already aggregated at the daily level.

---

### Weather Categories

The `weathersit` column encodes four weather conditions (sourced from [Freemeteo](http://www.freemeteo.com)):

| Code | Description |
|:----:|-------------|
| 1 | Clear, Few clouds, Partly cloudy |
| 2 | Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist |
| 3 | Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds |
| 4 | Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog |

---

## License

This dataset is released under the **[CC0: Public Domain](https://creativecommons.org/publicdomain/zero/1.0/)** license.

### Citation

> Fanaee-T, Hadi, and Gama, Joao. "Event labeling combining ensemble detectors and background knowledge."
> *Progress in Artificial Intelligence* (2013): pp. 1–15, Springer Berlin Heidelberg.
> DOI: [10.1007/s13748-013-0040-3](https://doi.org/10.1007/s13748-013-0040-3)

### Acknowledgements

- **Original data source:** [Capital Bikeshare — System Data](https://www.capitalbikeshare.com/system-data)
- **Weather information:** [Freemeteo](http://www.freemeteo.com)
- **Holiday schedule:** [DC Department of Human Resources](http://dchr.dc.gov/page/holiday-schedule)