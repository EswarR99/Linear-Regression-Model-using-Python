PROJECT DESCRIPTION:

Prediction of full load electrical power output of a base load operated combined cycle power plant using Linear Regression.


ALGORITHM DESCRIPTION:

Imported Linear Regression Module from scikit-learn library.
The target value is expected to be a linear combination of the features. In mathematical notation, if hat{y}
 is the predicted value.
 hat{y}(w, x) = w_0 + w_1 x_1 + ... + w_p x_p

LinearRegression fits a linear model with coefficients w = (w_1, ..., w_p) to minimize the residual sum of squares between the observed targets in the dataset, and the targets predicted by the linear approximation. Mathematically it solves a problem of the form: 
min_{w} || X w - y||_2^2

LinearRegression will take in its fit method arrays X, y and will store the coefficients w of the linear model in its coef_ member.
The coefficient estimates for Ordinary Least Squares rely on the independence of the features. When features are correlated and the columns of the design matrix X have an approximate linear dependence, the design matrix becomes close to singular and as a result, the least-squares estimate becomes highly sensitive to random errors in the observed target, producing a large variance. This situation of multicollinearity can arise, for example, when data are collected without an experimental design.

Complexity:The least squares solution is computed using the singular value decomposition of X. If X is a matrix of shape (n_samples, n_features) this method has a cost of O(n_samples(n_features)^2)
assuming that  n_samples is greater than or equal to n_features.


DATASET DESCRIPTION:

The dataset contains 9568 data points collected from a Combined Cycle Power Plant over 6 years (2006-2011), when the power plant was set to work with full load. Features consist of hourly average ambient variables Temperature (T), Ambient Pressure (AP), Relative Humidity (RH) and Exhaust Vacuum (V) to predict the net hourly electrical energy output (EP) of the plant.
A combined cycle power plant (CCPP) is composed of gas turbines (GT), steam turbines (ST) and heat recovery steam generators. In a CCPP, the electricity is generated by gas and steam turbines, which are combined in one cycle, and is transferred from one turbine to another. While the Vacuum is colected from and has effect on the Steam Turbine, he other three of the ambient variables effect the GT performance.
For comparability with our baseline studies, and to allow 5x2 fold statistical tests be carried out, we provide the data shuffled five times. For each shuffling 2-fold CV is carried out and the resulting 10 measurements are used for statistical testing.


ATTRIBUTE INFORMATION:

Features consist of hourly average ambient variables
- Temperature (T) in the range 1.81°C and 37.11°C,
- Ambient Pressure (AP) in the range 992.89-1033.30 milibar,
- Relative Humidity (RH) in the range 25.56% to 100.16%
- Exhaust Vacuum (V) in teh range 25.36-81.56 cm Hg
- Net hourly electrical energy output (EP) 420.26-495.76 MW
The averages are taken from various sensors located around the plant that record the ambient variables every second. The variables are given without normalization.


DATASET WEBSITE:

http://archive.ics.uci.edu/ml/datasets/Combined%20Cycle%20Power%20Plant


