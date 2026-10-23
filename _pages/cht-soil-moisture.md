---
title: "CHT Soil Moisture Research"
layout: page
permalink: /research/cht-soil-moisture/
---

<p><a href="{{ '/research/' | relative_url }}">← Back to all research projects</a></p>

# Chittagong Hill Tracts | Soil moisture observability & gap-filling

<section class="research-feature" id="cht-soil-moisture-results" markdown="0">
<h2>Research showcase: can radar improve SMAP gap filling in hill forests?</h2>
<p class="research-feature-intro">This independent <strong>exploratory feasibility study</strong> examines surface-soil-moisture observations in a bounding-box proxy for Bangladesh's Chittagong Hill Tracts (CHT), 6 March–30 December 2021. It investigates missing regional SMAP values and a machine-learning reconstruction using Sentinel-1 C-band radar, vegetation, rainfall and terrain. The central scientific question is <strong>incremental SAR information beyond meteorological and seasonal predictors</strong>. The exploratory model has <em>not</em> passed independent validation, and the study has <em>not</em> established why SMAP observations are missing.</p>
<p><strong>Data:</strong> SMAP enhanced L3 passive soil moisture, Sentinel-1 SAR, MODIS vegetation indices, ERA5-Land precipitation, SRTM elevation and HydroSHEDS terrain. <strong>Methods:</strong> Google Earth Engine, Python, XGBoost and SHAP; a corrected chronological-validation workflow has been added for re-analysis.</p>
<div class="research-stats">
<div><strong>300</strong><span>Calendar days examined in 2021</span></div>
<div><strong>148</strong><span>Days with a recorded regional SMAP mean</span></div>
<div><strong>152</strong><span>Days missing in the committed series</span></div>
<div><strong>0.036</strong><span>Previously reported test R²; not independently revalidated</span></div>
</div>

<h3>Main findings: verified versus provisional</h3>
<ul>
<li><strong>Verified observation gap.</strong> The committed 300-day CSV has <strong>50.7% missing regional daily values</strong>. Monthly missing fractions remain close to one half (47–54%); the longest uninterrupted missing sequence is four days. These are counts in the exported <em>regional mean</em> series, not missing-pixel percentages or verified RFI losses.</li>
<li><strong>Exploratory prediction.</strong> An earlier XGBoost notebook reported RMSE <strong>0.0445 m³/m³</strong> and R² <strong>0.036</strong> against withheld SMAP values. However, the test labels were also used for early stopping; the result is <strong>not a clean independent test</strong> and cannot be compared to mission accuracy criteria or ground observations.</li>
<li><strong>Feature contributions remain a hypothesis.</strong> The older model emphasized day of year and antecedent precipitation, with around 15% combined native importance assigned to SAR features. Importance and SHAP are descriptive; they do not prove that canopy attenuation eliminates radar sensitivity. A climate/no-SAR/full-SAR ablation is prepared for new evaluation.</li>
<li><strong>Spatial claims are deliberately limited.</strong> The original labels were regional daily means used for repeated pixel samples, not ground-validated high-resolution soil moisture. The area was a geographic rectangle rather than a surveyed CHT/evergreen-forest boundary.</li>
</ul>

<h3>Figures and research evidence</h3>
<p>The first figure is regenerated from committed data. The two later model figures are retained to document the original experiment, <strong>not</strong> as independently validated performance or uncertainty.</p>
<div class="research-evidence-grid">
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/results/availability_verified.svg" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/results/availability_verified.svg" alt="Verified 2021 regional SMAP daily availability chart with recorded and missing dates and monthly missing fractions" loading="lazy"></a>
<figcaption><strong>Availability audit — verified.</strong> All 300 dates are represented, with 148 recorded and 152 missing regional means. Evenly distributed missingness does not identify its cause.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/results/model_performance_final.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/results/model_performance_final.png" alt="Historical XGBoost actual-versus-predicted soil moisture plot and model feature importance" loading="lazy"></a>
<figcaption><strong>Original model — exploratory.</strong> The reported fit and feature ranking are not independently revalidated. A distinct validation period is needed because model early stopping accessed the test labels.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/results/shap_analysis.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/main/results/shap_analysis.png" alt="Historical SHAP feature attribution for a Sentinel-1 and meteorological XGBoost soil moisture model" loading="lazy"></a>
<figcaption><strong>SHAP diagnostic — exploratory.</strong> A model-explanation graphic, not causal evidence of C-band attenuation or proof of the incremental value of Sentinel-1.</figcaption>
</figure>
</div>

