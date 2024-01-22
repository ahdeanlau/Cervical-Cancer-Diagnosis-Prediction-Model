# Group-Cancer_2

## Variables Used
### Load Dataset

| Variable Name | Definition |
| --- | --- |
| df | whole dataset |
| X | features |
| y | target |

### Split Dataset

| Variable Name | Definition |
| --- | --- |
| X_train | training set - features |
| X_vald | validation set - features |
| X_test | test set - features |
| y_train | training set - target |
| y_vald | validation set - target |
| y_test | test set - target |

### Data Preprocessing

#### Missing Data

| Variable Name | Definition |
| --- | --- |
| X_train_nan | X_train, replaced ‘?’ with nan |
| X_train_imputed | X_train_nan, nan replaced with column mean |
| X_vald_nan | X_vald, replaced ‘?’ with nan |
| X_vald_imputed | X_vald_nan, nan replaced with column mean |
| X_test_nan | X_test, replaced ‘?’ with nan |
| X_test_imputed | X_test_nan, nan replaced with column mean |

#### Outliers

| Variable Name | Definition |
| --- | --- |
| column_train | column index which contains outliers |
| X_train_outlier | copy of X_train_imputed |
| X_train_sqrt | X_train_outlier, columns with outlier transformed with square root transformation |
| column_vald | column index which contains outliers |
| X_vald_outlier | copy of X_vald_imputed |
| X_vald_sqrt | X_vald_outlier, columns with outlier transformed with square root transformation |
| column_test | column index which contains outliers |
| X_test_noutlier | copy of X_test_imputed |
| X_test_sqrt | X_test_outlier, columns with outlier transformed with square root transformation |

#### Imbalanced Data

| Variable Name | Definition |
| --- | --- |
| y_train_reset_index | y_train, index reset |
| train | concatenation of X_train_sqrt and y_train_reset_index |
| train_major | train, rows with column ‘Biopsy’ = 0 (majority class) |
| train_minor | train, rows with column ‘Biopsy’ = 1 (minority class) |
| train_minor_upsampled | train_minor, resampled to 722 rows |
| train_upsampled | concatenation of train_minor_upsampled and train_major |
| X_train_balanced | X_train_sqrt, balanced data |
| y_train_balanced | y_train, balanced data |
| y_vald_reset_index | y_vald, index reset |
| vald | concatenation of X_vald_sqrt and y_vald_reset_index |
| vald_major | vald, rows with column ‘Biopsy’ = 0 (majority class) |
| vald_minor | test, rows with column ‘Biopsy’ = 1 (minority class) |
| vald_minor_upsampled | vald_minor, resampled to 81 rows |
| vald_upsampled | concatenation of vald_minor_upsampled and vald_major |
| X_vald_balanced | X_vald_sqrt, balanced data |
| y_vald_balanced | y_vald, balanced data |
| y_vald_balanced | y_vald, balanced data |
| y_test_reset_index | y_test, index reset |
| test | concatenation of X_test_sqrt and y_test_reset_index |
| test_major | test, rows with column ‘Biopsy’ = 0 (majority class) |
| test_minor | test, rows with column ‘Biopsy’ = 1 (minority class) |
| test_minor_upsampled | test_minor, resampled to 81 rows |
| test_upsampled | concatenation of test_minor_upsampled and test_major |
| X_test_balanced | X_test_sqrt, balanced data |
| y_test_balanced | y_test, balanced data |

#### Data Normalization

| Variable Name | Definition |
| --- | --- |
| columns_need_norm | Columns in the dataframe that needs to be normalized |
| X_train_norm | X_train_sqrt, normalized |
| X_vald_norm | X_vald_sqrt, normalized |
| X_test_norm | X_test_sqrt, normalized |
| X_train_norm_balanced | X_train_balanced, normalized |
| X_vald_norm_balanced | X_vald_balanced, normalized |
| X_test_norm_balanced | X_test_balanced, normalized |

#### Data Standardization

| Variable Name | Definition |
| --- | --- |
| columns_need_std | Columns in the dataframe that needs to be standardized |
| X_train_std | X_train_sqrt, standardized |
| X_vald_std | X_vald_sqrt, standardized |
| X_test_std | X_test_sqrt, standardized |
| X_train_std_balanced | X_train_norm_balanced, standardized |
| X_vald_std_balanced | X_vald_norm_balanced, standardized |
| X_test_std_balanced | X_test_norm_balanced, standardized |

### Feature Selection

#### Correlation Heatmap

| Variable Name | Definition |
| --- | --- |
| train_corr | concatenation of X_train_std and y_train_rest_index, to be used in producing correlation matrix |
| corr_matrix | correlation matrix created with train_corr |

#### Identifying columns

| Variable Name | Definition |
| --- | --- |
| corr_biopsy | corr_matrix with only the column ‘Biopsy’ |
| drop_features | list of names of columns to be dropped |
| drop_features_index | list of index of columns to be dropped |

#### Drop low correlation features

| Variable Name | Definition |
| --- | --- |
| X_train | X_train_std, with less correlatied features removed |
| X_vald | X_vald_std, with less correlatied features removed |
| X_test | X_test_std, with less correlatied features removed |
| X_train_balanced | X_train_std_balanced, with less correlatied features removed |
| X_vald_balanced | X_vald_std_balanced, with less correlatied features removed |
| X_test_balanced | X_test_std_balanced, with less correlatied features removed |
