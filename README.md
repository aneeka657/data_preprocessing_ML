1.	**Missing_values**
1.	1. Before filling missing values for numerical , first check mean and median of that column. If the mean < median , insert mean for missing values otherwise mode.
2.	2. Before putting mode for the missing values in categorical column , checl count values of each category , and put the larger count value category to for missing values. 
3.	3. If the column have more than 70 to 80 percent missing values , better to drop that column.
4.	4. We can also use sklearn to impute missing values. 
2.	from sklearn.impute import SimpleImputer
1.	
2.	5. Scikit.impute from simpleImputer also do the missing values task
3.	6. Multivariate imputer also insert missing values but based on neighbor columns.
3.	from sklearn.experimental import enable_iterative_imputer
4.	from sklearn.impute import IterativeImputer
1.	max_iter: This parameter specifies the maximum number of imputation iterations that the IterativeImputer will perform. During each iteration, the imputer updates the missing values of each feature using a regression model based on the other features. The imputation process can be thought of as repeatedly filling in missing values, re-estimating the models, and updating the imputations.
2.	
3.	7. For categorical we can use forward and backward pass as well.
4.	Ffill() and bfill().
5.	8. K nearest neighbor can also be use to imput missing values. 
5.	from sklearn.impute import KNNImputer
6.	
7.	# impute age column using KNNImputer from sklearn
8.	imputer = KNNImputer(n_neighbors=5)
9.	df['age'] = imputer.fit_transform(df[['age']])
1.	n_neighbors: This parameter determines the number of neighboring samples to use for imputing each missing value. The neighbors are the rows (or samples) in the dataset that are closest to the sample with the missing value, based on a specified distance metric (e.g., Euclidean distance).

