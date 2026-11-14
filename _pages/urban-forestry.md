---
title: "Urban Forestry GeoAI: Street-Tree Siting for Heat Reduction in Mott Haven, New York City"
layout: page
permalink: /research/urban-forestry-geoai/
---

<p><a href="{{ '/research/' | relative_url }}">← Back to all research projects</a></p>

# Urban Forestry GeoAI | Which tree, where, to cool a street?

<section class="research-feature" id="urban-forestry-results" markdown="0">
<p class="research-feature-intro">Can open geospatial data recommend <strong>which tree species to plant at which street location</strong> so that it cools the sidewalk, survives, and avoids health and ecological costs? This pilot builds and tests that decision pipeline for <strong>121 real planting spaces on the Third Avenue corridor of Mott Haven, South Bronx, New York City</strong>, a neighbourhood ranked in the city's highest heat-vulnerability class. It joins aerial LiDAR, four satellite records, city tree inventories and a sourced species knowledge base with a pedestrian-heat model, a tree-failure model and a multi-objective optimiser. Uncertainty and untested assumptions are reported beside each result.</p>
<div class="research-stats">
<div><strong>6,017</strong><span>Planting spaces characterised (~70 features each)</span></div>
<div><strong>20,309</strong><span>Young Bronx trees used to model 5-year failure</span></div>
<div><strong>−4.8 °C</strong><span>Median local sidewalk radiant cooling per new tree at 20 years</span></div>
<div><strong>2,687</strong><span>Sourced trait values for 49 species</span></div>
</div>

<h2>Research questions and data</h2>
<ul>
<li>Where along the corridor can a tree physically be planted, and how hot, shaded, paved and vulnerable is each site?</li>
<li>Which site and species conditions predict that a young street tree fails within five years?</li>
<li>How much does a new tree reduce afternoon pedestrian radiant heat (mean radiant temperature, Tmrt) on a heat-wave day, locally and corridor-wide?</li>
<li>Can an optimiser choose species and rooting-soil treatment that keep the cooling while lowering allergy, ozone and ecological costs, within NYC planting rules?</li>
</ul>
<p><strong>Geometry:</strong> USGS 3DEP LiDAR 2017 (1 m surface, terrain and canopy height), NYC building footprints, sidewalks, curbs and hydrants. <strong>Satellite:</strong> Landsat 8/9 surface temperature (77 summer scenes), NASA ECOSTRESS afternoon LST (487 granules, 53 clear afternoon scenes), Sentinel-2 (105 scenes) and NAIP 2022/23 imagery, 2019–2026. <strong>City records:</strong> NYC Parks Forestry tree points, planting spaces, inspections and work orders; the 2015 Street Tree Census; PLUTO land use; Heat Vulnerability Index; SSURGO soils. <strong>Weather:</strong> ERA5 hourly forcing for 24 June 2025, adjusted to observed maxima at Central Park (99 °F) and LaGuardia (101 °F). <strong>Species:</strong> NYC Parks approved list, USDA PLANTS, New York Flora Atlas, NIACS and USFS climate assessments, Xerces pollinator lists, published allergenicity and isoprene-emission surveys, and USFS/UF street-tree fact sheets.</p>

<h2>1. The site layer: where trees can go and how hot it is</h2>
<p>Every NYC Forestry planting space within 1 km of the corridor (<strong>6,017</strong>; 594 in the 0.48 km² core) was described by its tree and maintenance history, street geometry, LiDAR shade, canopy and paving, satellite heat and greenness, land use, soil and heat vulnerability. The core holds <strong>121 candidate spaces</strong>: 88 empty, 29 removed trees or stumps and 4 dead trees. Hourly shadow casting on the 1 m surface for 15 July shows that buildings shade only <strong>5–6%</strong> of the ground at 13:00–15:00.</p>
<p>Afternoon surface temperature rises with paved fraction (<strong>r = +0.39</strong>) and falls with canopy within 30 m (<strong>r = −0.28</strong>); Landsat and ECOSTRESS agree (<strong>r = 0.74</strong>). London planetree already makes up <strong>19.9%</strong> of core street trees, breaking the 10% single-species guideline, so it is not planted again.</p>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Urban-Forestry-GEOAI/main/docs/images/site_layer_check.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/urban-forestry/site-layer.webp' | relative_url }}" alt="Planting spaces over ECOSTRESS afternoon surface temperature, and building-only sun hours from LiDAR shadow simulation" loading="lazy"></a>
<figcaption><strong>Site layer.</strong> Left: planting spaces over median afternoon surface temperature (ECOSTRESS, 12–16 h). Right: building-only sun hours on 15 July from LiDAR shadow casting, with candidate sites. Surface temperature is not air temperature.</figcaption>
</figure>

