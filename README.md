### Predicting Titanic Survival with SAS Machine Learning

## Project Overview
This project uses supervised machine learning to predict passenger survival on the Titanic using demographic, class, and family-related features. The analysis was conducted in SAS using procedures such as "proc freq", "proc logistic", "proc hpforest", and "proc sgplot".

## Key Variable Definitions
"survived": 1 = survived, 0 = did not survive  
"pclass": 1 = first class, 2 = second class, 3 = third class  
"sex": gender of the passenger  
"age": age in years  
"sibsp": number of siblings or spouses aboard  
"parch": number of parents or children aboard  
"embarked": port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)  
"familysize": sibsp + parch + 1  
"isalone": 1 = alone, 0 = with family  

## Objectives
Predict survival using sex, age, pclass, and family size  
Analyze patterns using cross-tabulation and visualization  
Train and compare logistic regression and random forest  
Generate and export Kaggle prediction file  

## Tools and Technologies
SAS Studio  
"proc import", "proc freq", "proc logistic", "proc hpforest", "proc sgplot"  
Kaggle Titanic dataset  
Git for version control  

## Methodology
Loaded and cleaned data using "proc import"  
Filtered invalid ages, cleaned "sex" and "embarked" values  
Created "familysize" and "isalone" variables  
Used "proc freq" to explore survival by pclass, embarked, and family size  
Trained logistic model with "proc logistic"  
AUC = 0.859, odds ratio for female = 13.7  
Trained random forest model with "proc hpforest"  
OOB error = 0.145  
Visualized patterns using "proc sgplot"  
Scored test data and exported predictions for Kaggle  

## Results
74.2 percent of women survived; 18.9 percent of men survived  
First-class survival rate was 62.6 percent; third-class was 24.2 percent  
Passengers alone had 32 percent survival rate  
Passengers with 2, 3, or 4 family members had over 50 percent survival  
Random forest had lower prediction error  
Logistic regression offered strong interpretability  

## Recommendation
Survival favored women and higher classes, but many men in class 1 and 2 still died  
Future models should analyze class and gender combinations, add interaction terms in "proc logistic", or use subgroup modeling  
Use "proc hpforest" for best prediction performance  
Use "proc sgplot" to visually explain model insights  
This approach works well for other binary classification problems using structured data
