# Exploratory data review

We explain the data as seen and analyzed, after downloading all the experiment data. We have done a preliminary review of the Paper (available in this repository) that was published to interpret the data and develop a statistical model in predictive mainatainence area. 

In all the 3 experiments - at least one bearing failed at the end of the experiment, and one or more of them performed well past their normal lifetime. 

We show the statistical data of the failed bearings in each of the experiments. 

We have charted the data and done the stats analysis at the **start**, the approximate **middle**, and at the **end** of the experiments. 

At this time we have only used the data from Test Set 2 and Test Set 3, since it was easier to handle and point out the failures. 

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

#### Raw plots - 

One example is shown here for brevity. This shows an datapoints for a single test setup - i.e. 1 second readings of ~20,000 values. 
All 4 channels representing the 4 bearings in the tests are concatenated (using `df.melt`) and plotted. 

<center>
    <img src = images/test2_start_smooth_line.png height = 75% width = 75% / >
</center>

#### Simple Stats (Min, Max, Mean, Median, Mode and Std)

For the same test we calculate and show the values of typical statistical compuations. 

<center>
    <img src = images/test2_start_Simple_Stats.png height = 75% width = 75% / >
</center>

#### Advanced Plots (Skewness, Kurtosis and RMS values)

Next, we look at some advanced Statistical functions that are calculated on each channel data. 

<center>
    <img src = images/test2_start_Advance_Stats.png height = 75% width = 75% / >
</center>



## End of Experiment data analysis for each test

#### Raw plots - 

#### Test 2

<center>
    <img src = images/test2_end_smooth_line.png width = 100% / >
</center>

Failure in **bearing 1** 
Bearings 2, 3 and 4 - did not exhibit any defects. 

#### Test 3

<center>
    <img src = images/test3_end_smooth_line.png width = 100% / >
</center>

Failure in **bearing 3**
Bearings 1, 2 and 4 did not exhibit any defects. 

#### Simple Stats (Min, Max, Mean, Median, Mode and Std)
#### Test 2

<center>
    <img src = images/test2_end_Simple_Stats.png width = 100% />
</center>

Failure in **bearing 1** 
Bearings 2, 3 and 4 - did not exhibit any defects. 

#### Test 3

<center>
    <img src = images/test3_end_Simple_Stats.png width = 100% />
</center>

Failure in **bearing 3**
Bearings 1, 2 and 4 did not exhibit any defects. 


#### Advanced Plots (Skewness, Kurtosis and RMS values)
#### Test 2

<center>
    <img src = images/test2_end_Advance_Stats.png width = 100% />
</center>

Failure in **bearing 1** 
Bearings 2, 3 and 4 - did not exhibit any defects. 

#### Test 3

<center>
    <img src = images/test3_end_Advance_Stats.png width = 100% />
</center>

Failure in **bearing 3**
Bearings 1, 2 and 4 did not exhibit any defects. 


## Summary of the Bearing Analysis Paper

The paper presents a wavelet filter-based method for the detection of weak signatures in signals, particularly applied to the prognostics of rolling element bearings.

### Key points:

**Importance of Bearing Prognostics:** Bearing failure is a major cause of breakdowns in rotating machinery, leading to costly downtime. Prognostics, or early detection of bearing defects, allows for timely maintenance and prevents catastrophic failures.

**Challenges in Bearing Fault Detection:** The vibration signals from defective bearings are often weak and masked by noise, making early detection difficult. Additionally, signal modulation effects further complicate the analysis.

**Wavelet Transform for Signal Analysis:** The wavelet transform is a powerful tool for signal analysis due to its ability to represent signals in both time and frequency domains. It has been used for signal demodulation and de-noising in bearing diagnostics.

**Limitations of Traditional Wavelet De-noising:** Traditional wavelet decomposition-based de-noising methods may not be effective for impulse-like signals, which are common in machinery diagnostics. These methods rely on the sparseness of wavelet coefficients, which may not be achieved for impulse signals.

**Proposed Wavelet Filter Method:** The paper proposes a Morlet wavelet filter-based method to address the limitations of traditional de-noising. The Morlet wavelet, due to its shape similarity to mechanical impulses, is well-suited for detecting impulse-like bearing defect signatures.

**Optimal Wavelet Filter Construction:** A two-step optimization process is proposed to construct an optimal wavelet filter. The first step involves selecting the optimal shape factor of the Morlet wavelet based on minimal Shannon entropy. The second step involves choosing the appropriate scale for the wavelet transform based on singular value decomposition (SVD) to reveal the periodicity of the signal.

**Experimental Validation:** The proposed method is validated using data collected from bearing run-to-failure tests. The results demonstrate the effectiveness of the method in enhancing weak periodic impulse signatures and enabling early detection of bearing defects.

In conclusion, the paper presents a wavelet filter-based method for weak signature detection in bearing prognostics. The proposed method addresses the limitations of traditional wavelet de-noising methods and demonstrates its effectiveness in enhancing weak periodic impulse signatures, enabling early detection of bearing defects and facilitating timely maintenance actions.

### Statistical Methods suggested to model predictive diagnostics

The paper emphasizes the importance of detecting periodic impulses within the vibration signal, which indicate defects in the bearing. To achieve this, the paper primarily focuses on two statistical measures:

**Root Mean Square (RMS):** RMS is used to quantify the overall energy or amplitude of the vibration signal. An increasing trend in RMS over time can suggest the progression of bearing damage.

**Kurtosis:** Kurtosis measures the "peakedness" of the signal distribution. Higher kurtosis values indicate the presence of impulses or sharp peaks in the signal, which are characteristic of bearing defects.

In addition to these, the paper also employs **Shannon entropy** to assess the sparseness of wavelet coefficients during the wavelet filter optimization process. However, Shannon entropy is not directly applied to the raw vibration data points themselves.

Therefore, for each of our 20KHz accelerometer data points, we should primarily calculate the RMS and Kurtosis. 

These two statistical measures will provide insights into the overall energy of the vibration and the potential presence of impulse-like features indicative of bearing defects.



## Time Series data - initial analysis

First we show a test that showed no defect in the bearings at the conclusion of the test. 

For this we look at Test 2, bearing 3 - i.e. data from channel 3

<center>
    <img src = images/Test_2_Channel_3.png width = 100% />
</center>


Next, we see the test where the bearing had a defect at the end of the experiment. 

Test 2, bearing 1 - i.e. data from Channel 1. 

<center>
    <img src = images/Test_2_Channel_1.png width = 100% />
</center>
