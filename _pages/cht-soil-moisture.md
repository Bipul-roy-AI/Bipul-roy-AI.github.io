---
title: "CHT Soil Moisture & Forest Ecohydrology"
layout: page
permalink: /research/cht-soil-moisture/
---

<p><a href="{{ '/research/' | relative_url }}">← Back to all research projects</a></p>

# Chittagong Hill Tracts | Soil-moisture gap filling & forest ecohydrology

<section class="research-feature" id="cht-results" markdown="0">
<h2>Research showcase: can machine learning reconstruct missing satellite soil-moisture observations?</h2>
<p class="research-feature-intro">The hill forests of <strong>Bandarban, Khagrachhari and Rangamati</strong> receive strongly seasonal monsoon rainfall, but satellite observations of soil moisture, vegetation and evapotranspiration have important quality and availability gaps. This independent study combines a <strong>2017–2022 forest ecohydrology context</strong> with <strong>2019–2022 quality-controlled SMAP machine-learning experiments</strong>. It evaluates reconstruction against held-out <em>SMAP satellite retrievals</em>, not against field soil-moisture instruments.</p>
<p><strong>Data:</strong> SMAP enhanced L3 AM soil moisture, Sentinel-1 radar, CHIRPS v3 rainfall, MODIS EVI, MOD16A2GF modeled evapotranspiration and terrain. <strong>Methods:</strong> Earth Engine, Python/Jupyter, QA screening, chronological train/validation/test splits, baselines, Random Forest, Ridge and XGBoost.</p>

<div class="research-stats">
  <div><strong>7.11%</strong><span>QA-accepted SMAP posting-date records (17,653 of 248,400 sampled)</span></div>
  <div><strong>0.0555</strong><span>2022 held-out XGBoost RMSE (m³/m³), against SMAP only</span></div>
  <div><strong>20.8%</strong><span>Lower test RMSE than a calendar-month baseline</span></div>
  <div><strong>15 / 72</strong><span>Monsoon district-months passing both EVI/ET support screens</span></div>
</div>

<h3>Study area and objectives</h3>
<p>The analysis uses a local three-district polygon rather than the rectangular proxy used by an earlier exploratory prototype. The boundary source/license needs independent confirmation; the map illustrates the study domain and is <em>not</em> an official administrative or surveyed boundary.</p>
<ol>
  <li>Measure where and when acceptable SMAP soil-moisture retrievals are available.</li>
  <li>Test whether machine learning reconstructs withheld, QA-accepted SMAP observations better than simple baselines.</li>
  <li>Check the contribution of radar and vegetation predictors and how results change under temporal and spatial holdouts.</li>
  <li>Explain rainfall seasonality and the observation limitations of forest greenness and modeled ET.</li>
</ol>

<h3>Main results, in plain language</h3>
<ul>
  <li><strong>A — Usable SMAP data are sparse.</strong> Only <strong>17,653 of 248,400</strong> sampled grid-posting × date rows were QA accepted (7.11%), spanning 39 accepted grid postings and 663 accepted dates. This is a sample acceptance rate, <em>not</em> a percentage of the landscape or an independent footprint count.</li>
  <li><strong>B — XGBoost improved held-out satellite-product reconstruction.</strong> The study trained on 2019–2020, selected models on 2021, and reserved 2022 for testing. On 4,042 QA-accepted test rows over 143 dates, XGBoost obtained <strong>RMSE 0.0555 m³/m³ and R² 0.544</strong>. The calendar-month baseline RMSE was 0.0701; the overall training-mean baseline was 0.0821. Scores are date-balanced.</li>
  <li><strong>C — Radar was useful, while vegetation added little extra validation improvement.</strong> In the 2021 validation comparison, XGBoost with climate/terrain/calendar predictors had RMSE 0.06147; adding radar gave 0.05996; including both radar and vegetation gave 0.05990. These are predictive comparisons, <em>not</em> proof of causal ecohydrological controls.</li>
  <li><strong>D — Unseen locations remain challenging.</strong> A separate future-date/held-out-grid experiment achieved RMSE <strong>0.0621 m³/m³</strong> on 8 held-out postings and 903 records. It is a different model/sample from the temporal test, so direct score comparison would be misleading.</li>
  <li><strong>E — Monsoon rainfall is pronounced, but paired EVI/ET evidence is limited.</strong> June–September accounted for about <strong>71–79%</strong> of mean annual district rainfall across 2017–2022. Only <strong>15 of 72</strong> June–September district-months passed both exploratory EVI and modeled ET support screens; alternative thresholds admitted 0–48 months. Missing observations cannot be interpreted as ecological declines.</li>
