In this notebook we can first observe some data exploration and some computations of preprocessing.

The data exploration is similar to the example 1-AnscombesQuartet.

The preprocessing phase concentrates quite all the attention to one factor: how to deal with null factors.
The important thing to infer is that we don't have to clean our data eliminating every null value, but first we have to understand which is the meaning of that null value.
In this example, depending on the attribute that we are analyzing, the null value has a different meaning.

Useful functions:
- DataFrame.isnull().sum(): allows to automatically count all the null values
- DataFrame.fillna("value_that_we_want_to_fill"): is used to fill the values with the value in the "" with zeros
- lambas: are special functions that allows to create custom functionalities
          i.e.: all_data["LotFrontage"] = all_data.groupby("Neighborhood")["LotFrontage"].transform(lambda x: x.fillna(x.median()))
                in this example it allows to fill all the null values with the median of the attribute x

Another part of the preprocessing is about cleaning the data.
This process is about deleting all the attributes and rows that don't carry any useful information for our application.

The correlation analysis describes how much an attribute influences/depends on the value of another attribute.
The diagonal of the correlation matrix is white since we compute the correlation of an item with itself, and so the correlation is maximal.

Which is the difference between heatmap and clustermap?
- heatmap: plot rectangular data as a color-encoded matrix
- clustermap: plot a matrix dataset as a hierarchically-clustered heatmap

The function get_dummies is used to generate the one hot encoding for all the categorical variables. It is a Pandas function that generates the binary variables for all the categorical variables

REMEMBER: after have preprocessed the data, we have to save the data into another file