# 🚗 Automobile Specifications, Performance & Price Analysis (Power BI) {#red_car-automobile-specifications-performance--price-analysis-power-bi}

This project presents an interactive **Power BI dashboard** developed as
a college Data Science project using an automobile dataset.

The project focuses on analyzing automobile specifications, performance
characteristics, and fuel-efficiency indicators to identify
relationships between vehicle characteristics and their **market
price**.

The project covers the complete workflow from **data preprocessing and
validation to transformation, DAX-based analysis, and interactive
dashboard development**.

------------------------------------------------------------------------

## 🎓 College Project {#mortar_board-college-project}

**Student Name:** `[YOUR NAME]`\
**Roll Number:** `[YOUR ROLL NUMBER]`\
**Course / Department:** `[YOUR COURSE / DEPARTMENT]`\
**College:** `[YOUR COLLEGE NAME]`\
**Academic Year:** `[ACADEMIC YEAR]`

------------------------------------------------------------------------

## 🎯 Objective {#dart-objective}

> **To analyze automobile specifications, performance, and fuel
> efficiency in order to identify relationships between vehicle
> characteristics and their market price.**

The dashboard uses automobile attributes such as engine size,
horsepower, body style, fuel type, drive wheels, curb weight, and
mileage to explore how these characteristics vary with vehicle price.

------------------------------------------------------------------------

## ⚙️ Data Preparation {#gear-data-preparation}

The dataset was prepared using **Power Query in Power BI** before
building the dashboard.

### 🧼 Data Cleaning {#soap-data-cleaning}

-   Duplicated the original query into `Automobile_Raw` and
    `Automobile_Clean`.
-   Replaced `?` with `null` to correctly represent missing values.
-   Removed `normalized-losses` because approximately 20% of its values
    were missing and it was not directly relevant to the project
    objective.
-   Removed the 4 records with missing `Price`, since price is the
    dependent variable for this analysis.
-   Retained the small number of missing values in `bore`, `stroke`,
    `horsepower`, and `peak-rpm`, since the remaining vehicle
    information was still useful for analysis.
-   Verified that Power BI correctly handled null values during
    aggregations.

### 🔄 Data Transformation {#arrows_counterclockwise-data-transformation}

-   Corrected numerical and categorical data types after handling the
    `?` values.
-   Created a numerical `Cylinder Count` column from the original
    textual `num-of-cylinders` field.
-   Renamed columns for readability, such as `city-mpg` → `City MPG`,
    `engine-size` → `Engine Size`, and `drive-wheels` → `Drive Wheels`.
-   Created `Average MPG`:

``` text
Average MPG = (City MPG + Highway MPG) / 2
```

-   Created `Price Category` with the categories:
    -   Budget
    -   Mid Range
    -   Premium
-   Created `Engine Size Category` with the categories:
    -   Small
    -   Medium
    -   Large

### 🔍 Data Validation {#mag-data-validation}

Power Query\'s **Column Quality**, **Column Profile**, and **Column
Distribution** features were used to validate:

-   Data types
-   Missing values
-   Errors
-   Categorical consistency
-   Numerical values
-   Impossible or invalid values

After validation, the cleaned data was loaded into Power BI using
**Close & Apply**.

### 🔁 Transformation & Validation Pipeline {#repeat-transformation--validation-pipeline}

``` text
Source
   ↓
Promoted Headers
   ↓
Changed Data Types
   ↓
Replaced "?" with null
   ↓
Removed normalized-losses
   ↓
Removed rows with missing Price
   ↓
Trimmed / Cleaned Text
   ↓
Renamed Columns
   ↓
Created Cylinder Count
   ↓
Created Average MPG
   ↓
Created Price Category
   ↓
Created Engine Size Category
   ↓
Changed Data Types
   ↓
Column Quality & Profile Validation
   ↓
Close & Apply
```

------------------------------------------------------------------------

## 📈 DAX Measures {#chart_with_upwards_trend-dax-measures}

The following measures were created:

-   **Total Vehicles**
-   **Average Price**
-   **Average Horsepower**
-   **Average Engine Size**
-   **Average MPG**
-   **Average City MPG**
-   **Average Highway MPG**
-   **Average Curb Weight**
-   **Maximum Price**
-   **Minimum Price**

These measures dynamically respond to filters and slicers in the
dashboard.

------------------------------------------------------------------------

# 📊 Dashboard Overview {#bar_chart-dashboard-overview}

The dashboard consists of **two interactive pages**.

## 🧾 1. Automobile Overview {#receipt-1-automobile-overview}

![Automobile Overview](images/page1-overview.png)

A high-level overview of the automobile dataset with KPIs, price
comparisons, relationship analysis, and interactive filters.

### 📌 KPIs {#pushpin-kpis}

-   Total Vehicles
-   Average Price
-   Average Horsepower
-   Average MPG
-   Average Curb Weight

### 🎛️ Slicers {#control_knobs-slicers}

Users can filter by:

-   Fuel Type
-   Drive Wheels
-   Make
-   Body Style
-   Aspiration

