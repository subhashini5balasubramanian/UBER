# Uber Ride Analytics Dashboard

## Project Overview

This project is an interactive Power BI dashboard developed to analyze Uber ride-booking operations and business performance using real-world ride data. The dashboard provides insights into booking trends, revenue generation, ride cancellations, customer satisfaction, driver performance, and vehicle utilization.

## Business Problem
Ride-booking companies process thousands of rides daily. Managing these operations efficiently becomes challenging due to:

* High ride cancellation rates
* Incomplete bookings
* Revenue loss from failed rides
* Customer dissatisfaction
* Driver performance monitoring
* Vehicle utilization imbalance

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

The raw dataset was cleaned and transformed using Power Query before building the dashboard.

### Data Cleaning Steps

* Removed unnecessary columns
* Corrected incorrect data types
* Removed duplicate records
* Handled missing and null values
* Applied proper column formatting


## DAX Measures Used

### Total Revenue

```DAX
Total Revenue = SUM('Uber Data'[Booking Value])
````

### Completed Bookings

```DAX
Completed Bookings =
CALCULATE(
    COUNT('Uber Data'[Booking ID]),
    'Uber Data'[Booking Status] = "Completed"
)
```

### Lost Bookings

```DAX
Lost Bookings =
CALCULATE(
    COUNT('Uber Data'[Booking ID]),
    'Uber Data'[Booking Status] <> "Completed"
)
```

### Average Driver Rating

```DAX
Average Driver Rating =
AVERAGE('Uber Data'[Driver Ratings])
```

### Average Customer Rating

```DAX
Average Customer Rating =
AVERAGE('Uber Data'[Customer Rating])
```

### Total Distance

```DAX
Total Distance =
SUM('Uber Data'[Ride Distance])
```

## Dashboard Features

* KPI Overview
* Revenue Analysis
* Booking Status Analysis
* Vehicle Performance Analysis
* Customer & Driver Rating Analysis
* Monthly Revenue Trends
* Revenue by Vehicle Type

## Tools & Technologies Used

* Power BI
* Power Query
* DAX
* Data Modeling
* Data Visualization

## Dataset Information

The dataset contains:

* Booking ID
* Booking Status
* Pickup & Drop Location
* Vehicle Type
* Ride Distance
* Booking Value
* Payment Method
* Customer Ratings
* Driver Ratings
* Cancellation Details

## Business Impact

This dashboard helps businesses:

* Reduce ride cancellations
* Improve operational efficiency
* Increase revenue
* Optimize vehicle allocation
* Improve customer satisfaction
* Monitor driver performance
* Support data-driven business decisions

## Future Improvements

* Real-time dashboard integration
* Predictive ride demand forecasting
* Geospatial analysis
* AI-based cancellation prediction

## Dashboard Overview

<video src="https://github.com/user-attachments/assets/ed41dcc2-84f5-4688-9e34-8605c67b3a59" controls width="800"></video>


## Conclusion

This project demonstrates how Power BI and frontend technologies can transform raw ride-booking data into meaningful business insights and interactive reporting solutions for operational and business analysis.