</ul>

<h3>Locked 2022 evaluation: the selected model versus simple baselines</h3>
<div style="overflow-x:auto">
<table>
<thead><tr><th scope="col">Model</th><th scope="col">RMSE (m³/m³) ↓</th><th scope="col">MAE (m³/m³) ↓</th><th scope="col">R² ↑</th></tr></thead>
<tbody>
<tr><td><strong>XGBoost + radar and vegetation</strong></td><td><strong>0.0555</strong></td><td><strong>0.0444</strong></td><td><strong>0.544</strong></td></tr>
<tr><td>Calendar-month average baseline</td><td>0.0701</td><td>0.0555</td><td>0.272</td></tr>
<tr><td>Global training-mean baseline</td><td>0.0821</td><td>0.0667</td><td>≈0.000</td></tr>
</tbody>
</table>
</div>
<p><strong>Interpretation:</strong> An RMSE reduction means predictions agree more closely with the <em>SMAP product values that passed QA</em>. It is <strong>not</strong> an independent estimate of actual soil-moisture accuracy on the ground. A date-resampled 95% test-RMSE interval (about 0.0515–0.0592 m³/m³) likewise refers to reconstruction errors against SMAP, not calibrated field uncertainty.</p>

<h3>Maps, figures and quality diagnostics</h3>
<p>Every figure below is an output from the research notebooks. Click a figure to view the source image in the public research repository.</p>
<div class="research-evidence-grid">
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/cht_study_area.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/cht_study_area.png" alt="Local study-area map with the three Chittagong Hill Tracts district polygons" loading="lazy"></a>
<figcaption><strong>Study area — Bandarban, Khagrachhari and Rangamati.</strong> District features remain separate in the source; the map is a research geometry illustration, not an independently certified boundary.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/02C_annual_seasonal_coverage.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/02C_annual_seasonal_coverage.png" alt="Annual and seasonal SMAP quality-accepted observation availability diagnostic" loading="lazy"></a>
<figcaption><strong>SMAP availability by year and season.</strong> QA selection leaves a small and uneven training/evaluation sample. Missing records are not measured wet or dry conditions.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/08_temporal_test_smap_scatter.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/08_temporal_test_smap_scatter.png" alt="XGBoost reconstructed versus observed SMAP soil moisture in the held-out 2022 test" loading="lazy"></a>
<figcaption><strong>Held-out 2022 reconstruction.</strong> The model predicts quality-accepted satellite-product values. The horizontal/vertical comparison is <em>not</em> a field-soil-moisture validation plot.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/08_validation_model_comparison.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/08_validation_model_comparison.png" alt="Validation performance comparison of baseline, Random Forest, Ridge and XGBoost predictor groups" loading="lazy"></a>
<figcaption><strong>Why the selected model was chosen.</strong> Training, validation and final test years were kept separate; radar showed useful predictive value, while vegetation added a marginal extra gain.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/09_rainfall_and_monsoon_observation_support.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/09_rainfall_and_monsoon_observation_support.png" alt="Mean annual gridded rainfall alongside joint monsoon EVI and modeled ET observation-support fractions by CHT district" loading="lazy"></a>
<figcaption><strong>Rainfall and joint vegetation/ET support.</strong> CHIRPS v3 district rainfall averages are about 2,859–3,409 mm/year. Joint EVI/ET support remains especially limited during the monsoon; these are different products, not a causal analysis.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/09_wet_season_qa_sensitivity.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/09_wet_season_qa_sensitivity.png" alt="How threshold choices alter the number of monsoon district-months supported by quality-screened EVI and modeled ET" loading="lazy"></a>
<figcaption><strong>Quality-threshold sensitivity.</strong> Between 0 and 48 of the same 72 monsoon district-months pass different combined EVI/ET screens; the figure reflects evidence availability, <em>not</em> changing evapotranspiration or forest health.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/05_evi_qa_support_heatmap.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/05_evi_qa_support_heatmap.png" alt="Monthly strict-quality EVI forest observation-support heatmap" loading="lazy"></a>
<figcaption><strong>Forest greenness observations are quality limited.</strong> The heatmap describes accepted EVI observation support, not a direct measurement of vegetation loss.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/05_et_main_algorithm_support_heatmap.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/outputs/figures/05_et_main_algorithm_support_heatmap.png" alt="Monthly support for main MOD16 evapotranspiration algorithm over forest areas" loading="lazy"></a>
<figcaption><strong>Modeled ET needs algorithm-support screening.</strong> The MOD16 product is modeled, and its main-algorithm support varies; it is not a direct forest water-flux measurement.</figcaption>
</figure>
</div>

