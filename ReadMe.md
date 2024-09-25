# Titanic Passenger Analysis

## Overview
This repository contains an analysis of the Titanic dataset, aiming to explore the factors that influenced passenger survival rates during the ill-fated voyage. By examining various attributes such as passenger demographics, ticket class, and travel fare, this project seeks to uncover insights and patterns that contributed to survival.

## Dataset
The dataset used in this analysis is derived from Kaggle's Titanic competition, which provides a comprehensive collection of passenger data, including:
- Passenger Class (Pclass)
- Name
- Sex
- Age
- Sibling/Spouse Count (SibSp)
- Parent/Child Count (Parch)
- Ticket Number
- Fare
- Cabin
- Embarked Port

## Questions Explored
This analysis aims to answer the following questions:
- What demographic factors influenced survival rates?
- How did ticket class impact the likelihood of survival?
- What was the distribution of ages among survivors versus non-survivors?
- What patterns can be observed in passenger fare with respect to survival?

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



