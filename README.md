# Predicting Titanic Survival with SAS Machine Learning

## Project Overview
This project uses supervised machine learning to predict passenger survival on the Titanic using demographic, class, and family-related features. The analysis was conducted entirely in SAS using procedures such as "proc freq", "proc logistic", "proc hpforest", and "proc sgplot".

## Key Variable Definitions
"survived": 1 = survived, 0 = did not survive  
"pclass": 1 = first class (upper deck), 2 = second class (middle deck), 3 = third class (lower deck)  
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
Train and compare logistic regression and random forest models  
Merge gender_submission data to finalize test set survival labels  
Generate and export predictions for evaluation  

## Tools and Technologies
SAS Studio  
"proc import", "proc freq", "proc logistic", "proc hpforest", "proc sgplot"  
Kaggle Titanic dataset  
Git for version control  

## Methodology
Loaded and cleaned train, test, and gender_submission files  
Merged test data with survival labels and combined with train  
Filtered invalid ages and cleaned "sex" and "embarked" values  
Created "familysize" and "isalone" variables  
Used "proc freq" to explore survival by class, family structure, and embarkation  
Trained logistic regression using "proc logistic"  
- AUC = 0.898  
- Odds ratio for female = 38.5  
Trained random forest model using "proc hpforest"  
- OOB error = 0.115  
Visualized survival patterns using "proc sgplot"

## Results
59.6 percent of first-class (upper deck) passengers survived  
42.9 percent of second-class (middle deck) survived  
26.9 percent of third-class (lower deck) passengers survived  
74.2 percent of women survived; 18.9 percent of men survived  
Passengers with 2–4 family members had over 50 percent survival  
Solo travelers had a 30.7 percent survival rate  
Most solo passengers (56 percent) were in third class  
Random forest had strong prediction performance  
Logistic regression offered clear interpretability

## Interpretation of Results
Survival was highest for passengers in first class, located on upper decks near lifeboats. Women in upper-class cabins had the best access to escape. Small families (2–4 members) also had better outcomes due to support and coordination. Solo travelers, mostly in third class on lower decks, had the lowest survival rate. Being alone and far from exits severely reduced survival chances.

## Recommendation
Evacuation systems should guarantee fair access to safety regardless of class or cabin location. Upper deck location should not determine survival. Additional support, drills, and planning should focus on lower-deck passengers and solo travelers. Predictive models like logistic regression and random forest are effective tools for evacuation design, transport safety, and structured risk prediction.
