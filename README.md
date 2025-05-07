Predicting Titanic Survival with SAS Machine Learning
Project Overview
This project uses supervised machine learning to predict passenger survival on the Titanic based on demographic, class, and family-related features. The analysis was conducted using SAS procedures such as "proc freq", "proc logistic", "proc hpforest", and "proc sgplot". The final output includes Kaggle-formatted predictions and interpretation based on variable importance and model accuracy.

Key Variable Definitions
"survived": Target variable indicating passenger outcome

"1" = survived

"0" = did not survive

"pclass": Passenger class, representing ticket type and socio-economic status

"1" = first class (wealthiest, highest priority access)

"2" = second class (middle-tier passengers)

"3" = third class (lowest class, often crowded lower decks)

"sex": Passenger gender ("male" or "female")

"age": Passenger age in years

"sibsp": Number of siblings or spouses aboard the Titanic

Example: A value of "1" means the passenger traveled with one sibling or spouse

"parch": Number of parents or children aboard

Example: A value of "2" means the passenger traveled with two parents, children, or a mix

"embarked": Port of embarkation

"C" = Cherbourg

"Q" = Queenstown

"S" = Southampton

"familysize": Total number of family members onboard (calculated as "sibsp + parch + 1")

"isalone": Indicator variable

"1" = passenger was traveling alone

"0" = passenger was with family

Objectives
Predict survival using features like sex, age, pclass, family size, and embarked
Explore survival patterns by passenger class, gender, and family structure
Compare model performance using logistic regression and random forest
Generate and export predictions for Kaggle competition submission

Tools and Technologies
SAS Studio
"proc import" to load train and test data
"proc freq" for categorical analysis and survival distribution
"proc logistic" to build interpretable classification models
"proc hpforest" to train ensemble models using random forest
"proc sgplot" for visualization of survival patterns
Kaggle Titanic dataset
Git for version control

Methodology
Imported data using "proc import"
Cleaned invalid age values and standardized text values in "sex" and "embarked"
Created new variables: "familysize = sibsp + parch + 1", "isalone = 1 if familysize = 1, else 0"
Used "proc freq" to examine survival by class, embarkation port, and family size
Found that among third-class passengers from Southampton, 229 died and only 61 survived
Among first-class passengers from Cherbourg, 53 survived and 21 died
Trained a logistic regression model using "proc logistic"
Significant predictors included sex, pclass, age, and familysize
Odds ratio for female was 13.7; area under ROC curve (AUC) was 0.859
Trained a random forest model using "proc hpforest" with 100 trees
Out-of-bag error reached 0.145 with top variables being sex, pclass, and familysize
Created bar charts using "proc sgplot" to visualize group-level survival
Scored the test dataset and exported predictions in Kaggle format

Results
Females had a 74.2 percent survival rate, while males had 18.9 percent
First-class passengers had a 62.6 percent survival rate, while third-class passengers had 24.2 percent
Passengers traveling alone had a 32 percent survival rate
Passengers with small families (2 to 4 people) had over 50 percent survival
Random forest outperformed logistic regression in prediction error
Logistic regression provided strong interpretability with AUC of 0.859

Recommendation
While overall survival rates favored first-class passengers and women, many men in higher classes still did not survive. This suggests that access to lifeboats alone was not enough—social behavior and evacuation policies likely played a role.

It is important to monitor survival patterns by both class and gender. Further modeling could include interaction terms like "sex*pclass" in "proc logistic", or subgroup models focusing on male passengers in first and second class.

Random forest is recommended for best accuracy. Logistic regression remains useful for interpretability and fairness checks. Features like "familysize" and "isalone" should be included when family dynamics matter. Visuals from "proc sgplot" help communicate findings clearly to non-technical audiences.

This framework can be applied to real-world problems where survival, fairness, or resource allocation must be predicted or optimized.
