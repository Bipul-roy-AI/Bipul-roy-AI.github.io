---
title: "Seasonal Air Pollution, Weather and Atmospheric Conditions in Dhaka, Bangladesh"
layout: page
permalink: /research/dhaka-air-pollution/
---

<p><a href="{{ '/research/' | relative_url }}">← Back to all research projects</a></p>

# Seasonal Air Pollution, Weather and Atmospheric Conditions in Dhaka, Bangladesh

<section class="research-feature" id="dhaka-results" markdown="0">
<p class="research-feature-intro">How does observed particulate pollution vary through the year in Dhaka? How much predictive information does weather add beyond pollution persistence and the calendar? This study combines an <strong>observed embassy PM₂.₅ record for 2016–2021</strong>, documented NASA meteorology and a credited reproduction of the <strong>2017–2022 HyAQMet regional reanalysis release</strong>. It separates observed patterns, conditional prediction and regional-product agreement, with uncertainty reported beside the findings.</p>
<div class="research-stats">
<div><strong>2,117</strong><span>Observed daily PM₂.₅ values, 2016–2021</span></div>
<div><strong>96.58%</strong><span>Daily record coverage; 75 days remain missing</span></div>
<div><strong>5.13×</strong><span>Available-day winter / monsoon mean</span></div>
<div><strong>1,752</strong><span>Paired days for regional-product comparison</span></div>
</div>

<h2>Research questions and data</h2>
<ul>
<li>What monthly and seasonal concentration patterns are supported by the observed record, and does its short trend differ clearly from zero?</li>
<li>How do weather associations change after seasonal adjustment, and does lagged meteorology improve prediction beyond temporal baselines?</li>
<li>Which published reanalysis results can be reproduced, and how closely does regional CAMS PM₂.₅ agree with the monitored location?</li>
</ul>
<p><strong>Observed data:</strong> EPA-hosted U.S. Embassy daily figure-support observations, 2016–2021. <strong>Weather:</strong> NASA POWER/MERRA-2 UTC daily temperature, dewpoint, humidity, wind, rainfall and pressure at the embassy coordinates. <strong>Regional air quality and weather:</strong> HyAQMet’s exact deposited release and public ERA5-Land, ERA5 Single Levels, CAMS EAC4 and MERRA-2 extracts. The processed extracts were checked; original gridded NetCDF acquisition was not repeated. These are distinct source types, with different spatial support.</p>
<figure class="research-evidence research-evidence--location">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/85d25f2810e571ca332d958d0d6e0b674d1f8ca5/figures/study_area.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/dhaka/study-area.webp' | relative_url }}" alt="Bangladesh country context locating Dhaka" loading="lazy"></a>
<figcaption><strong>Study location.</strong> Bangladesh country context marking Dhaka. This location map does not define an official city boundary or show a pollution surface. <a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/85d25f2810e571ca332d958d0d6e0b674d1f8ca5/figures/study_area.svg">Editable SVG</a> · <a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/85d25f2810e571ca332d958d0d6e0b674d1f8ca5/figures/study_area.pdf">Figure PDF</a>.</figcaption>
</figure>

<h2>1. Observed seasonality is strong; the short-period trend remains uncertain</h2>
<p>The record contains <strong>2,117 of 2,192 calendar days</strong>. Available-day PM₂.₅ mean is <strong>87.18 µg/m³</strong>, median <strong>60.71</strong> and maximum daily value <strong>340.79</strong>. January has the highest pooled monthly mean, <strong>193.29 µg/m³</strong>, and July the lowest, <strong>30.16</strong>.</p>
<table>
<thead><tr><th>Seasonal window</th><th>Observed / calendar days</th><th>Mean PM₂.₅, µg/m³</th></tr></thead>
<tbody>
<tr><td>Winter, December–February</td><td>527 / 542</td><td><strong>172.02</strong></td></tr>
<tr><td>Pre-monsoon, March–May</td><td>525 / 552</td><td>76.40</td></tr>
<tr><td>Monsoon, June–September</td><td>711 / 732</td><td><strong>33.53</strong></td></tr>
<tr><td>Post-monsoon, October–November</td><td>354 / 366</td><td>84.61</td></tr>
</tbody>
</table>
<p>The winter mean is about <strong>five times</strong> the monsoon mean. The unequal seasonal windows and missing days require separate coverage denominators. These are point-monitor summaries, not population-wide exposure estimates.</p>
<div class="research-evidence-grid">
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/main/figures/01_seasonality.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/dhaka/seasonality.webp' | relative_url }}" alt="Observed calendar-month and seasonal PM2.5 means with weighting sensitivity" loading="lazy"></a>
<figcaption><strong>Observed seasonal cycle.</strong> Calendar-month summaries are primary. Equal-year weighting is also shown to expose sensitivity to available-day coverage.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/main/figures/02_trend.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/dhaka/trend.webp' | relative_url }}" alt="Annual observed PM2.5 means and season-adjusted trend whose interval includes zero" loading="lazy"></a>
<figcaption><strong>Trend uncertainty.</strong> The season-adjusted slope is +0.677 µg/m³/year, with a 12-month block interval of −0.166 to +1.533. The interval includes zero.</figcaption>
</figure>
</div>
<p><strong>Meaning:</strong> Seasonality is clear, but an increasing short-period trend is <strong>not established</strong>. Sixty-nine of 72 months meet the ≥75% daily-coverage screen; both six- and 12-month block intervals span zero. This does not prove that concentrations were unchanged, and six years cannot identify a climate-change effect.</p>
<p><strong>High-concentration days:</strong> 2,068 observed days (<strong>97.69%</strong>) exceed the WHO 2021 daily benchmark of 15 µg/m³, applied retrospectively. A pooled 95th percentile of <strong>212.77 µg/m³</strong> identifies 56 observed exceedance runs; the longest uninterrupted observed run is six days. Missing days may censor longer episodes. These indicators do not calculate AQI, legal compliance or health outcomes.</p>

