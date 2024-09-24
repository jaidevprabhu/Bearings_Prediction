# Exploratory data review

We explain the data as seen and analyzed after donwloading all the experiments. WE have done a preliminary review of the Paper that was published to interpret the data and develop a statistical model in predictive mainatainence area. 

In all the 3 experiments - at least one bearing failed at the end of the experiment, and one or more of them performed well past their normal lifetime. 

We show the statistical readings that clearly show the data of the failed bearings in each of the experiments. 

We have charted the data and done the stats analysis at the beginning, the approximate center and at the end of the experiments. 


## Data Preview 

  This shows the structured data after being read in using `read_csv` method of pandas. 

```python
df.head().to_markdown()

'|    |      1 |      2 |      3 |      4 |\n|---:|-------:|-------:|-------:|-------:|\n|  0 |  0.085 | -0.139 | -0.071 | -0.078 |\n|  1 |  0.088 |  0.02  | -0.078 |  0.405 |\n|  2 |  0.022 |  0.273 |  0.168 |  0.41  |\n|  3 | -0.076 |  0.132 | -0.876 | -0.076 |\n|  4 | -0.212 | -0.22  | -0.354 | -0.432 |'

df.describe().to_markdown()

'|       |              1 |              2 |             3 |              4 |\n|:------|---------------:|---------------:|--------------:|---------------:|\n| count | 20480          | 20480          | 20480         | 20480          |\n| mean  |    -0.00248315 |    -0.00124644 |     0.0176133 |    -0.00368184 |\n| std   |     0.154769   |     0.234438   |     0.495062  |     0.248059   |\n| min   |    -0.667      |    -0.886      |    -5         |    -0.955      |\n| 25%   |    -0.107      |    -0.164      |    -0.239     |    -0.159      |\n| 50%   |    -0.005      |    -0.007      |     0.024     |    -0.01       |\n| 75%   |     0.098      |     0.156      |     0.293     |     0.161      |\n| max   |     0.742      |     0.872      |     3.167     |     0.867      |'

```  

## Early data for each experiment

### Raw plots - 

#### Test 2

<center>
    <img src = images/test2_start_smooth_line.png width = 100% / >
</center>

#### Test 3

<center>
    <img src = images/test3_start_smooth_line.png width = 100% / >
</center>


### Simple Stats (Min, Max, Mean, Median, Mode and Std)


#### Test 2

<center>
    <img src = images/test2_start_Simple_Stats.png width = 100% / >
</center>

#### Test 3

<center>
    <img src = images/test3_start_Simple_Stats.png width = 100% / >
</center>


### Advanced Plots (Skewness, Kurtosis and RMS values)


#### Test 2

<center>
    <img src = images/test2_start_Advance_Stats.png width = 100% / >
</center>

#### Test 3

<center>
    <img src = images/test3_start_Advance_Stats.png width = 100% / >
</center>





