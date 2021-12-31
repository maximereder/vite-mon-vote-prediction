This project aims to **study the opinion of the population** of Grand Nancy (France) on a few specific questions. The objective was to collect people's opinions without favoring a particular social category. 
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

493 people responded to the survey.

![responses](responses.png)

People features: 
*  First name,
*  gender,
*  age,
*  city,
*  socio-professional-category,
*  dependent.

Predicting if people are **agree to make Grand Nancy much greener** (First question).

*   **to_drop**: Time, Name and First.
*   **target**: First.
*   **all targets**: First, second and third.
*   **test_size**: 10%.
*   **precision**: High.


| Classifier  | Score          |
| :--------------- |:---------------:|
| knn  |   0.46        |
| svc  | 0.48             |
| baggingclassifier  | 0.44          |
| adaboostclassifier  | 0.20          |
| gradientboostingclassifier  | 0.54          |

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
