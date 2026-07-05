# Dataset Documentation — Smart Electricity Consumption Dataset

**Task ID:** ML-3 | Teyzix Core Internship (June Batch)

## 1. Dataset Collection Method
This dataset was **not** downloaded from Kaggle, UCI, GitHub, or any public repository.
It was generated using **realistic synthetic data generation** in Python (NumPy/Pandas),
simulating household electricity behavior based on:

- Real-world **appliance power ratings** (in kW) for AC, fan, refrigerator, washing
  machine, water motor, and lighting.
- Logical dependencies between variables (e.g., AC usage rises with outdoor
  temperature; fan usage drops in winter; appliance count scales with family size
  and number of rooms).
- Controlled random noise to mimic natural variation between households.
- A small proportion of missing values, duplicate rows, and outliers were
  deliberately injected (~1.5% missing, 6 duplicates, 5 outlier days such as
  festivals/guests) so the dataset supports genuine data-cleaning and EDA work,
  just like a real-world collected dataset would.

This approach follows the "Realistic Synthetic Data Generation" method explicitly
permitted in the task guidelines.

## 2. Dataset Summary
- **File:** `smart_electricity_consumption_dataset.csv`
- **Total Records:** 856 (after including intentional duplicates)
- **Total Features:** 20 (19 input features/ID + 1 target variable)
- **Target Variable:** `Daily_Electricity_Consumption_kWh`
- Covers both **residential** (Villa, Apartment, Independent House) and
  **commercial/industrial** (General Store, Industry, Outlet, Factory)
  customer types.

## 3. Feature Description

| Column | Type | Description |
|---|---|---|
| Record_ID | Categorical (ID) | Unique record identifier |
| Customer_Name | Categorical | Customer/household or business name (Pakistani names for residential; realistic business names for commercial types) |
| House_Type | Categorical | Villa / Apartment / Independent House / General Store / Industry / Outlet / Factory |
| Family_Members_or_Staff | Numeric | Number of family members (residential) or staff/workers (commercial) |
| Number_of_Rooms_or_Units | Numeric | Number of rooms (residential) or units/floor sections (commercial) |
| AC_Usage_Hours | Numeric | Hours per day AC/cooling is used |
| Fan_Usage_Hours | Numeric | Hours per day fans are used |
| Refrigerator_Usage_Hours | Numeric | Hours refrigerator/cold-storage runs (nearly always on) |
| Washing_Machine_Usage_Hours | Numeric | Hours per day washing machine is used (0 for commercial types) |
| Water_Motor_Usage_Hours | Numeric | Hours per day water motor/pump runs |
| Lighting_Hours | Numeric | Total daily lighting hours |
| Daily_Appliance_Count | Numeric | Number of distinct appliances/equipment used that day |
| Machinery_Load_kW | Numeric | Rated power of heavy machinery (Industry/Factory only, else 0) |
| Machinery_Usage_Hours | Numeric | Daily machinery run-hours (Industry/Factory only, else 0) |
| Outdoor_Temperature_C | Numeric | Outdoor temperature in Celsius |
| Day_of_Week | Categorical | Monday–Sunday |
| Season | Categorical | Summer / Winter / Monsoon / Spring |
| Is_Holiday | Binary (0/1) | 1 = weekend/holiday, 0 = working day |
| Electricity_Unit_Price | Numeric (Fixed per type) | Villa=30, Apartment=35, Independent House=33, General Store=48, Industry=58, Outlet=72, Factory=82 |
| **Daily_Electricity_Consumption_kWh** | Numeric (Target) | Total electricity consumed that day |

### Electricity Unit Price Table (per client specification)
| House/Business Type | Unit Price (per kWh) |
|---|---|
| Villa | 30 |
| Apartment | 35 |
| Independent House | 33 |
| General Store | 48 |
| Industry | 58 |
| Outlet | 72 |
| Factory | 82 |

## 4. Known Data Quality Notes (for the Preprocessing step)
- Missing values exist in: `AC_Usage_Hours`, `Fan_Usage_Hours`,
  `Outdoor_Temperature_C`, `Lighting_Hours` (~1.5% each).
- 6 duplicate rows are present and should be removed during cleaning.
- 6 rows contain outlier consumption values (simulating special high-usage
  days such as festivals, guests, or extra production shifts).
- `Customer_Name` is an identifier field and should be **dropped before
  model training** (not a predictive feature) — keep it only for reporting
  and the prediction interface.
- All of the above are intentional so the internship deliverable can
  genuinely demonstrate missing-value handling, duplicate removal, and
  outlier detection as required by the task.

## 5. Suggested Preprocessing Steps
1. Drop identifier columns (`Record_ID`, `Customer_Name`) before training.
2. Handle missing values (median/mean imputation or model-based imputation).
3. Drop duplicate rows.
4. Detect/treat outliers in the target variable (IQR or Z-score method).
5. Encode categorical columns (`House_Type`, `Day_of_Week`, `Season`) via
   One-Hot or Label Encoding.
6. Scale numeric features (StandardScaler/MinMaxScaler) before model training.
7. Note that `Electricity_Unit_Price` is fully determined by `House_Type`
   (a fixed mapping) — mention this in your feature engineering/business
   insights section, since it may introduce near-perfect correlation with
   the one-hot encoded `House_Type` columns.

## 6. Originality Statement
This dataset was designed and generated specifically for this internship task
using custom simulation logic written by the applicant. No external dataset,
public or private, was copied, downloaded, or reused in its creation.
