````md
# Uber Ride Analytics Dashboard | Power BI Project

## Project Overview

This project presents a comprehensive Power BI dashboard developed to analyze Uber ride-booking operations, revenue performance, customer behavior, and operational efficiency using real-world ride data.

The dashboard transforms raw transactional ride data into meaningful business insights that help identify operational bottlenecks, revenue leakage, customer satisfaction trends, and vehicle performance metrics.

This project demonstrates practical applications of:
- Business Intelligence
- Data Cleaning
- Data Modeling
- DAX Calculations
- Interactive Dashboard Development

## Business Problem

Ride-booking companies process thousands of ride transactions daily. Managing these operations efficiently becomes challenging due to:

- High ride cancellation rates
- Incomplete bookings
- Revenue loss from failed rides
- Driver performance monitoring
- Customer satisfaction management
- Vehicle utilization imbalance

This dashboard helps businesses monitor operational performance and make data-driven decisions to improve efficiency, customer experience, and profitability.

## Dashboard KPIs

| KPI | Value |
|------|------|
| Completed Bookings | 93K |
| Lost Bookings | 57K |
| Total Revenue | 52M |
| Total Distance Covered | 2.51M |
| Average Ride Distance | 17 KM |
| Average Driver Rating | 4.23 |
| Average Customer Rating | 4.40 |

## Data Cleaning & Transformation (Power Query)

The raw dataset was cleaned and transformed using Power Query to ensure data quality and accurate reporting.

### Removed Unnecessary Columns

Removed:
- Unwanted time columns
- Temporary attributes
- Irrelevant fields

#### Purpose
- Improves dashboard performance
- Reduces memory consumption
- Simplifies analysis

### Corrected Data Types

| Column Name | Data Type |
|------|------|
| Date | Date |
| Booking ID | Text |
| Customer ID | Text |
| Booking Value | Decimal Number |
| Ride Distance | Whole Number |
| Ratings | Decimal Number |

#### Purpose
- Enables accurate calculations
- Supports filtering and grouping
- Improves DAX performance

### Removed Duplicate Records

Duplicate rows were identified and removed using Power Query.

#### Purpose
- Prevents incorrect revenue calculations
- Avoids duplicate booking counts
- Ensures reliable KPIs

### Handling Missing Values

Handled null and blank values in:
- Ratings
- Cancellation reasons
- Incomplete ride reasons

#### Techniques Used
- Replaced null values with:
  - "Unknown"
  - "Not Available"
- Removed unnecessary blank rows

#### Purpose
- Improves reporting consistency
- Prevents visualization errors
- Maintains data integrity

### Column Formatting

Applied formatting to:
- Revenue columns
- Ratings
- Dates
- Text fields

#### Purpose
- Enhances dashboard readability
- Improves user experience
- Creates professional visual reports

## Data Modeling

A structured Star Schema model was implemented to improve analytical performance and dashboard scalability.

### Fact Table
- Ride Booking Data

### Dimension Tables
- Date Table
- Vehicle Type Table
- Payment Method Table
- Location Table

### Relationships Used
- One-to-Many Relationships
- Primary Key & Foreign Key Relationships

### Benefits of Data Modeling
- Faster report performance
- Accurate DAX calculations
- Better filtering capability
- Scalable dashboard architecture

## DAX Measures Used

### Total Revenue

```DAX
Total Revenue = SUM('Uber Data'[Booking Value])
````

Calculates total revenue generated from ride bookings.

### Completed Bookings

```DAX
Completed Bookings =
CALCULATE(
    COUNT('Uber Data'[Booking ID]),
    'Uber Data'[Booking Status] = "Completed"
)
```

Counts successfully completed rides.

### Lost Bookings

```DAX
Lost Bookings =
CALCULATE(
    COUNT('Uber Data'[Booking ID]),
    'Uber Data'[Booking Status] <> "Completed"
)
```

Tracks cancelled and incomplete bookings.

### Average Driver Rating

```DAX
Average Driver Rating =
AVERAGE('Uber Data'[Driver Ratings])
```

Measures overall driver performance.

### Average Customer Rating

```DAX
Average Customer Rating =
AVERAGE('Uber Data'[Customer Rating])
```

Measures customer satisfaction.

### Total Distance

```DAX
Total Distance =
SUM('Uber Data'[Ride Distance])
```

Calculates total ride distance covered.

### Average Ride Distance

```DAX
Average Distance =
AVERAGE('Uber Data'[Ride Distance])
```

Calculates average ride distance per booking.

## Dashboard Features

### KPI Overview

Displays:

* Completed Bookings
* Lost Bookings
* Total Revenue
* Total Distance
* Average Ride Distance

### Revenue Analysis

Analyzes:

* Monthly revenue trends
* Revenue by vehicle type

### Booking Status Analysis

Tracks:

* Completed rides
* Cancelled rides
* Incomplete rides

### Vehicle Performance Analysis

Compares:

* Auto
* Bike
* Go Mini
* Go Sedan
* Premier Sedan
* Uber XL

### Customer & Driver Rating Analysis

Monitors:

* Driver performance
* Customer satisfaction

## Tools & Technologies Used

* Power BI
* Power Query
* DAX
* Data Modeling
* Data Visualization
* SQL

## Dataset Information

The dataset contains:

* Booking ID
* Booking Status
* Pickup Location
* Drop Location
* Vehicle Type
* Ride Distance
* Booking Value
* Payment Method
* Customer Ratings
* Driver Ratings
* Cancellation Reasons

## Business Impact

This dashboard helps ride-booking businesses to:

* Reduce ride cancellations
* Improve operational efficiency
* Increase revenue
* Optimize vehicle allocation
* Improve customer satisfaction
* Monitor driver performance
* Support strategic decision-making

## Dashboard Preview

### Home Dashboard

(Add Screenshot Here)

### Overview Dashboard

(Add Screenshot Here)

## Project Structure

```text
Uber-Ride-Analytics-Dashboard
│
├── Uber Dashboard.pbix
├── Uber Dataset.csv
├── Dashboard Screenshots
└── README.md
```

## Future Improvements

* Real-time dashboard integration
* Predictive ride demand forecasting
* Geospatial route analysis
* AI-based cancellation prediction
* Customer segmentation analytics

## Author

Subha Shini

Aspiring Data Analyst | Power BI Developer | SQL Enthusiast

### Skills

* Power BI
* SQL
* Python
* Data Analytics
* Dashboard Development

## Conclusion

This project demonstrates how Power BI can transform raw ride-booking data into meaningful business insights. The dashboard helps analyze operational efficiency, revenue trends, customer satisfaction, and ride performance, enabling smarter and data-driven business decisions.

```
```
