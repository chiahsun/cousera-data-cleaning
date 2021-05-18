# `tidy_data.csv`
## Variable Description

| Variable | Type | Description | 
| :-: | :-- | :-- |
| subject | integer | The id between 1~30 which represents the volunteer |
| activity | factor <br> 1 `WALKING` <br> 2 `WALKING_UPSTAIRS` <br> 3`WALKING_DOWNSTAIRS` <br> 4 `SITTING` <br> 5 `STANDING` <br> 6 `LAYING` | One of the six activities|
| feature | character | Extracted features for sensors |
| measurement | factor <br> 1 `mean` <br> 2 `std` | The statistics in mean or standard deviation |
| axis | factor <br> 1 `MAG` <br> 2 `X` <br> 3 `Y` <br>  4 `Z` | The axis of the sensor. <br> `MAG` represents the Euclidean norm of the three axes |
| value | double | The value calculated from different sensors and metrics. <br> They are unitless values since they are normalized between -1 and 1. |
| domain | factor <br> 1 `frequency` <br> 2 `time` | The signals are in time or frequency domain(after applying FFT) | 
| sensor | factor <br> 1 `accelerometer` <br> 2 `gyroscope` | Sensor type |
| acceType | factor <br> 1 `body` 2 `gravity` 3 `NA` | Accelerator type. <br> `NA` for non-accelerator signals |
| jerk | factor <br> 1 `no` <br> 2 `yes` | Indicate if this is a jerk signal |

## Transformation

1. Train and test data are merged to the same data set
2. Features are separated into different rows for `measurement`, `axis`, `domain`, `sensor`, `acceType`, `jerk` for data manipulation
3. Variables are turned into factor variables if possible
4. Averages are calculated with respect to per subject for the same variables

See `index.Rmd` for details for each step

# `tidy_data_groued.csv`

## Variable Description

| Variable | Type | Description | 
| :-: | :-- | :-- |
| subject | '' | '' |
| activity |'' | '' |
| measurement | '' | '' |
| axis | '' | '' |
| domain | '' | '' || sensor | '' | '' |
| acceType | '' | '' |
| jerk | '' | '' |      
| mean | double | average of grouped by the same above variables |

## Transformation

* The averages are computed from grouped by the above variables.

See `index.Rmd` for details for each step