<h3>Data, methods and reproducible code</h3>
<ul>
<li><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling">Complete research repository</a> — study aims, verified findings, limitations, source datasets and citations.</li>
<li><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/tree/main/notebooks">Notebooks 00–09</a> — boundary audit, GEE inventory, ecohydrology quality review, corrected ML and integrated results.</li>
<li><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/blob/main/outputs/tables/08_temporal_test_metrics.csv">Final 2022 model metrics</a> and <a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/blob/main/outputs/tables/08_validation_leaderboard.csv">2021 model/feature leaderboard</a>.</li>
<li><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/blob/main/outputs/tables/07_training_data_manifest.json">SMAP sampling/QA manifest</a>, <a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/blob/main/outputs/tables/08_model_run_manifest.json">model run and split manifest</a> and <a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/blob/main/outputs/tables/09_reporting_manifest.json">integrated report manifest</a>.</li>
<li><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/blob/main/outputs/reports/09_integrated_research_summary.md">Notebook 09 integrated research summary</a>; <a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/blob/main/docs/METHODS_AND_REPRODUCIBILITY.md">Windows/Jupyter/GEE reproduction guide</a>.</li>
<li><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/tree/main/legacy">Original historical prototype</a> — retained to show the development of the study, not used as a directly comparable test result.</li>
</ul>

<h3>Limitations — what this study cannot claim</h3>
<ul>
<li><strong>No independent ground validation.</strong> Agreement with held-out SMAP data cannot establish true field-level surface soil-moisture accuracy, even when RMSE looks promising.</li>
<li><strong>Nonrandom observation gaps.</strong> The QA-accepted subset is small, uneven across districts and limited in seasons and grid postings; missing cells cannot be honestly assigned the same measured accuracy.</li>
<li><strong>Grid posting is not a sensor footprint.</strong> Adjacent SMAP postings need not represent independent soil-moisture measurements; fine-scale maps require a defensible scale treatment.</li>
<li><strong>Rainfall, EVI and ET are satellite/gridded or modeled products.</strong> Mountain rain-gauge biases, optical clouds and MOD16 algorithm support constrain forest ecohydrology interpretation.</li>
<li><strong>Correlations are not causes.</strong> Feature importance does not prove that forest canopy, terrain or rainfall physically caused the reconstructed pattern.</li>
</ul>

<h3>Research references</h3>
<p>Key product documentation: <a href="https://developers.google.com/earth-engine/datasets/catalog/NASA_SMAP_SPL3SMP_E_005">NASA SMAP enhanced v005</a>, <a href="https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S1_GRD">Sentinel-1 GRD</a>, <a href="https://developers.google.com/earth-engine/datasets/catalog/UCSB-CHC_CHIRPS_V3_DAILY_RNL">CHIRPS v3</a>, <a href="https://developers.google.com/earth-engine/datasets/catalog/MODIS_061_MOD13Q1">MOD13Q1 EVI</a> and <a href="https://developers.google.com/earth-engine/datasets/catalog/MODIS_061_MOD16A2GF">MOD16A2GF ET</a>. Related gap-filling methodology: <a href="https://doi.org/10.1016/j.jhydrol.2025.132762">“Global-scale gap filling of satellite soil moisture products: Methods and validation,” <em>Journal of Hydrology</em> 653 (2025), 132762</a>. These references inform the method; the performance values above come from this study's linked tables.</p>

<p class="research-links"><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling">Explore the complete CHT research, figures, results and notebooks →</a></p>
</section>

<section class="research-ongoing" markdown="0">
<h2>Future directions and field-validation boundary</h2>
<p>The <strong>satellite-only reconstruction experiment is complete</strong> through held-out product evaluation. The next steps require independently measured 0–5 cm soil moisture across forest types, elevations and slopes, coordinated with overpass times; spatially blocked/footprint-aware evaluation; rain-gauge comparisons; and measured vegetation/evapotranspiration references. Until then, this is a transparent <strong>satellite-product gap-filling and observation-feasibility study</strong>, not a field-validated forest soil-moisture map or an established forest water-balance mechanism.</p>
</section>
