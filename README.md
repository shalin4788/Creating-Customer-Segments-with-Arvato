# Creating-Customer-Segments-with-Arvato

**Install**
This project requires Python 3.x and the following Python libraries installed:

- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org)
- [matplotlib](http://matplotlib.org/)
- [Seaborn](https://seaborn.pydata.org/) (for data visualization) The code should run with no issues using Python versions 3.*.
- [scikit-learn](https://scikit-learn.org/stable/) 

You will also need to have software installed to run and execute an iPython Notebook

Install Anaconda, a pre-packaged Python distribution that contains all of the necessary libraries and software for this project.

### Run

In a terminal or command window, navigate to the top-level project directory `Creating-Customer-Segments-with-Arvato` (that contains this README) and run one of the following commands:

```bash
ipython notebook Identify_Customer_Segments.ipynb
```  
or
```bash
jupyter notebook Identify_Customer_Segments.ipynb
```

This will open the iPython Notebook software and project file in your browser.

**Data** 
In this project, Bertelsmann partners AZ Direct and Arvato Financial Solutions have provided two datasets one with demographic information about the people of Germany, and one with that same information for customers of a mail-order sales company. We looked at relationships between demographics features, organized the population into clusters, and saw the customers type in each of the segments obtained.
Datasets that are needed for analysis are 
1) Population demographic dataset
2) Customer dataset

**About the repo**
The repo contains a .ipynb file that does the following:

**Approach and Observations**

Data wrangling was done to find out missing values from the Population demographic dataset  that has demographic information about people of Germany. Missing data in each column and row was identified and graphs were plot to find out outliers

Using basic statistical techniques, outliers of missing value count across rows and columns were removed

As a part of encoding technique, categorical and multi level categorical values were identified and few of them removed, numeric data that had categorical values were numeric encoded to make data consistent. For the mixed formatted data entries, apply function was used to break down 1 variable into multiple variables (columns). 

Finally all variables to be dropped were cached in a variable for future tracking

A 'clean' function was written to iterate through data wrangling step to perform the cleaning exercise in a dynamic fashion on a) Demographic population data b) Customer population data

Feature scaling was performed on the cleaned demographic dataframe to keep value range consistent and avoid additional outliers

Scikit learn's PCA was applied to find vectors with maximum variance in the dataframe

ADditionally, Dimensionality Reduction was performed using PCA, and 15 features were retained to derive 70% explained variance

In the first principal components, we know that Number of family houses in the PLZ8 region are very important features i.e. **No. of 6-10 family houses** in the PLZ8 region have highest positive impact,  **Movement pattern** has highest negative impact on the dataset

In the second principal components, we know that **Estimated age** is a influent factor, **personal topology** ex: social minded, family minded etc. had highest negative factor

In the third principal components, we found that **personal topology** ex: social minded, family minded etc. had highest positive factor now (which contradicts a bit with 2nd component analysis results) **gender** has highest negative impact

To apply clustering to the general population using KMeans, we decided to use 15 clusters to segment the population, because, from the curve of the average distance to centroid, we found that the elbow of the curve is around 15, which is also the turning point of the curve.

Thereafter, the customer dataset was pre-processed and engineered for dropping/ cleaning by running the 'clean' function

We can see that the segments of the population that are relatively popular are also popular for the customer segment as derived from the customer dataset the company.

These segments are relatively popular in the customers: 1) Etimated age 2) Gender 3) Financial topology (which was not one of the most highest positively impacted feature as derived for the demographic population except for **VORSORGER**: be prepared, which was 2md highest impacted feature in 2nd component)

**Note**: The co-relation as a part of the unsupervised segmentation done may not be most accurate as you see all variables w/ positive impact don't match entirely across population and customer dataset, however the explained variance can be changed to see the impact 

**References**
References
https://stackoverflow.com/questions/59502854/how-do-i-perform-join-on-2-dataframes-that-have-same-number-of-rows-but-no-match/59503051?noredirect=1#comment105188086_59503051

https://stackoverflow.com/questions/59505335/how-to-create-a-histogram-for-a-dataframe-with-just-1-column-and-multiple-rows/59505450#59505450

https://stackoverflow.com/questions/18022845/pandas-index-column-title-or-name

https://jakevdp.github.io/PythonDataScienceHandbook/05.09-principal-component-analysis.html

https://github.com/joshuayeung/Creating-Customer-Segments-with-Arvato/blob/master/Identify_Customer_Segments.ipynb

https://github.com/chauhan-nitin/Udacity-IdentifyCustomerSegments-Arvato/blob/master/Identify_Customer_Segments.ipynb

https://ro-che.info/articles/2017-12-11-pca-explained-variance
