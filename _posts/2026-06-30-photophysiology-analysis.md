# Photophysiology Analysis: Light vs. Dark Algal Samples

## Overview

This project analyzes photophysiology data from algal samples exposed to two treatments: **Dark** and **Light**.

The aim of the analysis was to compare photosynthetic performance between the two treatments using fitted parameters extracted from rapid light-response curves. The data were organized into a tidy format suitable for R, analyzed statistically, and visualized using graphs.

## Samples and Algal Taxa

The analysis included **19 samples** in total: **8 Dark samples** and **11 Light samples**.

## Dark Treatment Samples

| Sample ID | Taxon |
|---|---|
| Dark_1 | Colpomenia |
| Dark_2 | Dictyota |
| Dark_3 | Sargassum |
| Dark_4 | Padina |
| Dark_5 | Jania |
| Dark_6 | Red UNK |
| Dark_7 | Ulva |
| Dark_8 | Galxaura |

## Light Treatment Samples

| Sample ID | Taxon |
|---|---|
| Light_1 | Jania |
| Light_2 | Halopteris |
| Light_4 | Sargassum |
| Light_5 | Hypnea |
| Light_6 | Cudiom |
| Light_7 | Padina |
| Light_8 | Cistosera |
| Light_10 | Galaxaura |
| Light_11 | Dictyota |
| Light_12 | Colpomenia |
| Light_13 | Ulva |

Two samples appeared in the metadata but were not included in the final analysis because fitted parameter values were missing: `Light_3` and `Light_9`.

## Photophysiology Parameters

| Parameter | Meaning |
|---|---|
| `Am` | **Maximum photosynthetic rate**. This represents the estimated maximum photosynthetic or electron transport capacity of the sample. |
| `AQY` | **Apparent Quantum Yield**. This represents the efficiency of photosynthesis under low light and is based on the initial slope of the light-response curve. |
| `Rd` | **Dark respiration**. This represents the estimated respiration or metabolic loss in darkness. |
| `Ik` | **Saturation irradiance**. This represents the light intensity at which photosynthesis begins to saturate. It is often estimated as `Am / AQY`. |

## Data Preparation

The original files used were:

- `dark_group_photo_parameters.csv`
- `light_group_photo_parameters.csv`
- `Photophysiology_metadata.csv`

The data were reorganized into tidy format, where each row represents one sample, one treatment, one parameter, and one value. This format is suitable for analysis in R.

## Statistical Analysis

The statistical analysis was performed in R.

For each parameter, summary statistics were calculated separately for the Dark and Light treatments. These included sample size, mean, standard deviation, minimum, quartiles, median, and maximum.

Two statistical tests were used to compare the treatments:

1. **Welch two-sample t-test**  
   This test was used because it compares two groups and does not assume equal variance between them.

2. **Mann-Whitney test**  
   This test was used as a non-parametric alternative because the sample size was small.

Because four different parameters were tested, p-values were adjusted using the **Benjamini-Hochberg correction** to account for multiple comparisons.

## Figures

## Figure 1. Parameter Distributions by Treatment

This figure shows boxplots and individual sample points for each photophysiology parameter in the Dark and Light treatments.

![Figure 1: Boxplots](Figure_1_boxplots.png)

## Figure 2. QQ Plots

This figure shows QQ plots used to visually inspect whether the data strongly deviate from normality.

![Figure 2: QQ plots](Figure_2_QQ_plots.png)

## Figure 3. Mean Values ± Standard Error

This figure summarizes the mean value of each parameter for the Dark and Light treatments, with standard error bars.

![Figure 3: Means and SE](Figure_3_means_SE.png)

## Results

## `Am` - Maximum Photosynthetic Rate

Light-treated samples had a slightly higher mean `Am` than dark-treated samples.

| Treatment | Mean Am |
|---|---:|
| Dark | 18.08 |
| Light | 21.52 |

This suggests that the Light samples may have a higher maximum photosynthetic capacity.

## `AQY` - Apparent Quantum Yield

Dark-treated samples had a higher mean `AQY` than light-treated samples.

| Treatment | Mean AQY |
|---|---:|
| Dark | 0.190 |
| Light | 0.137 |

This may suggest that the Dark samples are more efficient under low-light conditions.

## `Ik` - Saturation Irradiance

Light-treated samples had a higher mean `Ik` than dark-treated samples.

| Treatment | Mean Ik |
|---|---:|
| Dark | 104.38 |
| Light | 153.42 |

This suggests that Light samples may tolerate or require higher light levels before photosynthesis reaches saturation.

## `Rd` - Dark Respiration

Light-treated samples had more negative mean `Rd` values than dark-treated samples.

| Treatment | Mean Rd |
|---|---:|
| Dark | -0.031 |
| Light | -0.165 |

This pattern should be interpreted carefully because `Rd` depends on the fitted model and showed high variability.

## Statistical Results

Although several biological trends were observed, none of the treatment differences were statistically significant after correction for multiple testing.

Welch test adjusted p-values:

| Parameter | Adjusted p-value |
|---|---:|
| AQY | 0.082 |
| Ik | 0.142 |
| Rd | 0.275 |
| Am | 0.568 |

The smallest adjusted p-value was observed for `AQY`, suggesting that low-light photosynthetic efficiency may be the strongest trend in the dataset. However, this result was still not statistically significant at α = 0.05.

## Biological Interpretation

The results suggest possible physiological differences between the Dark and Light treatments.

Light-treated samples tended to show higher maximum photosynthetic capacity, represented by `Am`, and higher saturation irradiance, represented by `Ik`. This may indicate that light-treated algae are better adapted to stronger light conditions.

Dark-treated samples tended to show higher apparent quantum yield, represented by `AQY`. This may indicate better photosynthetic efficiency under low-light conditions, which is consistent with adaptation to darker environments.

However, the statistical tests did not show significant differences after correction for multiple testing. Therefore, these results should be interpreted as biological trends rather than confirmed treatment effects.

The lack of statistical significance may be due to small sample size, high variability among samples, differences between algal taxa, and natural biological variation.

## Conclusion

This analysis shows that algal samples from Light and Dark treatments may differ in their photophysiological responses.

The Light samples showed trends toward higher maximum photosynthetic capacity and higher saturation irradiance. The Dark samples showed a trend toward higher low-light photosynthetic efficiency.

Overall, the results suggest that light conditions may influence photophysiological traits. However, because the differences were not statistically significant, additional samples would be needed to confirm this pattern.
