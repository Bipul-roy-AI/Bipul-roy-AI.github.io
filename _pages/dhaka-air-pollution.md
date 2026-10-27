---
title: "Dhaka Air Pollution Research"
layout: page
permalink: /research/dhaka-air-pollution/
---

<p><a href="{{ '/research/' | relative_url }}">← Back to all research projects</a></p>

# Dhaka | Air-pollution dynamics, climate context &amp; exposure indicators

<section class="research-feature" id="dhaka-results" markdown="0">
<h2>Research showcase: Dhaka air pollution and climate</h2>
<p class="research-feature-intro">An independent environmental data-science investigation of Dhaka's <strong>2000–2025 archived pollution series</strong>, monthly climate reanalysis, satellite indicators and exploratory machine-learning models. The results and figures below are actual outputs from the published repository. <strong>Verification is ongoing:</strong> the historical PM2.5 record has a major possible source/aggregation discontinuity around August 2022, so apparent long-term trends and model scores must not be treated as independently validated atmospheric findings.</p>
<p><strong>Data:</strong> compiled historical air-quality records (original provenance under review), MODIS AOD/LST, Sentinel-5P NO₂, ERA5-Land variables. <strong>Methods:</strong> monthly descriptive statistics, Mann–Kendall and change-point tests, PCA, correlations, VIF, and chronological model evaluations. <strong>Health:</strong> relevance to exposure, <em>not</em> measured illness or mortality.</p>
<div class="research-stats">
<div><strong>312</strong><span>Archived monthly periods (2000–2025)</span></div>
<div><strong>267 / 312</strong><span>AOD availability flags</span></div>
<div><strong>91 / 312</strong><span>Satellite NO₂ availability flags</span></div>
<div><strong>24</strong><span>Held-out test months (2024–2025)</span></div>
</div>

<h3>Selected exploratory findings</h3>
<ul>
<li><strong>Data-source comparability is the key uncertainty.</strong> The processed monthly PM2.5 field changes from <strong>148.02 (July 2022)</strong> to <strong>29.65 (August 2022)</strong>, while the <code>observations</code> field changes from 744 to 1,392. The break has not been independently explained; it cannot be called a real air-quality improvement.</li>
<li><strong>Long-term trends are currently provisional.</strong> The archive contains annual and seasonal patterns, Mann–Kendall tests, and change-point outputs. Different input regimes or generated values may distort these statistics, so no independently validated long-term trend is claimed.</li>
<li><strong>Satellite coverage varies.</strong> The 312-month data table marks AOD available in <strong>267</strong> months, LST in <strong>271</strong>, and satellite NO₂ in only <strong>91</strong>. The sensor histories and missingness must be respected.</li>
<li><strong>Correlations do not prove pollutant sources or climate causes.</strong> The archived PM2.5–PM10 correlation is <strong>r = 0.992</strong>. Several predictor VIF values are high (dewpoint <strong>47.86</strong>, temperature <strong>33.98</strong>), making simple individual-driver explanations unreliable.</li>
<li><strong>Machine learning was tested, not yet independently reproduced.</strong> The saved forecasting Linear Regression score is test <strong>R² = 0.788</strong>, RMSE <strong>12.21</strong>; its validation RMSE is <strong>38.79</strong>. The environmental-feature track performs poorly on the held-out test period, with negative R² values. Source breaks, baselines and temporal leakage remain unverified.</li>
<li><strong>No measured health outcome is inferred.</strong> There are no linked medical, mortality or population exposure records in this project; it must not be presented as estimating disease burden or causal health impacts.</li>
</ul>

