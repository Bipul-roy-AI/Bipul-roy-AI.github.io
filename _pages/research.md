---
title: "Research"
layout: page
permalink: /research/
---

# Research

I study environmental systems through GIS, hydrodynamic modelling, spatial analysis and Earth observation. The projects below include independent research and applied-methods development; they are not all peer-reviewed publications.

<div class="research-grid" markdown="0">
<div class="research-card">
<img src="{{ '/images/research/flood.svg' | relative_url }}" class="research-thumb" alt="Illustration of a river and floodplain mesh" width="400" height="200">
<div class="research-body">
<h2 class="research-title">Flood hydrodynamics &amp; hydraulic networks</h2>
<p class="research-desc">Coupled 1D/2D hydraulic modelling, mesh–pipe integration, culvert connectivity and model QA for flood-risk assessment.</p>
</div>
</div>
<div class="research-card">
<img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13B_2022_may_expansion_spatial_change.png" class="research-thumb research-thumb--map" alt="Actual Sentinel-1 paired VV/VH change map for Hakaluki Haor in May 2022" width="800" height="400" loading="lazy">
<div class="research-body">
<h2 class="research-title">Hakaluki Haor | Wetland dynamics &amp; methane observability</h2>
<p class="research-desc">Independent satellite research (2019–2025) combining Sentinel-1, Sentinel-2, rainfall, temperature and TROPOMI XCH₄, with an October 2026 ESA Biomass P-band pilot.</p>
<p class="research-desc"><strong>Selected result:</strong> Similar large low-backscatter radar transitions in May 2022 and June 2023; evidence of strong threshold sensitivity in June 2024. These are radar observations, not validated flood extents.</p>
<p class="research-links"><a href="#hakaluki-results">View maps &amp; results ↓</a> <a href="https://github.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research">Research data &amp; code ↗</a></p>
</div>
</div>
<div class="research-card">
<img src="{{ '/images/research/health.svg' | relative_url }}" class="research-thumb" alt="Illustration of urban ward risk map" width="400" height="200">
<div class="research-body"><h2 class="research-title">Dengue geospatial risk</h2><p class="research-desc">Chattogram-focused spatial epidemiology with environmental factors, ward-level data and multi-criteria risk assessment.</p></div>
</div>
<div class="research-card">
<img src="{{ '/images/research/coastal.svg' | relative_url }}" class="research-thumb" alt="Illustration of coastal delta and mangrove cover" width="400" height="200">
<div class="research-body"><h2 class="research-title">Coastal &amp; land-cover change</h2><p class="research-desc">Time-series remote sensing of changing shorelines, mangroves and biological cover in the Sundarbans.</p></div>
</div>
<div class="research-card">
<img src="{{ '/images/research/lulc.svg' | relative_url }}" class="research-thumb" alt="Illustration of classified land-cover pixels" width="400" height="200">
<div class="research-body"><h2 class="research-title">Land-cover classification &amp; uncertainty</h2><p class="research-desc">Sentinel/Landsat classification, cross-validation and uncertainty-aware Google Earth Engine workflows.</p><p><a href="https://github.com/Bipul-roy-AI/gee-lulc-research-engine">View research engine →</a></p></div>
</div>

</div>

