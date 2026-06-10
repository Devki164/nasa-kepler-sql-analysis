# NASA Kepler Space Telescope Exoplanet SQL Pipeline

An end-to-end data engineering and SQL analytics platform that transforms raw observational data from NASA's Kepler Space Telescope into a structured, queryable planetary database. Using advanced SQL logic, multi-tiered aggregations, and classification frameworks, this project isolates habitable world candidates and maps out complex multi-planetary stellar architectures.

---

## 🚀 Pipeline Architecture & Core Logic

The pipeline uses `ipython-sql` to execute high-performance relational database tasks natively within an optimized data structure, handling the workflow in four core stages:

### 1. Database Ingestion & Initialization
* Dynamically locates observational raw CSV tables in the workbench environment.
* Utilizes `pandas` and `sqlite3` to instantiate an independent local database instance (`kepler_project.db`).
* Maps high-dimensional astrophysical features directly to structured relational schemas.

### 2. Data Cleansing & Validation (`clean_kepler`)
* Engineers a core table containing essential metrics: planetary radius, orbital period, equilibrium temperature, host star properties, and classification scores.
* Filters out identified false-positive instruments to eliminate telemetry anomalies (`WHERE koi_disposition != 'FALSE POSITIVE'`).
* Applies robust physical integrity checks to ensure vital observation indices (`koi_prad`, `koi_teq`, `koi_steff`) are fully validated and non-null.

### 3. Target Habitable Candidate Discovery
* Executes conditional filters to map out the Goldilocks zone for life-supporting worlds:
  * **Planetary Physical Volume Constraints:** Radii strictly between 0.5 and 2.0 times Earth's dimensions (`BETWEEN 0.5 AND 2.0`).
  * **Thermal Envelope Profiles:** Equilibrium temperatures bounded within the liquid water threshold of 200K to 373K.
* Isolates a verified catalog of target cosmic bodies sorted sequentially by physical radius.

### 4. Categorical Profiling & Cosmic Inventory
* Leverages standard `CASE WHEN` conditional frameworks to construct five explicit exoplanet categories based on Earth-relative geometric volumes:
  * **Rocky/Earth-sized** ($R_p < 1.2$)
  * **Super-Earth** ($1.2 \le R_p \le 2.0$)
  * **Sub-Neptune** ($2.0 \le R_p \le 4.0$)
  * **Neptune-like** ($4.0 \le R_p \le 10.0$)
  * **Gas Giant** ($R_p > 10.0$)
* Integrates `GROUP BY` structural buckets and statistical aggregates (`COUNT`, `AVG`, `ROUND`) to establish mean orbital period baselines for each planetary class.

### 5. Multi-Planetary Stellar Architectures
* Employs analytical metrics grouped under explicit `kepid` systems to flag solar setups holding multiple orbiting exoplanets.
* Uses the conditional `HAVING COUNT(*) > 1` logic to pinpoint the most crowded cosmic neighborhoods, capturing intricate systems holding up to 7 distinct planetary nodes.

---

## 📊 Analytical Insights

An integrated visualization suite built via `seaborn` maps out the physical density distributions discovered within the cleaned stellar matrix, showing the distinct population dominance of **Sub-Neptunes** and **Super-Earths** over traditional massive Gas Giants:

* **Sub-Neptune:** 1,554 planets discovered (Average orbital period: ~144.5 days)
* **Super-Earth:** 1,424 planets discovered (Average orbital period: ~34.7 days)
* **Rocky/Earth-sized:** 824 planets discovered (Average orbital period: ~17.5 days)
* **Neptune-like:** 370 planets discovered (Average orbital period: ~99.2 days)
* **Gas Giant:** 305 planets discovered (Average orbital period: ~78.1 days)

---

## 🛠️ Environment Configuration

* **SQL Engine:** SQLite via `ipython-sql` extension
* **Data Core:** `pandas`, `sqlite3`, `glob`
* **Visualization Stack:** `matplotlib`, `seaborn`

### Installation & Initialization
1. Clone the repository framework:
   ```bash
   git clone [https://github.com/your-username/nasa-kepler-sql-analysis.git](https://github.com/your-username/nasa-kepler-sql-analysis.git)
   cd nasa-kepler-sql-analysis
