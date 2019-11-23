







## Module 2: Classification

**Classification:**

The separation of data into two or more categories, or (a point’s
classification) the category a data point is put into.



Examples:

- Bank wants to differentiate between those who will repay loans and those who will default
- Security agency wants to differentiate between those who are regular visitors and those who are potential terrorists
- Automated email filter wants to differentiate between genuine and spam email
- A legal document system wants to differentiate between documents
  that are relevant or irrelevant to a certain case.
- Surgeon wants to know whether an organ is safe to transplant or carry infectious disease
- Political consultant wants to differentiate between supportive, opposition and undecided voters
- Paleontologist wants to differentiate betweent the many species of dinosaurs



Classification questions **require data** to answer.

- For loan applicants, companies may collect data on: Income, Credit History, Age, Family SIze, Assets, Liabilities, etc..

<img src="../../../../../TyporaPics/1574112041228.png" alt="1574112041228" style="zoom: 33%;" />

- The line that separates the data is a **Classifier**

**Classifier** 

A boundary that separates the data into two or more categories. Also
(more generally) an algorithm that performs classification. 



<u>How do we know what line/classifier to draw?</u>

- We want to find a line that is as far away from the two different types of data as possible. This would result in a lower likelihood of misclassification.

<u>What if there's no line that can separate the data perfectly?</u>

- In this case, we use a **soft classifier** as opposed to a **hard classifier** that separates the data perfectly

| Pre-tilt: Less mistakes but more near mistakes Overall - Higher total mistakes | Post-tilt:  More mistakes but less near mistakes. Overall - Lower total mistakes |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![1574112404654](../../../../../TyporaPics/1574112404654.png) | ![1574112427812](../../../../../TyporaPics/1574112427812.png) |



<u>What if the cost of misclassification is different for different types of data?</u> i.e. what if giving away a bad loan has a higher cost than mistakenly turning away a good applicant, accepting red as green (Type 1: False positive) has a higher cost than rejecting green as red (Type 2: False negative).

<img src="../../../../../TyporaPics/pregnant.jpg" alt="pregnant" style="zoom: 50%;" />

- Hence, if giving away a bad loans is twice as costly as mistakenly turning away a good applicant, we will shift the classifier/line away from the red data and closer to the green data.

<img src="../../../../../TyporaPics/1574112925304.png" alt="1574112925304" style="zoom: 33%;" />







### Data Terminology

| Ex.1 Loan Applicants                                         | Ex2. Daily Car Sales                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![image-20191118214442164](../../../../../TyporaPics/image-20191118214442164.png) | ![image-20191118214427739](../../../../../TyporaPics/image-20191118214427739.png) |



- **Row** - Data point refers to each row. I.e. if we're looking at loan applications, then each applicant would be a datapoint. If we are looking at future sales, then each day will be a datapoint.

<img src="../../../../../TyporaPics/image-20191118214652805.png" alt="image-20191118214652805" style="zoom: 30%;" />

