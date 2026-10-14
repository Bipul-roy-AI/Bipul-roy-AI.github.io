---
title: "Research"
layout: page
permalink: /research/
---

# Research

I study environmental systems through GIS, hydrodynamic modelling, spatial analysis and Earth observation. The projects below include independent research and applied-methods development; they are not all peer-reviewed publications.

<div class="research-grid">
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

  <div class="research-card">
    <img src="{{ '/images/research/water.svg' | relative_url }}" class="research-thumb" alt="Illustration of rainfall, river and basin relief" width="400" height="200">
    <div class="research-body"><h2 class="research-title">Watershed water balance &amp; recharge</h2><p class="research-desc">Integrating precipitation, evapotranspiration, runoff and storage data for regional screening and comparison.</p><p><a href="https://github.com/Bipul-roy-AI/gee-water-balance-recharge-bangladesh">View recharge model →</a></p></div>
  </div>
</div>

<section class="research-feature" id="hakaluki-results">
  <h2>Research showcase: Hakaluki Haor</h2>
  <p class="research-feature-intro">Selected results from a <strong>2019–2025 satellite observation record</strong> and a separate <strong>2026 ESA Biomass experiment</strong>. The graphics below are generated research outputs, not illustrations or independently validated flood maps.</p>

  <div class="research-stats">
    <div><strong>84</strong><span>Monthly periods (2019–2025)</span></div>
    <div><strong>94</strong><span>SAR acquisitions examined (2022–2025, May–September)</span></div>
    <div><strong>6</strong><span>Paired spatial radar comparisons</span></div>
    <div><strong>69 / 84</strong><span>Months with a study-area XCH₄ value</span></div>
  </div>

  <div class="research-evidence-grid">
    <figure class="research-evidence">
      <a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13B_2022_may_expansion_spatial_change.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13B_2022_may_expansion_spatial_change.png" alt="Hakaluki Haor May 2022 matched-scene low-VV transition states and VV/VH change maps" loading="lazy"></a>
      <figcaption><strong>Radar change map · May 2022.</strong> Low-VV detections increased by approximately <strong>121.26 km²</strong> at −17 dB between 11 and 23 May, alongside broad VV/VH darkening. This is an observed screening change, <em>not confirmed inundation</em>.</figcaption>
    </figure>
    <figure class="research-evidence">
      <a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13C_four_year_scene_comparison.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis13/13C_four_year_scene_comparison.png" alt="Actual four-panel acquisition-level low-VV screening plot for 2022 to 2025" loading="lazy"></a>
      <figcaption><strong>Four-year radar chronology.</strong> Acquisition-level observations show that large scattering transitions occurred at different times. Monthly composites can conceal this timing; no exact flood-onset day was determined.</figcaption>
    </figure>
    <figure class="research-evidence">
      <a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis_2019_2025/methane11_availability_and_grid_support.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/analysis_2019_2025/methane11_availability_and_grid_support.png" alt="TROPOMI monthly methane observation availability and grid support over Hakaluki Haor" loading="lazy"></a>
      <figcaption><strong>Methane observation gap.</strong> XCH₄ was available in <strong>69 of 84 months</strong>, but only <strong>1 of 7 Augusts</strong>. This limits what can be inferred about wet-season methane, and XCH₄ is not an emission flux.</figcaption>
    </figure>
    <figure class="research-evidence">
      <a href="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/biomass_2026/biomass_20261002_reference_gamma0_four_polarizations.png" target="_blank" rel="noopener noreferrer"><img src="https://raw.githubusercontent.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research/main/docs/assets/figures/biomass_2026/biomass_20261002_reference_gamma0_four_polarizations.png" alt="Actual October 2026 ESA Biomass P-band HH HV VH and VV polarization maps for Hakaluki Haor" loading="lazy"></a>
      <figcaption><strong>ESA Biomass P-band · October 2026.</strong> Four radar polarizations were processed and compared descriptively with Sentinel-1 and Sentinel-2. No superiority in flood-classification accuracy has been demonstrated.</figcaption>
    </figure>
  </div>
  <p class="research-links"><a href="https://github.com/Bipul-roy-AI/Hakaluki-Haor-Wetland-Methane-Research">Explore the complete Hakaluki research, methods, maps and datasets →</a></p>
</section>

<section class="research-ongoing">
  <h2>Ongoing research</h2>
  <p>The Hakaluki study's exploratory satellite processing and results are published. The remaining scientific work is <strong>independent water/flooded-vegetation validation</strong> using reliable reference observations, <strong>upstream rainfall and historical river-stage analysis</strong> to test hydrological explanations, and <strong>native TROPOMI Level-2 quality, atmospheric transport and methane detectability assessment</strong>. Field methane-flux observations or a defensible atmospheric inversion would be needed before estimating local emissions. These steps remain open; no validated flood-area accuracy, flood-causation or methane emission-rate claim is made.</p>
</section>