<h2>2. Site conditions predict young-tree failure better than species</h2>
<p>A LightGBM model was trained on <strong>20,309 young Bronx street trees</strong> (trunk ≤ 4 in; 16.6% recorded as failed) and validated by spatial cross-validation over <strong>132 one-kilometre blocks</strong>. Failure depends strongly on how long a record has existed (64% of 2015 records versus 2% of 2025 records), so models are also compared <strong>within record-year cohorts</strong>.</p>
<table>
<thead><tr><th>Model</th><th>AUC</th><th>AUC at equal exposure</th></tr></thead>
<tbody>
<tr><td>Record age only</td><td>0.715</td><td>0.536</td></tr>
<tr><td>+ species and species traits</td><td>0.736</td><td>0.553</td></tr>
<tr><td>+ site conditions</td><td><strong>0.779</strong></td><td><strong>0.652</strong></td></tr>
</tbody>
</table>
<p>At equal exposure, site features add <strong>+0.10 AUC</strong> and species adds <strong>+0.02</strong>. Paved surroundings, curbside pits and the highest heat-vulnerability ZIP codes raise risk; large lots and greener surroundings lower it. Isotonic calibration matches predicted to observed failure (e.g. 28.5% predicted, 28.5% observed). <strong>Meaning:</strong> the model is most useful for flagging sites that need better pits, watering or stewardship; its species ranking does not significantly agree with independent 2015 census health (Spearman ρ = 0.22, p = 0.20).</p>

<h2>3. Strong local cooling, modest corridor change</h2>
<p>Afternoon Tmrt was simulated at 1 m with SOLWEIG (UMEP) for the hottest clear summer day of 2019–2025 (24 June 2025, air temperature ≈ 37.8 °C), for current canopy and for one tree at every candidate site at 10 and 20 years. On today's sidewalks, Tmrt under existing canopy averages <strong>45.1 °C</strong> versus <strong>60.1 °C</strong> in the open.</p>
<ul>
<li><strong>Locally:</strong> sidewalk within 15 m of a new tree cools by a median <strong>−2.5 °C at 10 years</strong> and <strong>−4.8 °C at 20 years</strong>; the best commercial frontages on Third Avenue, E 137th Street and Lincoln Avenue reach about <strong>−13 °C</strong> over 100–140 m².</li>
<li><strong>Corridor-wide:</strong> mean sidewalk Tmrt falls only from <strong>57.0 to 56.1 °C</strong>, and the share above 60 °C from <strong>49.0% to 45.5%</strong>.</li>
<li><strong>Air and water:</strong> first-order per-canopy rates from the NYC i-Tree Eco assessment give about 199 g O₃, 65 g NO₂, 10 g PM₂.₅ removed and 580 L of avoided runoff per 20-year tree per year. These are removal estimates, not changes in street-level concentration.</li>
</ul>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Urban-Forestry-GEOAI/main/docs/images/benefits_map.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/urban-forestry/cooling-benefit.webp' | relative_url }}" alt="SOLWEIG afternoon mean radiant temperature now, and change after planting 121 trees at 20 years" loading="lazy"></a>
<figcaption><strong>Pedestrian heat.</strong> Left: afternoon Tmrt (13–16 h, 24 June 2025) on current surfaces. Right: change with 121 new trees at 20 years. Tree crowns are a generic assumption pending species growth curves.</figcaption>
</figure>

