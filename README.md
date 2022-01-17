# vite-mon-vote-prediction

## About the projet :
This project aims to study the opinion of the population of Grand Nancy (France) on a few specific questions. This study is part of a student project allowing to visualize a project proposed by the city.
This study makes it possible to feed the software for the thesis with real data.

This document will help me to put the data pipeline into production for the new software. Indeed, all the parts will be reused except the data visualization part.

## About the data:

Several pieces of information are necessary to take into account to understand the data set. 

We have created a google forms to collect the votes of each person.
A QR code has been specially created so that everyone can access it quickly.

The objective was to collect people's opinions without favoring a particular social category. However, the help from the university (email bank) raises awareness among people i.e students have been more affected overall.

24 QR codes have been displayed at points of interest in Grand Nancy.

Data was retrieved in parallel from multiple locations :

*   Our school,
*   Nancy city centre,
*   Essey-lès-Nancy,
*   Saint-Max,
*   Laxou.

The survey was also shared on social networks like Facebook. However, it was difficult to recover a lot of data because our networks cannot recover thousands of data. This justifies the rather low number of votes.

People can answer questions on a scale of 1 to 6. The objective is to study the **correlations** between their **characteristics and their responses**.

493 people responded to the survey.

![responses](responses.png)

People features: 
*  First name,
*  gender,
*  age,
*  city,
*  socio-professional-category,
*  dependent.

Correlation Matrix :

![corr](correlation_matrix.png)

Predicting if people are **agree to make Grand Nancy much greener** (First question).

*   **to_drop**: Time, Name and First.
*   **target**: First.
*   **all targets**: First, second and third.
*   **test_size**: 10%.


| Classifier  | Score          |
| :--------------- |:---------------:|
| knn  |   0.46        |
| svc  | 0.48             |
| baggingclassifier  | 0.44          |
| adaboostclassifier  | 0.20          |
| gradientboostingclassifier  | 0.54          |

As you can see, the results are quite low. As you can see, the results are quite low. To overcome this problem, we decided to make the answers of each person less precise in order to **reduce the risk of error** in the model.
In this way, an elected official of the town hall could choose a compromise between the precision of the answers and that of the model.

We can **predict people opinion** with different precisions: 
*   **High**: 
    *   [1 - 6] : approval graduation.
*   **Medium**: 
    *   [1 - 2] : People tend to disagree.
    *   [3 - 4] : People are mixed.
    *   [5 - 6] : People tend to agree.
*   **Low**: 
    *   [1 - 3] : People generally disagree.
    *   [4 - 6] : People generally agree.

Predicting if people are **agree to make Grand Nancy much greener** (First question).

*   **to_drop**: Time, Name and First.
*   **target**: First.
*   **all targets**: First, second and third.
*   **test_size**: 10%.
*   **precision**: Medium.

| Classifier  | Score          |
| :--------------- |:---------------:|
| knn  |   0.72        |
| svc  | 0.70             |
| baggingclassifier  | 0.74          |
| adaboostclassifier  | 0.78          |
| gradientboostingclassifier  | 0.76          |

Predicting if people are **agree to make Grand Nancy much greener** (First question).

*   **to_drop**: Time, Name and First.
*   **target**: First.
*   **all targets**: First, second and third.
*   **test_size**: 10%.
*   **precision**: Low.

| Classifier  | Score          |
| :--------------- |:---------------:|
| knn  |   0.96        |
| svc  | 1.00             |
| baggingclassifier  | 0.98          |
| adaboostclassifier  | 0.96          |
| gradientboostingclassifier  | 1.00          |