<h2>2. Seasonal adjustment changes weather interpretation</h2>
<p>Temperature–PM₂.₅ Pearson correlation changes from <strong>−0.755</strong> unadjusted to <strong>−0.077</strong> after calendar-month adjustment; pressure changes from <strong>+0.736</strong> to <strong>+0.068</strong>. Adjusted humidity, wind and rainfall correlations are approximately −0.328, −0.260 and −0.184. Shared seasonality explains much of some raw relationships; residual associations remain descriptive.</p>
<p>The prediction experiment uses fixed-penalty Ridge regression, training-fold imputation/scaling, calendar terms and past PM₂.₅ values. Training begins in 2016–2017, followed by monthly expanding refits and daily observed-lag updates. The primary weather branch uses <strong>lag-two UTC weather</strong>, because previous-UTC-day weather can overlap the beginning of a local target day. Actual publication latency remains unverified.</p>
<table>
<thead><tr><th>2020–2021 model, same 670 observed days</th><th>MAE, µg/m³</th><th>RMSE, µg/m³</th></tr></thead>
<tbody>
<tr><td>Previous-day persistence</td><td>19.90</td><td>29.51</td></tr>
<tr><td>Calendar climatology</td><td>25.56</td><td>37.00</td></tr>
<tr><td>365-day seasonal baseline</td><td>34.10</td><td>49.26</td></tr>
<tr><td>Ridge: PM₂.₅ lags + calendar</td><td>18.84</td><td><strong>27.74</strong></td></tr>
<tr><td>Ridge + conservative lag-two weather</td><td>18.77</td><td><strong>27.48</strong></td></tr>
</tbody>
</table>
<p>MAE is mean absolute error; RMSE gives larger errors more weight. Lower values are better. These are retrospective daily predictions, not certified operational forecasts.</p>
<div class="research-evidence-grid">
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/main/figures/03_weather_associations.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/dhaka/weather-associations.webp' | relative_url }}" alt="Weather correlations before and after calendar adjustment" loading="lazy"></a>
<figcaption><strong>Raw versus adjusted associations.</strong> Temperature and pressure correlations weaken markedly after accounting for calendar timing. Correlation does not isolate causal effects.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/main/figures/04_prediction.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/dhaka/prediction.webp' | relative_url }}" alt="Common-case retrospective prediction scores for baselines and conservative weather model" loading="lazy"></a>
<figcaption><strong>Baseline-controlled prediction.</strong> Calendar and pollutant lags improve on persistence in the inspected comparison. Added weather makes only a small later-period difference.</figcaption>
</figure>
</div>
<p><strong>Meaning:</strong> Extra weather skill depends on the period. On <strong>697 paired core/weather days</strong> in 2020–2021, weather-minus-core RMSE is <strong>−0.325 µg/m³</strong>, with a 30-day block interval of <strong>−0.810 to +0.382</strong>. It spans zero, so later-period benefit is not established. The paired set differs from the 670-day all-model intersection. In 2018–2019, 703 paired days give −1.274, with an interval of −1.847 to −0.278. These conditional results do not establish universal model superiority.</p>

