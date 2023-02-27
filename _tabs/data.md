---
layout: page
icon: fas fa-stream
title: Data
order: 2
---
# Data Sources
We obtained sensor reading data from the readings of student labs in EBU-3B (Computer Science) building. The dataset includes readings from 15 rooms across three floors, taken over the course of an entire year from July 2017 to June 2018. The number of datapoints in the dataset varies depending on the number of rooms involved and any missing values.

# Data Issues
A glaring weakness with this dataset is the period of collection. The data is collected from the sensors occassionally, with numerous gaps where there is no reading ranging from 2 days to about 50. These gaps will significantly impact the performance of models that rely on periodicity such as the prophet model. Additionally, key settings from the sensors have been left out, which could have statistical significance. Naturally, there is also noise in hte sensor readings.

# Data Cleaning
Other than basic transformations to prepare for the modelling, we removed some entries with room codes that did not make sense. Some of the entries seem to be duplicate entries under different codes. Missing periods of readings have been imputed with the last known value. We are also flooring the timestamps to the even 5 minute-values before the measurement using the Pandas Timestamp floor function.

# Final Working Data
The energy column post-processing can be seen in the plot below:
![Cleaned Energy Readings](/assets/energyplot.png)