<h3>Figures and data-quality evidence</h3>
<p>The first figure is a new diagnostic based directly on the published monthly table. The other six figures are existing repository research outputs. These are displayed to document the analysis, <strong>not as validated monitoring-station results</strong>.</p>
<div class="research-evidence-grid">
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/research_docs/figures/pm25_source_discontinuity.svg" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/research_docs/figures/pm25_source_discontinuity.svg" alt="Source-quality diagnostic — derived from archived Dhaka analysis; validation pending" loading="lazy"></a>
<figcaption><strong>Source-quality diagnostic.</strong> The monthly PM2.5 series shifts abruptly around August 2022, while the observation-count field changes. An unresolved source/aggregation boundary, not a confirmed pollution decrease.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_1_Dhaka_PM25_Annual_Trend.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_1_Dhaka_PM25_Annual_Trend.png" alt="Apparent long-term pattern — derived from archived Dhaka analysis; validation pending" loading="lazy"></a>
<figcaption><strong>Apparent long-term pattern.</strong> Archived annual trend across 2000–2025. Source continuity has not been verified, so this is not a defensible long-term atmospheric trend.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_2_Dhaka_Observation_Count.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_2_Dhaka_Observation_Count.png" alt="Observation counts — derived from archived Dhaka analysis; validation pending" loading="lazy"></a>
<figcaption><strong>Observation counts.</strong> The archived count changes between source regimes and still needs a precise definition.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_3_Dhaka_PM25_Monthly_Seasonal_Cycle.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_3_Dhaka_PM25_Monthly_Seasonal_Cycle.png" alt="Monthly seasonal cycle — derived from archived Dhaka analysis; validation pending" loading="lazy"></a>
<figcaption><strong>Monthly seasonal cycle.</strong> Exploratory pooled seasonal PM2.5 pattern. Source changes and missingness may affect the cycle.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_4_Dhaka_PM25_Monthly_Boxplot.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_4_Dhaka_PM25_Monthly_Boxplot.png" alt="Monthly distributions — derived from archived Dhaka analysis; validation pending" loading="lazy"></a>
<figcaption><strong>Monthly distributions.</strong> Archived month-by-month PM2.5 distributions, shown without a claim of independent measurement validity.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_5_Dhaka_Extreme_PM25_Frequency_by_Month.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_5_Dhaka_Extreme_PM25_Frequency_by_Month.png" alt="Extreme-frequency screening — derived from archived Dhaka analysis; validation pending" loading="lazy"></a>
<figcaption><strong>Extreme-frequency screening.</strong> Archived frequency of threshold-defined events by month. Interpretation awaits threshold, unit and source checks.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_6_Dhaka_Annual_Extreme_PM25_Frequency.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/main/Phase_3_Climate_Integration/figures/Figure_6_Dhaka_Annual_Extreme_PM25_Frequency.png" alt="Yearly extreme-frequency screening — derived from archived Dhaka analysis; validation pending" loading="lazy"></a>
<figcaption><strong>Yearly extreme-frequency screening.</strong> Archived annual extreme event frequencies; source discontinuity may influence comparisons.</figcaption>
</figure>
</div>

<h3>Preliminary model evaluation (published output)</h3>
<p>These scores have not been rerun here. Because target units and source comparability require verification, numerical accuracy should not be interpreted as verified operational forecast performance.</p>
<table>
<thead><tr><th>Track / model</th><th>Validation RMSE</th><th>Test RMSE</th><th>Test R²</th></tr></thead>
<tbody>
<tr><td>Forecasting · Linear Regression</td><td>38.79</td><td>12.21</td><td>0.788</td></tr>
<tr><td>Forecasting · Ridge</td><td>40.14</td><td>12.47</td><td>0.778</td></tr>
<tr><td>Forecasting · Random Forest</td><td>67.22</td><td>17.75</td><td>0.551</td></tr>
<tr><td>Forecasting · XGBoost</td><td>64.88</td><td>18.03</td><td>0.537</td></tr>
<tr><td>Environmental-feature design · Linear Regression</td><td>62.69</td><td>68.10</td><td>−5.609</td></tr>
<tr><td>Environmental-feature design · Random Forest</td><td>60.81</td><td>89.51</td><td>−10.419</td></tr>
</tbody>
</table>
<p>Original CSV: <a href="https://github.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/blob/main/Phase_3_Modeling/results/model_evaluation_metrics.csv">model evaluation metrics</a>. The environmental-feature model is not a causal attribution study.</p>

<h3>Methods, data &amp; reproduction</h3>
<ul>
<li><a href="https://github.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/tree/main/Phase_2_Pollution_Dynamics">Phase 2: historical pollution dynamics and computed statistics</a></li>
<li><a href="https://github.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/tree/main/Phase_3_Climate_Integration">Phase 3: remote sensing, reanalysis and processed 312-month table</a></li>
<li><a href="https://github.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/tree/main/Phase_3_Modeling">Phase 3.3: chronological dataset splits, metrics and prediction exports</a></li>
<li><a href="https://github.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence/blob/main/research_docs/DATA_PROVENANCE_AND_VALIDATION.md">Data provenance, unresolved source issues and verification checklist</a></li>
<li><a href="https://github.com/Albab-Hasan/Bangladesh-District-Level-Weather-Pollution-DataSet/tree/main/data">Additional 2025+ district dataset: OpenWeatherMap-derived comparison candidate (not integrated)</a></li>
</ul>

<h3>What this research does not establish</h3>
<p>The complete 2000–2025 air-quality input series has not been verified as a consistent DoE station record. A source-regime change may explain the apparent 2022 decrease. Trend significance, causal meteorological relationships, exact exposure estimates, health outcomes, and reliable prospective forecast accuracy are <strong>not established</strong>. The repository does not yet include a complete clean-rerun pipeline for the archived preprocessing and models.</p>
<p class="research-links"><a href="https://github.com/Bipul-roy-AI/Dhaka-Air-Pollution-Climate-Health-Intelligence">Explore the Dhaka research repository, results and datasets →</a></p>
</section>

<section class="research-ongoing" markdown="0">
<h2>Further verification is ongoing</h2>
<p>Next steps: verify the original hourly data and source-generation chain; distinguish official DoE monitoring from model-based Open-Meteo/CAMS and OpenWeatherMap products; harmonize units and timestamps; reconstruct source-consistent subperiod trends; check satellite retrieval coverage; and rerun statistical and predictive models with training-only preprocessing, seasonal baselines and source-aware sensitivity tests. Existing raw and computed files remain preserved.</p>
</section>
