---
layout: page
icon: fas fa-archive
title: Results
order: 4
---
# Model Insights
Through our group testing a broad range of predictive models, our expectations were met in some ways and thoroughly defied in others. For example, the decision tree model was originally not intended to be the final model. However, its performance and accuracy were much better than initially predicted and outpaced the competing models. The highly complex Prophet model was not nearly as fortunate because of its reliance on using timestamp values as a predictor. The model likely tried to accommodate for large outliers in both the cleaned and uncleaned datasets leading to unrealistic predictions. To make this model viable, our group would have had to do a different kind of data cleaning or use data inaccessible to us students. On another note, the neural network model proved tough to get working and progress remained slow throughout. After multiple unsuccessful attempts to get it running, the neural net model was abandoned due to upcoming deadlines. The autoregression models were also unreliable due to frequent gaps in time for the sensor readings. Although the previous experiment passed the statistical tests, intuitively energy should not affect the power used by the air handling unit. For this reason, the vector autoregression regression especially may not have worked since the features and labels had little to no influence on each other.

As a result of our analysis of all five model types we tried, we decided to use the decision tree as our final predictive model. We needed our model to be reliable, which ruled out the neural network from the beginning. We also wanted the prediction to be as accurate as possible, and our inability to lower the mean squared errors of the Prophet model and autoregression models excluded them. Between the linear regression and decision tree regressor, both had similar mean squared errors and training times (which we wanted to keep low). We ended up selecting the decision tree model over the linear model because we thought it would be more generalizable to future data since the energy values are not strictly linear.


<style>
    th, td {
    padding: 15px;
    }
</style>
<table>
<tr>
    <th>Model</th>
    <th>MSE Data Uncleaned</th>
    <th>MSE Data Cleaned</th>
</tr>
<tr>
    <td>Linear Regression</td>
    <td>~5.3</td>
    <td>~0.0040</td>
</tr>
<tr>
    <td>Decision Tree Regressor</td>
    <td>~4.4</td>
    <td>~0.0040</td>
</tr>
<tr>
    <td>Meta Prophet Model</td>
    <td>Range from 45 to 275+</td>
    <td>~44</td>
</tr>
<tr>
    <td>Neural Network</td>
    <td>Failure to Converge</td>
    <td>Failure to Converge</td>
</tr>
<tr>
    <td>Autoregression</td>
    <td>81.76</td>
    <td>28.51</td>
</tr>
</table>

# Future Modeling Analysis
While we were successfully able to predict cost values for our time period covered, limitations in our early process lead to multiple avenues in which this venture could be expanded upon. Firstly, this model could be used to analyze HVAC costs during the COVID lockdowns (2020-2021 roughly). COVID fundamentally changed how air circulation worked at UCSD and will need newer data to create a generalizable model. An ambitious project could involve using our predictive model to actively automate HVAC adjustments via BRICK programming. Occupancy, air circulation standards, time of day, and other requirements could be referenced to improve the minute-to-minute HVAC processes. Even small optimizations could save organizations sums of money in the long run. Another large-scale plan could use this predictive model’s framework to analyze the cost-benefit of non-HVAC energy uses. Light fixtures, especially those that can shift their brightness, are but one of many smart building areas that stand to benefit greatly. Finally, the broad application of this project could be streamlined by using BRICKschema for deployment. Standardizing smart building asset names would significantly expedite the deployment process and ensure uniform changes for buildings outside of UCSD’s scope. 

# Conclusions
Our experience was defined by a combination of difficult failures and great successes. For the aspects that did not end up as we hoped: we found from the beginning that obtaining building data proves to be one of the largest challenges. We encourage future building designers at UC San Diego and otherwise to consider how data will be extracted in the design of future (smart) buildings. We also found that attempting to optimize setpoint values is ineffective when setpoints and actual values are separated, so any future optimization attempts on user setpoints need to first reduce differences or somehow devalue the actual values. Part of doing that analysis involves having up to date occupancy information to understand when the actual values or the setpoint values are accurate.

Despite our failures, we did make important discoveries about this data. We found great success in predicting energy and cost usage with simple (linear and decision tree) models. With additional time to train more advanced models, we believe it is possible to improve upon those predictions as well. We also found when there is an energy toll for users to turn on/off their local HVAC setpoint by analyzing output hourly, creating opportunities for future data analysts and building designers to correct for these differences for long-term benefit and energy reduction.