<section class="research-feature" id="hakaluki-results" markdown="0">
<h2>Research showcase: Hakaluki Haor</h2>
<p class="research-feature-intro">Hakaluki Haor is a large wetland in northeastern Bangladesh that changes sharply between the dry season and the monsoon. This project uses satellite radar, optical imagery, rainfall, temperature and atmospheric methane data from <strong>2019 to 2025</strong> to ask what those changes show, and what the sensors cannot show. A separate <strong>October 2026 ESA Biomass P-band</strong> test is included as an experiment. The graphics below are generated research outputs, not illustrations or independently validated flood maps.</p>
<p><strong>Data:</strong> Sentinel-1 C-band SAR, Sentinel-2 optical imagery, CHIRPS rainfall, ERA5-Land temperature, Sentinel-5P TROPOMI methane (XCH₄), ESA Biomass P-band SAR. <strong>Tools:</strong> Google Earth Engine, Python, GIS.</p>
<div class="research-stats">
<div><strong>84</strong><span>Monthly periods (2019–2025)</span></div>
<div><strong>94</strong><span>SAR acquisitions examined (2022–2025, May–September)</span></div>
<div><strong>6</strong><span>Paired spatial radar comparisons</span></div>
<div><strong>69 / 84</strong><span>Months with a study-area XCH₄ value</span></div>
</div>
<h3>Main results</h3>
<p>"Low-VV area" means radar pixels below a backscatter threshold, which is not a measured flood area. XCH₄ is a column concentration in the atmosphere, not a surface emission rate.</p>
<ul>
<li><strong>Strong seasonal signal.</strong> Every one of the 84 months had radar coverage (214 acquisitions). A −17 dB screen finds much more low-backscatter area in many wet-season months.</li>
<li><strong>Rainfall helps, but does not explain it.</strong> Rainfall from the previous three months had a month-adjusted Spearman correlation of +0.524 with the radar signal (81 months). In leave-one-year-out tests, a rainfall and temperature model did not consistently beat a simple month-median baseline (MAE 13.65 vs 13.26 km²).</li>
<li><strong>Single images hide the timing.</strong> Low-VV area rose by about 121 km² between 11 and 23 May 2022 and again between 11 and 23 June 2023. June 2022 was not an unusually high June compared with 2024.</li>
<li><strong>Thresholds can flip the story.</strong> For 5–17 June 2024, the change in low-VV area runs from about −104 km² at −19 dB to roughly zero at −15 dB. One cutoff alone should not be read as water retreating or returning.</li>
<li><strong>Methane data are thin in the monsoon.</strong> TROPOMI had values in 42 of 42 months from November to April, but in only 3 of 7 Junes, 2 of 7 Julys and 1 of 7 Augusts. The weak correlations in the months that do have data cannot show how wet-season emissions behave.</li>
<li><strong>Independent optical checks are limited.</strong> Cloud cover and tile coverage left some key monsoon dates with no usable Sentinel-2 reference points, so no water-classification accuracy is reported.</li>
<li><strong>P-band test.</strong> A fully polarimetric ESA Biomass scene (2 October 2026) was processed and compared with Sentinel-1 and Sentinel-2. The images differ in date and geometry, so the comparison is descriptive only.</li>
</ul>
<h3>Maps and figures</h3>
<div class="research-evidence-grid">
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/hakaluki_boundary_audit_map.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/hakaluki_boundary_audit_map.png" alt="Study-area boundary used for the Hakaluki Haor analysis" loading="lazy"></a>
<figcaption><strong>Study area.</strong> The analysis covers a domain of about 172 km². Its boundary is an analysis window, not an official wetland outline.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis_2019_2025/inundation09_monthly_screening_timeseries.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis_2019_2025/inundation09_monthly_screening_timeseries.png" alt="Monthly low-VV radar screening area for Hakaluki Haor, 2019 to 2025" loading="lazy"></a>
<figcaption><strong>Monthly radar record, 2019–2025.</strong> Low-backscatter area follows a clear yearly cycle, with the largest values in the wet season.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13B_2022_may_expansion_spatial_change.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13B_2022_may_expansion_spatial_change.png" alt="Hakaluki Haor May 2022 matched-scene low-VV transition states and VV/VH change maps" loading="lazy"></a>
<figcaption><strong>Radar change map · May 2022.</strong> Low-VV detections increased by approximately <strong>121.26 km²</strong> at −17 dB between 11 and 23 May, alongside broad VV/VH darkening. This is an observed screening change, <em>not confirmed inundation</em>.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13B_2023_june_expansion_spatial_change.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13B_2023_june_expansion_spatial_change.png" alt="Paired Sentinel-1 VV and VH change map for 11 to 23 June 2023" loading="lazy"></a>
<figcaption><strong>Radar change map · June 2023.</strong> A similar jump of about 121 km² appears a year later, so these transitions repeat across seasons.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13B_2024_june_early_to_mid_spatial_change.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13B_2024_june_early_to_mid_spatial_change.png" alt="Paired Sentinel-1 change map for 5 to 17 June 2024 showing threshold sensitivity" loading="lazy"></a>
<figcaption><strong>Threshold sensitivity · June 2024.</strong> The same pair of scenes gives a large loss or almost no change depending on the VV cutoff.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13C_four_year_scene_comparison.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13C_four_year_scene_comparison.png" alt="Actual four-panel acquisition-level low-VV screening plot for 2022 to 2025" loading="lazy"></a>
<figcaption><strong>Four-year radar chronology.</strong> Large scattering transitions occurred at different times each year. Monthly composites can conceal this timing; no exact flood-onset day was determined.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis_2019_2025/hydro10_timeseries_rain_temperature_lowvv.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis_2019_2025/hydro10_timeseries_rain_temperature_lowvv.png" alt="Rainfall, temperature and radar screening time series for Hakaluki Haor" loading="lazy"></a>
<figcaption><strong>Rainfall, temperature and radar signal.</strong> Rainfall tracks the radar signal with a lag, but upstream river conditions are not in this dataset.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis_2019_2025/methane11_availability_and_grid_support.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis_2019_2025/methane11_availability_and_grid_support.png" alt="TROPOMI monthly methane observation availability and grid support over Hakaluki Haor" loading="lazy"></a>
<figcaption><strong>Methane observation gap.</strong> XCH₄ was available in <strong>69 of 84 months</strong>, but only <strong>1 of 7 Augusts</strong>. This limits what can be inferred about wet-season methane, and XCH₄ is not an emission flux.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/biomass_2026/biomass_20261002_reference_gamma0_four_polarizations.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/biomass_2026/biomass_20261002_reference_gamma0_four_polarizations.png" alt="Actual October 2026 ESA Biomass P-band HH HV VH and VV polarization maps for Hakaluki Haor" loading="lazy"></a>
<figcaption><strong>ESA Biomass P-band · October 2026.</strong> HH, HV, VH and VV maps at 25 m. Median contrast was about 8.16 dB for P-band HH–HV and 11.00 dB for C-band VV–VH. No superiority in flood-classification accuracy has been demonstrated.</figcaption>
</figure>
</div>
<h3>Data and code</h3>
<ul>
<li><a href="https://github.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/tree/main/docs/assets/tables/analysis_2019_2025">Monthly tables, 2019–2025</a> (radar screening, methane availability, per-acquisition records)</li>
<li><a href="https://github.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/tree/main/docs/assets/tables/analysis13">Paired-scene transition tables</a> (threshold sensitivity, optical reference checks, methane scenarios)</li>
<li><a href="https://github.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/tree/main/docs/assets/tables/biomass_2026">ESA Biomass 2026 tables</a></li>
<li><a href="https://github.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/tree/main/notebooks">Notebooks 09–13F</a> (Python and Google Earth Engine)</li>
<li><a href="https://github.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/blob/main/research_docs/FINDINGS_2019_2025_AND_LIMITATIONS.md">Full findings and limitations</a></li>
</ul>
<h3>What this does not show</h3>
<p>There are no independent water or non-water reference labels, so flooded area and accuracy are not reported. The study boundary needs independent verification. Methane values are concentrations, not emission rates, and the monsoon gaps leave the wet-season methane question open.</p>
<p class="research-links"><a href="https://github.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research">Explore the complete Hakaluki research, methods, maps and datasets →</a></p>
</section>

<section class="research-ongoing" markdown="0">
<h2>Ongoing research</h2>
<p>The Hakaluki study's exploratory satellite processing and results are published. The remaining scientific work is <strong>independent water/flooded-vegetation validation</strong> using reliable reference observations, <strong>upstream rainfall and historical river-stage analysis</strong> to test hydrological explanations, and <strong>native TROPOMI Level-2 quality, atmospheric transport and methane detectability assessment</strong>. Field methane-flux observations or a defensible atmospheric inversion would be needed before estimating local emissions. These steps remain open; no validated flood-area accuracy, flood-causation or methane emission-rate claim is made.</p>
</section>
