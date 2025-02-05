# Hospitality_Domain
Power BI Second Dashboard
Objective - the objective is to develop a Power BI dashboard for AtliQ Grands to analyze historical data, provide key insights, and help the company regain market share and revenue in the luxury/business hotel segment.
Steps - 
1)Get the Sample Data: Review the data provided by the stakeholders. This could include historical hotel performance data such as occupancy rates, room prices, bookings, revenue, etc.
2)Key Metrics: 
Revenue (total revenue, room revenue, F&B revenue, etc.)
Occupancy Rate
Average Daily Rate (ADR)
Revenue Per Available Room (RevPAR)
Booking trends
Customer segments (business vs leisure, geography, etc.)
Seasonality patterns
Market share compared to competitors
Revenue Metrics:
Total Revenue, Room Revenue, Total Bookings, Average Daily Rate (ADR)
Occupancy Rate, Revenue Per Available Room (RevPAR)

4)Visualizations: 
->Use a combination of charts and visuals
->Line/Area charts for time-series analysis (booking trends, seasonal variations).
->Bar charts for comparisons (Revenue per segment, geography).
->KPI cards for high-level metrics (Occupancy Rate, ADR, Revenue).
->Pie/Donut charts for distribution (customer type, market share, room type distribution).

5)Insights:
->Declining Market Share in High-Season: Revenue from business travelers dropped 15% in Q2 2024, indicating a loss in high-season bookings.
->Room Type Performance: Standard rooms have 60% occupancy, while premium rooms are at 85%. Consider promotions for standard rooms.
->Booking Lead Time vs. Occupancy: Bookings made 30+ days in advance have 10% higher occupancy. Focus on early-bird offers.
Some Dax queries for creating to this dashboard:
1)Revenue = SUM(fact_bookings[revenue_realized])
2)Total Bookings = COUNT(fact_bookings[booking_id])
3)Total Capacity = SUM(fact_aggregated_bookings[capacity])
4)Total Succesful Bookings = SUM(fact_aggregated_bookings[successful_bookings])
5)Occupancy % = DIVIDE([Total Succesful Bookings],[Total Capacity],0)
6)Average Rating = AVERAGE(fact_bookings[ratings_given])
7)No of days = DATEDIFF(MIN(dim_date[date]),MAX(dim_date[date]),DAY) +1
8)Total cancelled bookings = CALCULATE([Total Bookings],fact_bookings[booking_status]="Cancelled")
9)Cancellation % = DIVIDE([Total cancelled bookings],[Total Bookings])
and so on