<h3>Methodological contribution and related research</h3>
<p>The original inspiration was <a href="https://doi.org/10.1016/j.jhydrol.2025.132762" target="_blank" rel="noopener noreferrer">Zhang et al. (2025), <em>Journal of Hydrology</em></a>, which compared methods for filling SMAP gaps using reanalysis references. This experiment asks a narrower question in a data-scarce, mountainous tropical setting. Related reproducible approaches include <a href="https://doi.org/10.1029/2019WR024902" target="_blank" rel="noopener noreferrer">Mao et al. (2019), <em>Water Resources Research</em></a>, on two-layer SMAP/Sentinel-1 gap filling and <a href="https://doi.org/10.1002/eco.70024" target="_blank" rel="noopener noreferrer">Beale et al. (2025), <em>Ecohydrology</em></a>, on low-rank SMAP reconstruction. These methods are comparisons and potential extensions, not direct replications within this project.</p>
<p>The accompanying open-source research audit identifies problems in product-version selection, NDVI/EVI labeling, calculation of the radar polarization ratio in dB, pseudo-replicated targets, early-stopping leakage and overly broad interpretations of model accuracy. A reproducible availability audit, test cases, and a leakage-controlled evaluation script now separate what is demonstrated from what needs re-analysis.</p>

<h3>Data, methods and code</h3>
<ul>
<li><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/blob/main/data/smap_daily_means.csv">Source daily SMAP availability table</a> (300 dated regional means / missing values)</li>
<li><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/tree/main/scripts">Auditable analysis scripts</a> (availability, corrected figure and temporal validation)</li>
<li><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/blob/main/docs/RESEARCH_AUDIT.md">Scientific audit, literature and interpretation boundaries</a></li>
<li><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling/blob/main/docs/REPRODUCIBILITY.md">Reproducibility and next-experiment protocol</a></li>
<li><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling">Full GitHub repository</a> (legacy exploratory notebooks and plots retained for provenance)</li>
</ul>
<h3>What the current evidence cannot show</h3>
<p>No in-situ soil-moisture records are used, so field-scale retrieval accuracy is unknown. SMAP agreement does not establish independent accuracy. The exported predictor file is not committed, the notebook's historical Earth Engine collection selection needs correction for 2021, and a new model test must be run. The current missingness table does not isolate radio-frequency interference from orbital availability, quality screening, vegetation or other effects. No validated pixel-level gap-filled map, physical forest attenuation result or reliable predictive interval is claimed.</p>
<p class="research-links"><a href="https://github.com/Bipul-roy-AI/cht-soil-moisture-gapfilling">Explore the CHT methods, evidence audit and next-stage analysis →</a></p>
</section>

<section class="research-ongoing" markdown="0">
<h2>Ongoing research</h2>
<p>The next stage is to re-extract 2021 SMAP data using a verified product version and quality flags, use a checked CHT forest mask, regenerate independent daily predictors, and evaluate chronological holdouts against simple baselines. The analysis will compare models with and without Sentinel-1, stratify by observation and forest conditions, and seek independent in-situ or other defensible external validation. NASA released provisional NISAR L-band data in 2026; a later, separately dated analysis may compare its utility without implying that the 2021 C-band experiment has been solved.</p>
</section>