- **Column**
  - Attribute, feature, covariate predictor
  - Response/Outcome - the answer for each datapoint (For loan applicants, it's the observation of whether they
    repaid the full loan or not or it could be the fraction
    of the loan they repaid from zero to 100%.
    For sales, the response could be the
    number of sales recorded on each day.



**Structured data:**

- <u>Quantitative data</u> 

  - Numbers with a meaning

    - e.g.: age, sales, temperature, income

    - HIgher means more, lower means less

- <u>Categorical data</u>

  - Numbers without meaning

    - e.g. zip codes

    - higher/lower is not meaningful

  - Non-numeric

    - Ex: Hair color: Black, brown, red, blonde, gray

- <u>Binary data</u> (subset of categorical data)

  - Can only take upto two values
    - E.g. M/F, Repaid in full (Y/N), ON/OFF
    - In some cases we can treat this as a quantitative measure

- <u>Unrelated data</u>

  - No relationship between data points
  - e.g. Each loan applicant is a different person
    with no relationship to most other loan applicants.

- <u>Time series data</u>
- Same data recorded over time
  - Often recorded at equal intervals
  - E.g. Daily sales, stock prices, child's height on each birthday





### Support Vector Machines



**Maximimal Margin Classifier**

<img src="../../../../../TyporaPics/image-20191121212105053.png" alt="image-20191121212105053" style="zoom:50%;" />





What's the issue with Maximal Margin Classifiers? 

- **High Variance from Outliers-** in the event that there is an outlier, then the Maximum Marginal Classifier may be super compressed (and close to one of the classifications), hence may perform poorly when provided with new data (test data) & result in **high variance**

<img src="../../../../../TyporaPics/image-20191121212431330.png" alt="image-20191121212431330" style="zoom: 50%;" />



| Maximal Margin                                               | Soft Margin                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| <img src="../../../../../TyporaPics/image-20191121212105053.png" alt="image-20191121212105053" style="zoom: 50%;" /> | <img src="../../../../../TyporaPics/image-20191121212702844.png" alt="image-20191121212702844" style="zoom:50%;" /> |
| - Lower Bias<br />- Higher Variance                          | - Higher Bias<br />- Lower Variance                          |





<u>How do we test whether one soft-margin is better than another?</u>

- The answer is simple: We use **Cross**
  **Validation** to determine how many
  misclassifications and observations to
  allow inside of the **Soft Margin** to get the
  best classification (minimum error).





**Soft Margin Classifier** / **Support Vector Classifier** - is a model used to classify observations using a **Soft Margin**

The name Support Vector Classifier comes from
the fact that the observations on the edge and within
the Soft Margin are called Support Vectors.

<img src="../../../../../TyporaPics/image-20191121213400213.png" alt="image-20191121213400213" style="zoom:50%;" />



| <img src="../../../../../TyporaPics/image-20191121213500610.png" alt="image-20191121213500610" style="zoom: 35%;" /> | <img src="../../../../../TyporaPics/image-20191121213524808.png" alt="image-20191121213524808" style="zoom:35%;" /> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|                                                              |                                                              |



What happens when the data is 3-Dimensional?

- Support Vector Classifer forms a plane, instead of a line

<img src="../../../../../TyporaPics/image-20191121213635167.png" alt="image-20191121213635167" style="zoom: 33%;" />



Mathematical jargon:

- If the data are **1-Dimensional**, the support vector Classifier is a single point on a 1-Dimensional Number line. The point is called a "flat affine **0-Dimensional subspace**"

<img src="../../../../../TyporaPics/image-20191121213934545.png" alt="image-20191121213934545" style="zoom:33%;" />

- If the data are 2-Dimensional, the support vector Classifier is line on a 2-Dimensional Number space. The line is called a "flat affine **1-Dimensional subspace**"

<img src="../../../../../TyporaPics/image-20191121214138445.png" alt="image-20191121214138445" style="zoom:30%;" />



- If the data are 3-Dimensional, the Support Vector Classifier is a 2-Dimenional plane on a 3-Dimensional space. The line is called a "flat affine **2-Dimensional subspace**

<img src="../../../../../TyporaPics/image-20191121214324109.png" alt="image-20191121214324109" style="zoom:33%;" />

- And when the data are in 4 or
  more Dimensions, the Support
  Vector Classifier is a hyperplane.
  psst! In mathematical jargon, a
  hyperplane is a "flat affine subspace".



| 1-D Data                                                     | 2-D Data                                                     | 3-D Data                                                     | 4-D Data |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | -------- |
| <img src="../../../../../TyporaPics/image-20191121213934545.png" alt="image-20191121213934545" style="zoom: 50%;" /> | <img src="../../../../../TyporaPics/image-20191121214138445.png" alt="image-20191121214138445" style="zoom: 50%;" /> | <img src="../../../../../TyporaPics/image-20191121214324109.png" alt="image-20191121214324109" style="zoom: 50%;" /> |          |
|                                                              |                                                              |                                                              |          |



However, Support Vector Classifiers don't perform well with data that have classifications grouped in the middle.

<img src="../../../../../TyporaPics/image-20191121214825358.png" alt="image-20191121214825358" style="zoom: 33%;" />



Support Vector Machines

1. Start with a data in relatively low dimension<img src="../../../../../TyporaPics/image-20191121215149740.png" alt="image-20191121215149740" style="zoom:33%;" />
2. Move data into a higher dimension<img src="../../../../../TyporaPics/image-20191121215316050.png" alt="image-20191121215316050" style="zoom:33%;" />
3. Find a Support Vector
   Classifier that separates the
   higher dimensional data into
   two groups.

<img src="../../../../../TyporaPics/image-20191121215355346.png" alt="image-20191121215355346" style="zoom:33%;" />



In order to make the
mathematics possible, Support
Vector Machines use
something called **Kernel**
**Functions** to systematically find
Support Vector Classifiers in
higher dimensions.

- In essence, the algorithm iteratively increases the **d**, dimensionality of the data, and hence the Soft-Vector Classifier.
- We then use cross-validation to find an optimal value for **d** 



**Kernel Trick**

- The Kernel Trick reduces the
  amount of computation
  required for Support Vector
  Machines by avoiding the
  math that transforms the data
  from low to high dimensions...

- $\ldots$ and it makes calculating
  relationships in the infinite
  dimensions used by the Radial
  Kernel possible.

<img src="../../../../../TyporaPics/image-20191121220043520.png" alt="image-20191121220043520" style="zoom:50%;" />



# Bias/Variance Trade Off



<img src="../../../../../TyporaPics/image-20191120211230516.png" alt="image-20191120211230516" style="zoom:33%;" />

- The **blue** curved like represents the true relationship of the data points. The **red** line represents a linear regression. As you can see, no matter how you slice-or-dice the regression, you will never be able to capture the true relationship, hence is has a large amount of bias. 
- The inability for a machine learning method (like linear regression) to capture the true relationship is called **bias**.

<img src="../../../../../TyporaPics/image-20191120211605512.png" alt="image-20191120211605512" style="zoom:33%;" />

- Consider the **Squiggly** line, it hugs the training set along the arc of the true relationship. This means that it contains little bias.



<img src="../../../../../TyporaPics/image-20191120212205082.png" alt="image-20191120212205082" style="zoom:33%;" />

We compare the **Straight** line with the  **Squiggly** Line with the Straight line with a sums-of-squared formula that shows how 'biased' a model is. 

- Compared to the Straight line, the Squiggly line has a Sums-of-Squared of 0, hence, it is lower, and supposedly a 'better' model, hence less bias.





However, that was with the training set of the data, not the test set.

<img src="../../../../../TyporaPics/image-20191120212343700.png" alt="image-20191120212343700" style="zoom:50%;" />

Using the **test** set of the data, we can see that even thought the Squiggly line won the **training** set contest, it lost the **test** set contest.

<img src="../../../../../TyporaPics/image-20191120212541867.png" alt="image-20191120212541867" style="zoom: 33%;" />





In Machine Learning, the difference between fits between the data sets is called **Variance.** 

<img src="../../../../../TyporaPics/image-20191120212752367.png" alt="image-20191120212752367" style="zoom:33%;" />





<img src="../../../../../TyporaPics/image-20191120212610032.png" alt="image-20191120212610032" style="zoom:33%;" />

- The Squiggly Line has **low bias**, since it is
  flexible and can adapt to the curve in the
  relationship between weight and hight but the Squiggly Line has **high variability**,
  because it results in vastly different Sums of
  Squares for different datasets. Since this line fits the training set well and not the test set, we say that the line is **overfit**
- In contrast, the Straight Line has relatively
  **high bias**, since it can not capture the curve in
  the relationship between weight and height but the Straight Line has relatively **low**
  **variance**, because the Sums of Squares are
  very similar for different datasets.
- This shows the advantages and disadvantages of using a Complicated (Squiggly ) and Simple (Straight) model.

How do we find the best model then?

- Three commonly used methods for finding
  the sweet spot between simple and
  complicated models are:
  **regularization**, **boosting** and **bagging**.

- 



