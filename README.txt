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