<h2>3. Regional reanalysis tracks variation while retaining concentration differences</h2>
<p>HyAQMet CAMS PM₂.₅ and the embassy reference have <strong>1,752 paired days</strong> in 2017–2021: <strong>r = 0.897</strong>, <strong>bias = +16.15 µg/m³</strong>, MAE 24.98 and <strong>RMSE = 34.23</strong>. Bias is regional model minus observation. On 57 eligible months using identical paired days for both means, r is 0.955 and RMSE is 24.59 µg/m³.</p>
<div class="research-evidence-grid">
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/main/figures/reference/independent_reference_comparison.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/dhaka/regional-comparison.webp' | relative_url }}" alt="Conditional regional CAMS and point-monitor PM2.5 comparison" loading="lazy"></a>
<figcaption><strong>Agreement and bias.</strong> High correlation coexists with a positive concentration difference. Daily timing and regional-versus-point support remain qualifications.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/main/figures/reference/pollutant_climatology.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/dhaka/regional-climatology.webp' | relative_url }}" alt="Monthly and local-hour pollutant climatologies reproduced from the HyAQMet release" loading="lazy"></a>
<figcaption><strong>Regional air-quality patterns.</strong> Monthly and hourly curves describe regional reanalysis fields; interpolation does not create independent hourly measurements.</figcaption>
</figure>
</div>
<p><strong>Meaning:</strong> Tracking day-to-day variation does not remove systematic concentration bias or make a regional field equivalent to a point monitor. BST/UTC and ±1-day sensitivities remain visible. A partial-period AirNow mirror supports local daily labels for 523 of 530 daily means, but does not certify the full record’s averaging or QA rules.</p>

<h2>4. Atmospheric mixing and data quality</h2>
<p>The final HyAQMet release reproduces <strong>52,584 hourly rows and 42 fields</strong>. Its four source products are ERA5-Land, ERA5 Single Levels, CAMS EAC4 and MERRA-2. The direct hourly boundary-layer-height–PM₂.₅ correlation is <strong>−0.4904</strong>, compared with −0.65 printed in the paper; the reason remains unresolved. The lowest/highest boundary-layer decile contrast is <strong>3.036×</strong>, consistent with its approximate threefold result.</p>
<p>Paper and release six-season labels disagree at <strong>13,968 hours</strong>. Both definitions are reported as separate sensitivities, with calendar months primary. The final precipitation field sums to <strong>20,142–33,893 mm/year if treated as hourly water amounts</strong>. These are suspect diagnostic sums, not validated rainfall totals. Native accumulation metadata is needed before repair, and this field was not used for the NASA-weather prediction experiment. Reproduction credits the original authors and preserves released values.</p>

<h2>Limits, further work and research materials</h2>
<p>Remaining priorities are full-record station QA and timing, documented provider latency, native precipitation metadata, additional monitoring locations and a prospective evaluation period. The observed record cannot support causal emissions, personal-exposure, health-outcome or source-apportionment claims. An earlier archive with a numerical discontinuity around 4 August 2022 is excluded from the primary observed study; the <a href="https://github.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/blob/main/DATA_SELECTION.md">data-selection note</a> explains that decision.</p>
<p class="research-links"><a href="https://github.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research">Read the research and methods →</a> <a href="https://github.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/tree/main/results">Numeric results ↗</a> <a href="https://github.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/blob/main/REPRODUCE.md">Reproduce the analysis ↗</a></p>
<p>Map and reanalysis reproduction graphics include <a href="https://github.com/Bipul-roy-AI/Dhaka-Air-Quality-Climate-Research/tree/main/figures/reference">600 dpi PNG, editable SVG and figure-only PDF exports</a>. </p>
<h3>Original sources and credit</h3>
<ul>
<li><strong>Golam Sarwar / U.S. EPA:</strong> <a href="https://doi.org/10.23719/1528454">published embassy observations and figure-support data</a>.</li>
<li><strong>NASA POWER / MERRA-2:</strong> <a href="https://power.larc.nasa.gov/">documented daily meteorology</a>.</li>
<li><strong>Adity Barua and Mrinal Basak Shuvo:</strong> <a href="https://doi.org/10.5281/zenodo.20705735">HyAQMet deposited dataset</a>; <strong>Barua and coauthors:</strong> <a href="https://doi.org/10.1002/gdj3.70111">HyAQMet source paper</a>.</li>
<li><strong>Ryza Rynazal / AirNow DOS providers:</strong> <a href="https://doi.org/10.6084/m9.figshare.12687695.v2">secondary hourly archive</a>, used as a same-station sensitivity check.</li>
<li><strong>World Health Organization:</strong> <a href="https://www.who.int/publications/i/item/9789240034228">2021 air-quality guidelines</a>.</li>
</ul>
</section>
