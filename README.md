# Water Quality Analysis Project

## Overview

The **Water Quality Analysis** project focuses on analyzing water quality data collected from various stations. This data includes various water quality parameters such as pH, dissolved oxygen, turbidity, and temperature, which are used to evaluate the overall water quality through a Water Quality Index (WQI). The analysis aims to uncover patterns and detect anomalies such as outliers, missing values, and inconsistencies in the dataset.

### Goals:
- To clean and preprocess the dataset.
- To explore and visualize the relationships between different water quality parameters.
- To calculate the Water Quality Index (WQI) for each sample.
- To classify water quality into categories based on WQI values.
  
## Dataset Details

The dataset used in this project contains the following attributes:
- **Station Code**: Identifier for the station where water samples are collected.
- **Location**: The location of the water sample collection.
- **State**: The state in which the water sample is collected.
- **Various water quality parameters**: These include pH, turbidity, dissolved oxygen, and more.

## Preprocessing Steps

1. **Data Import & Selection**: 
   - We import the dataset and select the first 1900 samples, as later samples contain incorrect data.
   
2. **Data Cleaning**: 
   - We handle missing values by imputing them using the median of the respective columns.
   - Missing station codes are filled based on the corresponding location and state.
   
3. **Outlier Detection**:
   - We use Z-Score normalization to detect outliers in the dataset.

4. **Water Quality Index (WQI) Calculation**:
   - The WQI is calculated based on a weighted sum of normalized values of several water quality parameters. This index helps classify water quality into different categories (Good, Moderate, Poor, etc.).

## Code Walkthrough

Here is a breakdown of the key steps in the analysis:

### Data Preprocessing and Cleaning

We first load the dataset and clean it by:
- Converting non-numeric values to numeric.
- Imputing missing values with the median of the column.
- Filling missing station codes based on location and state.

### Outlier Detection

We use **Z-Score Normalization** to detect outliers, with values greater than 3 being flagged as outliers. This step helps in ensuring the accuracy of our dataset before further analysis.

### Water Quality Index Calculation

The Water Quality Index is calculated for each sample based on the following formula:
\[
WQI = \sum \left( \frac{V_i - V_{ideal}}{S_i - V_{ideal}} \times 100 \right) \times W_i
\]
Where:
- \(V_i\): Observed value of the parameter
- \(V_{ideal}\): Ideal value for the parameter
- \(S_i\): Standard value of the parameter
- \(W_i\): Weight of the parameter

The final WQI values are used to classify the water quality into categories:
- **0**: Excellent
- **1**: Good
- **2**: Moderate
- **3**: Poor

### Visualizations

The following visualizations are generated to better understand the dataset:

- **KDE Plots** for different numeric attributes to check their distribution.
- **Outlier Detection** plots based on Z-Score.
  
## Analysis Results

The final WQI values for each sample are classified into categories, giving a clear understanding of the water quality at different locations. By analyzing this data, we can identify areas that need attention and intervention to improve water quality.



## Conclusion

This project highlights the importance of water quality monitoring and how data analysis can help in detecting issues such as poor water quality and outliers. The Water Quality Index provides a comprehensive measure of water quality, which can be used for further environmental assessments and policy-making.

## Setup and Installation

To run this project locally:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/water-quality-analysis.git