<h2>4. Optimised plans keep the cooling and cut health and ecological costs</h2>
<p>An NSGA-II optimiser chose one of 41 NYC-approved species and whether to install expanded rooting soil for each site, maximising risk-adjusted cooling and ecology (native to NY, pollinator value, climate suitability 2070–2099) while minimising pollen allergy and isoprene (ozone-precursor) emission. Plans had to respect the 10-20-30 diversity rule including existing trees, no large trees under known overhead wires, narrow-sidewalk and NYC location rules. The search was seeded with rule-based plans so it could only match or beat them.</p>
<table>
<thead><tr><th>Plan (30 expanded-soil sites)</th><th>Cooled sidewalk, m²</th><th>Allergy + isoprene ↓</th><th>Ecology ↑</th></tr></thead>
<tbody>
<tr><td>Optimiser: maximum cooling</td><td><strong>3,012</strong></td><td>330</td><td>134</td></tr>
<tr><td><strong>Optimiser: balanced</strong></td><td>2,801</td><td><strong>305</strong></td><td><strong>176</strong></td></tr>
<tr><td>Rule: biggest tree that fits</td><td>2,943</td><td>429</td><td>90</td></tr>
<tr><td>Rule: NYC's commonly planted mix</td><td>2,955</td><td>426</td><td>87</td></tr>
</tbody>
</table>
<p>The balanced plan keeps about <strong>95%</strong> of the best rule's cooling with about <strong>29% less</strong> allergy and ozone risk and <strong>twice</strong> the ecological score. Expanded soil has diminishing returns: the first 30 installations add 14% cooling to the maximum-cooling plan; the next 30 add 7%. On cooling alone, the simple rule comes within 2–3%; the optimiser's value is the trade-off.</p>
<div class="research-evidence-grid">
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Urban-Forestry-GEOAI/main/docs/images/plan_balanced_K30.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/urban-forestry/balanced-plan.webp' | relative_url }}" alt="Balanced planting plan: tree size class and expanded soil at each candidate site over current afternoon Tmrt" loading="lazy"></a>
<figcaption><strong>Balanced plan.</strong> Large trees with expanded soil on hot open frontages; small trees in already-shaded courtyards. Red crosses mark sites that need an on-site wire or wet-site check.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Urban-Forestry-GEOAI/main/docs/images/interface_site.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/urban-forestry/planner-interface.webp' | relative_url }}" alt="Planner interface showing a selected site with species, cooling, failure risk and field checks" loading="lazy"></a>
<figcaption><strong>Planner interface.</strong> Plan switcher, soil budget, site details, plan comparison and question answering over the plan data. Model outputs, not planting approvals.</figcaption>
</figure>
</div>

<h2>Data and code</h2>
<ul>
<li><a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Pilot_Plan_v2.md">Feasibility and pilot design</a> and <a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Data_Audit_Area_A.md">data audit</a></li>
<li><a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Species_KB.md">Species knowledge base</a> with an evidence table and source registry for every value</li>
<li><a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Survival_Model.md">Survival model</a>, <a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Benefits_Model.md">benefit modelling</a> and <a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Optimiser.md">optimiser</a> write-ups</li>
<li><a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/tree/main/scripts">23 reproducible Python scripts</a> and the <a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/tree/main/interface">planner interface</a></li>
</ul>

<h2>What this does not show</h2>
<p>Tmrt is pedestrian radiant heat on one hot day, not air temperature, and comes from an experimental standalone port of SOLWEIG. Tree crown sizes at 10 and 20 years are generic assumptions, and a large species without expanded soil is assumed capped at a medium crown. The failure label is a cross-sectional proxy from city inventory records, not measured survival. Overhead wires are recorded at only 11 of 121 sites, and pit soil and underground utilities are not public. Dense crowns in narrow streets can trap pollution, and oaks are high isoprene emitters. Nothing has yet been validated in the field.</p>
<p class="research-links"><a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI">Explore the complete pipeline, maps, models and data →</a></p>
</section>

<section class="research-ongoing" markdown="0">
<h2>Ongoing research</h2>
<p>Next steps are <strong>species-specific growth curves</strong> from the USFS Urban Tree Database to replace the generic crowns; <strong>street-level imagery</strong> to fill missing overhead-wire and pit-size records; <strong>true 10-year survival</strong> from the Trees Count 2025 census once released; and a <strong>summer field campaign</strong> with globe thermometers, air-temperature loggers and pit-soil sampling to validate the modelled cooling. A peri-urban contrast site (Staten Island) and a European transfer test (Berlin) are planned to check whether the method generalises.</p>
</section>