### 📊 Visuals {#bar_chart-visuals}

1.  **Scatter Chart** -- Horsepower vs. Price by Body Style
2.  **Scatter Chart** -- Engine Size vs. Price by Fuel Type
3.  **Pie Chart** -- Vehicle Distribution by Price Category
4.  **Column Chart** -- Average Price by Body Style
5.  **Column Chart** -- Average Price by Make
6.  **Column Chart** -- Average Price by Fuel Type

------------------------------------------------------------------------

## 🔎 2. Price & Performance Analysis {#mag_right-2-price--performance-analysis}

![Price & Performance Analysis](images/page2-analysis.png)

This page focuses on investigating relationships between automobile
specifications and market price.

### 📌 KPIs {#pushpin-kpis-1}

-   Average Price
-   Average Horsepower
-   Average Engine Size

### 🎛️ Filters {#control_knobs-filters}

-   Make
-   Body Style
-   Fuel Type
-   Drive Wheels

### 📊 Visuals {#bar_chart-visuals-1}

1.  **Scatter Chart** -- Horsepower vs. Price by Body Style
2.  **Scatter Chart** -- Engine Size vs. Price by Engine Type
3.  **Decomposition Tree** -- Price Breakdown by Vehicle Characteristics
4.  **Column Chart** -- Average Price by Body Style
5.  **Column Chart** -- Average Price by Drive Wheels
6.  **Column Chart** -- Average Price by Engine Size Category
7.  **Column Chart** -- Average Price by Fuel Type

### 🌳 Decomposition Tree {#deciduous_tree-decomposition-tree}

The decomposition tree provides an interactive breakdown of **Average
Price** according to vehicle characteristics such as engine-size
category and body style.

------------------------------------------------------------------------

## 🧠 Key Observations {#brain-key-observations}

The dashboard provides the following descriptive observations from the
dataset:

-   Vehicle price varies across manufacturers and body styles.
-   Larger engine-size categories have higher average prices in this
    dataset.
-   Rear-wheel-drive vehicles have a higher average price than
    front-wheel-drive vehicles in the analyzed data.
-   Diesel vehicles have a higher average price than gasoline vehicles
    in this dataset.
-   Horsepower and engine size show visible positive relationships with
    vehicle price.
-   The Price Category visualization shows the distribution of vehicles
    across Budget, Mid Range, and Premium groups.

> **Note:** These are descriptive patterns within this dataset. They
> should not be interpreted as proof that a particular vehicle
> characteristic directly causes a change in market price.

------------------------------------------------------------------------

## ✨ Power BI Features Demonstrated {#sparkles-power-bi-features-demonstrated}

-   Power Query
-   Data cleaning and transformation
-   Missing-value handling
-   Data type conversion
-   Conditional columns
-   Custom columns
-   Column quality and profiling
-   DAX measures
-   KPI cards
-   Scatter charts
-   Column charts
-   Pie charts
-   Decomposition tree
-   Interactive slicers
-   Dynamic filtering
-   Conditional formatting
-   Categorical data transformation

------------------------------------------------------------------------

## 🚀 How to Use {#rocket-how-to-use}

1.  Clone or download this repository.
2.  Open the `.pbix` file using **Power BI Desktop**.
3.  If required, update the dataset/file path in Power Query.
4.  Refresh the data.
5.  Explore the dashboard using the slicers and interactive visuals.

------------------------------------------------------------------------

## 📁 Project Structure {#file_folder-project-structure}

``` text
Automobile-PowerBI-Dashboard/
│
├── Automobile-Analysis.pbix
│
├── Data/
│   └── Automobile_data.csv
│
├── images/
│   ├── page1-overview.png
│   ├── page1-kpis.png
│   ├── page1-price-analysis.png
│   ├── page2-analysis.png
│   ├── page2-decomposition-tree.png
│   ├── page2-price-comparisons.png
│   └── filtered-dashboard.png
│
└── README.md
```

------------------------------------------------------------------------

## 🛠️ Tools & Technologies {#hammer_and_wrench-tools--technologies}

-   **Microsoft Power BI Desktop** -- Dashboard development and
    visualization
-   **Power Query** -- Data cleaning, transformation, and validation
-   **DAX** -- Measures and dynamic calculations
-   **CSV** -- Source dataset

------------------------------------------------------------------------

## 🎓 Academic Project {#mortar_board-academic-project}

This project was developed as a **college Data Science / Business
Intelligence project** to demonstrate practical skills in:

-   Data preprocessing
-   Data validation
-   Data transformation
-   Exploratory data analysis
-   Data visualization
-   DAX
-   Interactive dashboard development
-   Analytical thinking

------------------------------------------------------------------------

## 👤 Author {#bust_in_silhouette-author}

**Name:** `[YOUR NAME]`\
**Roll Number:** `[YOUR ROLL NUMBER]`\
**Course:** `[YOUR COURSE]`\
**College:** `[YOUR COLLEGE NAME]`

------------------------------------------------------------------------

## ⭐ Project {#star-project}

If you found this project useful or interesting, feel free to ⭐ the
repository.
