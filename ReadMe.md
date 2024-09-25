# Alternate Dimenesional Analysis

## Overview
This repository contains an analysis of the Spaceship_Titanic dataset. In this analysis, our objective is to predict whether a passenger aboard the Spaceship Titanic was transported to an alternate dimension during the catastrophic collision with a spacetime anomaly. This unique event poses a fascinating challenge, blending elements of science fiction with data science.

The Spaceship Titanic, a luxurious interstellar vessel, encountered a mysterious spacetime anomaly that has led to the disappearance of certain passengers. Utilizing various passenger features such as demographics, spending behaviors, and CryoSleep status, we aim to build a predictive model that can accurately classify passengers based on whether they were transported to an alternate dimension.

## Dataset: Spaceship Titanic Passenger Records
The dataset consists of personal records for approximately two-thirds (~8700) of the passengers aboard the Spaceship Titanic. This data serves as the training set for predictive modeling, aiming to determine whether passengers were transported to an alternate dimension during the ship's collision with a spacetime anomaly. Below is a detailed description of each feature included in the dataset:

### PassengerId:
  A unique identifier for each passenger. The format is gggg_pp, where gggg represents the group the passenger is traveling with and pp indicates their number within that group. This feature can reveal family or group connections among passengers.

### HomePlanet:
  The planet from which the passenger departed, typically indicating their planet of permanent residence. This feature can provide insights into the demographics and origins of the passengers.

### CryoSleep:
  A binary indicator that shows whether the passenger elected to enter suspended animation for the duration of the voyage. Passengers in CryoSleep are confined to their cabins, which may affect their likelihood of being transported to another dimension during the collision.

### Cabin:
  The cabin number assigned to the passenger, structured in the format deck/num/side, where side can be either P (Port) or S (Starboard). This information may relate to the passenger's location on the ship.

### Destination: 
 The planet where the passenger is scheduled to debark. This feature indicates the intended endpoint of their journey.

### Age:
  The age of the passenger, which may correlate with survival rates and the likelihood of being transported during the anomaly.

### VIP:
  A binary indicator showing whether the passenger has purchased special VIP services for the voyage. This could reflect on their spending patterns and potentially their chances of being transported.

### RoomService, FoodCourt, ShoppingMall, Spa, VRDeck:
  These features represent the amounts billed to the passenger for various luxury amenities on the Spaceship Titanic. Analyzing spending patterns across these amenities could offer insights into passenger behavior and preferences.

### Name:
  The full name of the passenger, consisting of their first and last names. While not directly useful for prediction, it may help in identifying relationships or familial connections.
Transported:  This is the target variable, indicating whether the passenger was transported to another dimension during the collision. This binary outcome is the primary focus of the predictive modeling effort.

## Questions Explored
This analysis aims to answer the following questions:
- The Age vs Spending rates.
- Factors affecting the transportation of passengers.
- How many passengers were able to get transported in another dimension?
- What was the passenger status in the cabin? 

## Tools Used
The following tools and libraries were utilized in this analysis:
- **Python**: For data manipulation and analysis.
- **Pandas**: For data manipulation and exploration.
- **Matplotlib**: For data visualization.
- **Seaborn**: For advanced statistical visualizations.
- **Jupyter Notebook**: For executing Python scripts and documenting the analysis.

## Data Preparation
### Import Libraries
The analysis begins with importing necessary libraries and loading the Titanic dataset.

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load the dataset
df = pd.read_csv('titanic.csv')
```

## Data Cleanup
Initial data cleaning involves handling missing values, converting data types, and creating new features where applicable.

```python 
# Check for missing values
df.isnull().sum()

# Fill missing Age values with the median age
df['Age'].fillna(df['Age'].median(), inplace=True)

# Convert 'Embarked' to category type
df['Embarked'] = df['Embarked'].astype('category') 
```

## The Analysis
The project consists of several key analyses, each focusing on specific aspects of the data to uncover insights about passenger behavior and preferences:

1. **Passenger Distribution by Home Planet**
   - This analysis visualizes the distribution of passengers based on their home planet. Insights reveal that the majority of passengers are from Earth, with fewer passengers originating from Europa and Mars.
   

2. **CryoSleep Status**
   - This section examines the CryoSleep status of passengers, illustrating the fairly even split between those in CryoSleep and those who are not. Understanding the implications of CryoSleep can help assess passenger preferences and behaviors.
   

3. **Distribution of Passengers by Age**
   - This analysis visualizes the age distribution of passengers, revealing a spread with some concentration in their 20s and 30s. Recognizing the age demographics of passengers can inform targeted services and amenities.
   

4. **Total Spending on Amenities**
   - This section explores passenger spending across various amenities, indicating that the highest spending occurs in the FoodCourt, followed by the Spa. Other areas, such as RoomService and ShoppingMall, show considerably less spending. This analysis highlights the amenities that are most popular among passengers.
   

5. **Age vs. Spending Analysis**
   - This analysis investigates the relationship between passenger age and their spending habits across different amenities. Understanding how age influences spending can help optimize service offerings and marketing strategies.
   

6. **Combined Insights**
   - Finally, we synthesize the findings from the previous analyses to draw overall conclusions about passenger behavior and preferences. This section highlights interdependencies between demographics, spending patterns, and amenity usage.
   


## Results and Insights
### Key Findings
1. **Model Performance**: The predictive model built for classifying passengers based on their characteristics achieved a significant accuracy in identifying which passengers were transported to different planets. This underscores the potential of machine learning techniques in analyzing passenger data.
   
2. **Passenger Demographics**: The analysis revealed that certain demographic factors, such as age and home planet, play crucial roles in determining the likelihood of being transported to a specific planet. Understanding these dynamics can inform targeted outreach and service offerings.

3. **Spending Patterns**: Insights into passenger spending revealed that individuals from different home planets displayed distinct spending behaviors, which could be leveraged for personalized marketing strategies.

4. **CryoSleep Influence**: The model indicated that passengers in CryoSleep had different probabilities of being transported to various planets compared to those not in CryoSleep, highlighting the importance of this status in transportation decisions.

### Challenges Faced
- **Model Complexity**: Building an accurate predictive model required careful feature selection and tuning of hyperparameters to ensure optimal performance.
  
- **Data Imbalance**: Addressing any imbalances in the dataset, particularly regarding the representation of passengers from different planets, was essential to enhance model robustness.

### Conclusion
This analysis and modeling effort to identify passengers transported to different planets offers valuable insights into passenger behaviors and preferences. By understanding these factors, we can better cater to the needs of our diverse clientele and improve overall service offerings.



