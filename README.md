# service-response-friction
## Overview
This analysis uses a two week snapshot from early January, comprising roughly 10,000 incidents, reported to the New Orleans Police Department and processed through the city’s 911 dispatch system. The goal is to demonstrate analytical process.

First we test whether hourly volume explains dispatch delay, then shift to system structure (priority and service path), and finally break down total time to identify where delays accumulate. Within this, volume is ruled out, process rules explain most variance, and an evening dispatch delay is isolated.
- Dataset source: https://catalog.data.gov/dataset/calls-for-service-2026

## Hourly Volume Is Not a Primary Driver of Dispatch Delay
Table: Time to Dispatch and Incident Volume by Hour

There is little to no visible correlation between the number of incidents and Time to Dispatch when analyzed by hour. High volume seemingly does not cause delays in Time to Dispatch and low volumes do not correlate with lower times. 

There is an outlier in Time to Dispatch. At 6pm, there is a large increase in Time to Dispatch. Service volume is both moderate and stable before and during this time and therefore service volume does NOT alone explain this variance. This could be due to operation level behaviors, such as a change of capacity, though further data is needed.

## Priority and Service Path as Drivers of Total Time
Table: Total Time by Service Path and Priority

High priority incidents have lower Median Total Time than lower priority incidents. Lower priorities show longer Median Total Times, consistent with incidents being resolved in priority order. This is also consistent across all service paths.

Service Path is a driver in total time to resolve an incident. Incidents that require dispatch on average take approximately twice as long to complete than non-dispatch serviced incidents. Meanwhile, GOA incidents take longer than either. Duplicates are resolved quickly.

## Where Time Accumulates in Dispatch Serviced Incidents
Table: Dispatch Serviced Incident Time Breakdown

We have 3 durations available for examining where time accumulates in Dispatch Serviced incidents relative to other service paths. The first 2 durations, Time to Dispatch and Time to Travel, are both low compared to the total time. Time On Scene is the primary duration within Dispatch Serviced incidents, resulting in longer total resolution times.

## Dispatch Delay and On-Scene Time During Evening Hours
Table: Dispatch Delay and On-Scene Time During Evening Hours

As previously stated, 6pm is an outlier in Time to Dispatch that is not explained by increased volume. At this hour, Time on Scene decreases rather than increases. Despite this reduction, Total Time to resolve an incident is higher at 6pm than in the surrounding hours, aligning with the observed increase in Time to Dispatch.

## Limitations
- This dataset represents a 2 week snapshot in early January. Findings are limited in their ability to infer patterns about yearly operations.
- Staffing and capacity data are unknown, which may affect dispatch performance

## Further Steps
- Extended analysis across multiple months to check for consistency of findings, including 6pm anomaly
- Segment to district or unit to see if there are localized patterns
