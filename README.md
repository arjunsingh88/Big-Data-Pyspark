# Big-Data (Pyspark, Databricks)
## `Project 1.` [Predictive Modeling: A case of Aircraft engine run-to-failure simulation](https://github.com/arjunsingh88/Big-Data-Pyspark/tree/master/Pyspark%20(Aircraft%20Engine%20Run-to-Failure%20Simulation))

### Description
The data used in this project is the simulated running data of different aircraft's engines, provided by NASA. All engines are of the same type, but each engine starts with different state and had different use circumstances.
The main goal of this project is to perform predictive maintenance on commercial turbofan engine. The predictive maintenance approach used here is a data-driven approach, meaning that data collected from the operational jet engine is used to perform predictive maintenance modeling. To be specific, the project aim is to build a predictive model to estimate the Remaining Useful Life ( RUL) of a jet engine based on run-to-failure data of a fleet of similar jet engines. The algorithm documented here follows closely
* Throughout the Experimenting and simulation the questions that needs to be answered are:
    *	How many unexploited running cycles are left for a given engine till its complete failure ?
    *	What causes an engine to fail (In case we came across the independent variables' labels ??? )
    *	Binning ???

### Modeling Strategies
* **`STRATEGY 1:` Regression models to predict remaining useful lifetime (RUL)**
    *	**QUESTION**: How many days/cycles are left before the system fails?
    *	**DATA CHARACTERISTICS**: Static and historical data are available, and every event is labelled. Several events of each type of failure are present in the dataset.
    *	**BASIC ASSUMPTIONS/REQUIREMENTS**:
Based on static characteristics of the system and on how it behaves now, the remaining useful time can be predicted which implies that both static and historical data are required and that the degradation process is smooth.
Just one type of “path to failure” is being modelled: if many types of failure are possible and the system’s behavior preceding each one of them differs, one dedicated model should be made for each of them. Labelled data is available and measurements were taken at different moments during the system’s lifetime.

* **`STRATEGY 2:` Classification models to predict failure within a given time window**
Creating a model, which can predict lifetimes very accurate can be very challenging. In practice however, one usually does not need to predict the lifetime very accurate far in the future. Often the maintenance team only needs to know if the machine will fail ‘soon’. This results in the next strategy:
    * **QUESTION**: Will the machinery/part fail in the next N days/cycles?
    * **DATA CHARACTERISTICS**: Same as for strategy 1
    * **BASIC ASSUMPTIONS/REQUIREMENTS**: The assumptions of a classification model are very similar to those of regression models. They mostly differ on:
Since we are defining a failure in a time window instead of an exact time, the requirement of smoothness of the degradation process is relaxed.
Classification models can deal with multiple types of failure, as long as they are framed as a multi-class problem, e.g.: 
        * class = 0 corresponding to no failure in the next n days,
        *	class = 1 for failure type 1 in the next n days, (Binary classification)
        *	class = 2 for failure type 2 in the next n days and so forth. (Multi Classification)
Labelled data is available and there are “enough” cases of each type of failure to train and evaluate the model.

***`NOTE` : In general, what regression and classification models are doing is modelling the relationship between features and the degradation path of the system. That means that if the model is applied to a system that will exhibit a different type of failure not present in the training data, the model will fail to predict it.***

### Pipeline stages
![b1](https://user-images.githubusercontent.com/45566835/83406130-47d72180-a40e-11ea-96ae-9c3d113a5fc0.png)




## `Project 2.` [Binary classification problem of USA 1991 census, earnings > 50k or < 50k](https://github.com/arjunsingh88/Big-Data-Pyspark/tree/master/Pyspark%20(A%20USA%201991%20census%20case))
1. **EDA & Feature (engineering, selection & transformation) pipeline**
2. **KPI's**
3. **Machine Learning ( Classification algorithms: Naive bayes, logistic regression, SVM, Random forest, Gradient Boosting )**
4. **Hyper parameter tuning**
5. **Binary class evaluation**
