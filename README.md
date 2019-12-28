# Creating-Customer-Segments-with-Arvato

**Install**
This project requires Python 3.x and the following Python libraries installed:

- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org)
- [matplotlib](http://matplotlib.org/)
- [Seaborn] (https://seaborn.pydata.org/) (for data visualization) The code should run with no issues using Python versions 3.*.
- [Sklearn / scikit-learn] (https://scikit-learn.org/stable/) 

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
In this project, Bertelsmann partners AZ Direct and Arvato Financial Solutions have provided two datasets one with demographic information about the people of Germany, and one with that same information for customers of a mail-order sales company. We looked at relationships between demographics features, organized the population into clusters, and saw how prevalent customers are in each of the segments obtained.

**About the repo**
The repo contains a .ipynb file that does the following:

**Approach and Observations**

DAta wrangling was done to find out missing values from the dataframe 

After performing Dimensionality Reduction using PCA, 28 features retained and we can explain over 85% of the variability.

In the first principal components, we know that Number of family houses in the PLZ8 region are very important features PLZ8_ANTG3 & PLZ8_ANTG4 (positive), PLZ8_ANTG1 (negative) top 5 positive and top 5 negative

In the second principal components, we know that Personality typology is a influent factor: event-oriented(+ve), sensual-minded(+ve), dutiful(-ve), religious(-ve) are all in top 5 +ve and top5 -ve

In the third principal components, we know that another personality typology contributes a lot: +ve: dreamful, socially-minded, cultural-minded, family-minded -ve: event-oriented, critical-minded, dominant-minded, combative attitude

To apply clustering to the general population using KMeans, we decided to use 8 clusters to segment the population, because, from the curve of the average distance to centroid, we found that the elbow of the curve is around 8, which is also the turning point of the curve.

We can describe segments of the population that are relatively popular with the mail-order company, and relatively unpopular with the company.

These segments are relatively popular with company: 3 are much more than the public 3 - related high affinity of combative attitude, male, low financial interest

These segments are relatively unpopular with company: 5,6 are much less than the public 5 is mostly related with Personality typology especially low affinity of rational, and relative young age (ALTERSKATEGORIE_GROB) 6 is mostly related with Personality typology especially rational, and high financial interest
