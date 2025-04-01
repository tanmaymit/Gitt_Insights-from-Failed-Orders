# Gitt_Insights-from-Failed-Orders
 Introduction Gett is a corporate Ground Transportation Management (GTM) platform where clients can order taxis through an application. However, some orders fail to be completed. This analysis aims to investigate the reasons behind failed orders, identify trends, and provide insights into potential improvements in the matching system.
# 2. Objective
The primary goals of this analysis are:
Identify reasons for order failures, including cancellations before and after driver assignment.
Analyze failed orders by time of day.
Investigate the average cancellation time trends.
Study the estimated time of arrival (ETA) distribution.
Conduct a geospatial analysis of failed orders using hexagonal binning.

# 3. Data Overview
We used two datasets:

data_orders.csv: Contains details about customer orders, including order timestamps, locations, and statuses.
data_offers.csv: Includes details about driver offers (not used extensively in this analysis).

Key columns in data_orders:
order_datetime: Timestamp of order placement.
origin_longitude, origin_latitude: Location coordinates of the order.
m_order_eta: Estimated time of arrival for the order.
order_status_key: Order status (4 = Cancelled by Client, 9 = Cancelled by System).
is_driver_assigned_key: Indicates whether a driver was assigned.
cancellation_time_in_seconds: Time elapsed before order cancellation.

# 4. Methodology

Convert the order timestamp into a datetime format and extract hourly trends.

Categorize failed orders into "Cancelled by Client" and "Cancelled by System."

Identify whether the cancellation happened before or after driver assignment.

Visualize distributions of failed orders using bar plots and histograms.

Remove outliers in cancellation times (99th percentile cutoff) and analyze trends.

Utilize geospatial analysis (H3 hexagonal binning) to visualize order failure clusters.

# 5. Analysis & Findings

5.1 Distribution of Failed Orders by Reason. Most failed orders were client cancellations before driver assignment.
System cancellations were comparatively fewer.

5.2 Failed Orders by Hour
There were noticeable peaks in failed orders during rush hours (early morning and late evening).
This trend suggests possible supply-demand mismatches.

5.3 Average Cancellation Time by Hour
The average cancellation time varied throughout the day.
Outliers were removed to refine the analysis.

5.4 ETA Distribution by Hour
Longer ETAs were associated with higher failure rates, indicating possible customer impatience.

5.5 Geospatial Analysis of Failed Orders

Using H3 hexagonal binning, we identified key hotspots where order failures were concentrated.
These hotspots suggest areas that may require better driver availability or system optimizations.

# 6. Conclusion & Recommendations

Optimize driver availability: Peak failure hours indicate the need for better demand forecasting and driver allocation.
Improve system matching: Orders with long ETAs should be assigned closer drivers to reduce cancellations.
Enhance user experience: Providing real-time updates and alternative transport options could reduce user-initiated cancellations.
Geospatial optimization: Focusing on high-failure areas with targeted incentives for drivers could improve fulfillment rates.

# 7. Next Steps

Implement machine learning models to predict potential failures.
Use reinforcement learning to optimize driver allocations in real time.
Conduct further analysis on driver behavior and response times to improve offer acceptance rates.
