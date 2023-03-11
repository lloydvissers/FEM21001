# FEM21001

In this repository, notebook files are presented.

bmmm_v5 uses real-live data, bmmm_v5_simulation uses simulated data. Only the bmmmm_v5 will be explained since bmmm_v5_simulation is the same apart from the different data sets used.

# bmmm_v5
## Libraries and functions
This section starts with installing the lightweight_mmm package, our main package. Also, an older version of numpy needs to be installed since some of the libraries have older dependencies.

Next, a custom function is defined in order to convert a time series into a moving average.

All libraries needed in this code are imported. Some warnings are disabled because of a deprecation. This deprecation has no direct effect on the working of the code.

## Load and Transform data
In this section, all data is first imported via Google drive.
The channels we use are define in the "channels" variable list.
Each data set we use (media_data, target, costs, extra_features) is converted to a numpy array, such that lightweight_mmm can work with it.

Next the data is split into a train and test set. The first 80% of the data is the training set, and the left over 20% is the test set.

All data sets are scaled such that lightweight_mmm can effectively use it.

## Run sampler
The mmm object is defined, we use the "adstock" model

mmm.fit has many input parameters that can be changed. In the paper different settings of this fit function are used.

## Evaluate
Certain parameter statistics of the fitted model are plot.

Next, the in-sample model fit and out-of-sample model fit are plot.
The printed MAPE variable is used in the paper.

## Budget allocation
In the last section, a budget optimization is applied. This is done for the first 75% of the test set data.

A plot is generated to get the proposed budget allocation before and after the optimization.
