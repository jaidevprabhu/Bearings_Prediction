# Exploratory data review

We explain the data as seen and analyzed after downloading all the experiment data. We have done a preliminary review of the Paper that was published to interpret the data and develop a statistical model in predictive mainatainence area. 

In all the 3 experiments - at least one bearing failed at the end of the experiment, and one or more of them performed well past their normal lifetime. 

We show the statistical data of the failed bearings in each of the experiments. 

We have charted the data and done the stats analysis at the **start**, the approximate **middle**, and at the **end** of the experiments. 


## Data Preview 

  This shows the structured data after being read in using `read_csv` method of pandas. 

```python
print(df.head().to_markdown()
|   1    |   2    |   3    |   4    |
|:------:|:------:|:------:|:------:|
| 0.085  | -0.139 | -0.071 | -0.078 |
| 0.088  |  0.02  | -0.078 | 0.405  |
| 0.022  | 0.273  | 0.168  |  0.41  |
| -0.076 | 0.132  | -0.876 | -0.076 |
| -0.212 | -0.22  | -0.354 | -0.432 |

print(df.describe().to_markdown())
|       |      1      |      2      |     3     |      4      |
|:-----:|:-----------:|:-----------:|:---------:|:-----------:|
| count |    20480    |    20480    |   20480   |    20480    |
| mean  | -0.00248315 | -0.00124644 | 0.0176133 | -0.00368184 |
|  std  |  0.154769   |  0.234438   | 0.495062  |  0.248059   |
|  min  |   -0.667    |   -0.886    |    -5     |   -0.955    |
|  25%  |   -0.107    |   -0.164    |  -0.239   |   -0.159    |
|  50%  |   -0.005    |   -0.007    |   0.024   |    -0.01    |
|  75%  |    0.098    |    0.156    |   0.293   |    0.161    |
|  max  |    0.742    |    0.872    |   3.167   |    0.867    |
```

 

## Early data for each experiment

## Raw plots - 

### Test 2

<center>
    <img src = images/test2_start_smooth_line.png height = 75% width = 75% / >
</center>

### Test 3

<center>
    <img src = images/test3_start_smooth_line.png height = 75% width = 75% / >
</center>


## Simple Stats (Min, Max, Mean, Median, Mode and Std)


### Test 2

<center>
    <img src = images/test2_start_Simple_Stats.png height = 75% width = 75% / >
</center>

### Test 3

<center>
    <img src = images/test3_start_Simple_Stats.png height = 75% width = 75% / >
</center>


## Advanced Plots (Skewness, Kurtosis and RMS values)


### Test 2

<center>
    <img src = images/test2_start_Advance_Stats.png height = 75% width = 75% / >
</center>

### Test 3

<center>
    <img src = images/test3_start_Advance_Stats.png height = 75% width = 75% / >
</center>


## Experiment mid-point data for each experiment

## Raw plots - 
### Test 2

<center>
    <img src = images/test2_middle_smooth_line.png height = 75% width = 75% / >
</center>

### Test 3

<center>
    <img src = images/test3_middle_smooth_line.png height = 75% width = 75% / >
</center>


## Simple Stats (Min, Max, Mean, Median, Mode and Std)
### Test 2

<center>
    <img src = images/test2_middle_Simple_Stats.png height = 75% width = 75% / >
</center>

### Test 3

<center>
    <img src = images/test3_middle_Simple_Stats.png height = 75% width = 75% / >
</center>


## Advanced Plots (Skewness, Kurtosis and RMS values)
### Test 2

<center>
    <img src = images/test2_middle_Advance_Stats.png height = 75% width = 75% / >
</center>

### Test 3

<center>
    <img src = images/test3_middle_Advance_Stats.png height = 75% width = 75% / >
</center>


## End of Experiment data analysis for each experiment
## Raw plots - 
### Test 2

<center>
    <img src = images/test2_end_smooth_line.png width = 100% / >
</center>

Failure in **bearing 1.**

### Test 3

<center>
    <img src = images/test3_end_smooth_line.png width = 100% / >
</center>

Failure in **bearing 3.**.

## Simple Stats (Min, Max, Mean, Median, Mode and Std)
### Test 2

<center>
    <img src = images/test2_end_Simple_Stats.png width = 100% />
</center>

Failure in **bearing 1.**

### Test 3

<center>
    <img src = images/test3_end_Simple_Stats.png width = 100% />
</center>

Failure in **bearing 3.**.

## Advanced Plots (Skewness, Kurtosis and RMS values)
### Test 2

<center>
    <img src = images/test2_end_Advance_Stats.png width = 100% />
</center>

Failure in **bearing 1.**

### Test 3

<center>
    <img src = images/test3_end_Advance_Stats.png width = 100% />
</center>

Failure in **bearing 3.**

