---
title: "Urban Forestry GeoAI: Street-Tree Siting for Heat Reduction in Mott Haven, New York City"
layout: page
permalink: /research/urban-forestry-geoai/
---

<p><a href="{{ '/research/' | relative_url }}">← Back to all research projects</a></p>

# Urban Forestry GeoAI | Which tree, where, to cool a street?

<section class="research-feature" id="urban-forestry-results" markdown="0">
<p class="research-feature-intro">Can open geospatial data recommend <strong>which tree species to plant at which street location</strong>, and say honestly what still has to be checked first? This remote pilot builds and tests that decision pipeline for the <strong>Third Avenue corridor of Mott Haven, South Bronx, New York City</strong>, a neighbourhood in the city's highest heat-vulnerability class. It joins aerial LiDAR, four satellite records, city tree inventories and a sourced species knowledge base with a pedestrian-heat model, a recorded-condition risk score and a multi-objective optimiser. <strong>The results were revised in November 2026 after an external audit</strong>; all figures below are from the corrected rerun. They are simulations and have not been validated in the field.</p>
<div class="research-stats">
<div><strong>98 / 23</strong><span>Planting spaces with consistent records / deferred because records conflict</span></div>
<div><strong>−4.8 °C</strong><span>Median modelled sidewalk radiant cooling beside a new tree with an 8 m crown</span></div>
<div><strong>2,167 m²</strong><span>Sidewalk cooled by more than 10 °C by 98 trees, each m² counted once</span></div>
<div><strong>0.65</strong><span>AUC of the condition-risk ranking within record-year cohorts (spatial CV)</span></div>
</div>

<h2>Research questions and data</h2>
<ul>
<li>Which recorded planting spaces are consistent enough to plan on, and how hot, shaded and paved is each one?</li>
<li>Which site and species conditions go with poor recorded condition of small street trees, and can that be used as a risk score?</li>
<li>How much does a new tree reduce afternoon pedestrian radiant heat (mean radiant temperature, Tmrt) on a heat-wave day, locally and corridor-wide?</li>
<li>Does an optimiser improve on simple planting rules once cooling is counted without overlap?</li>
</ul>
<p><strong>Geometry:</strong> USGS 3DEP LiDAR 2017 (1 m surface, terrain and canopy height), NYC building footprints, sidewalks, curbs and hydrants. <strong>Satellite:</strong> Landsat 8/9 surface temperature (77 summer scenes), NASA ECOSTRESS afternoon LST, Sentinel-2 (95 unique acquisitions, reflectance offset harmonised) and NAIP 2022/23 imagery. <strong>City records:</strong> NYC Parks Forestry tree points, planting spaces, inspections and work orders; the 2015 Street Tree Census; PLUTO land use; Heat Vulnerability Index; SSURGO soils. <strong>Weather:</strong> ERA5 hourly forcing for 24 June 2025, adjusted to observed maxima at Central Park (99 °F) and LaGuardia (101 °F). <strong>Species:</strong> NYC Parks approved list, USDA PLANTS, New York Flora Atlas, NIACS and USFS climate assessments, Xerces pollinator lists, published allergenicity and isoprene-emission surveys, and USFS/UF street-tree fact sheets (49 taxa, 2,687 sourced evidence rows; conflicts between sources are kept).</p>

<h2>1. Site evidence: a recorded planting space is not yet a plantable site</h2>
<p>All 6,017 NYC Forestry planting spaces within 1 km of the corridor were described by tree and maintenance history, street geometry, LiDAR shade, canopy and paving, satellite heat and greenness, land use and soil. In the 0.48 km² core (594 spaces), reconciling each space's status with its tree record leaves <strong>98 candidates</strong>, <strong>23 conflicting records</strong> (for example an "empty" space with a living tree on record) and 473 trees to retain. Conflicting sites are deferred, not planted.</p>
<p>No candidate has a recorded pit width or length; wire status is known at 9 sites; 83 have no ownership on record. London planetree already makes up <strong>19.9%</strong> of core street trees, above the 10% single-species guideline, so it is not planted again.</p>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Urban-Forestry-GEOAI/main/docs/images/site_layer_check.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/urban-forestry/site-layer.webp' | relative_url }}" alt="Planting spaces over ECOSTRESS afternoon surface temperature, and building-only sun hours from LiDAR shadow simulation" loading="lazy"></a>
<figcaption><strong>Site layer.</strong> Left: planting spaces over median afternoon surface temperature (ECOSTRESS). Right: building-only sun hours on 15 July from LiDAR shadow casting. Figure from the first build, before site records were reconciled. Surface temperature is not air temperature.</figcaption>
</figure>

<h2>2. A condition-risk score that ranks sites, but is not a survival model</h2>
<p>A LightGBM model was trained on the <strong>current recorded condition of 20,309 small-diameter Bronx street trees</strong> (16.6% recorded poor) and validated by spatial cross-validation over 132 one-kilometre blocks.</p>
<table>
<thead><tr><th>Model</th><th>AUC</th><th>AUC within record-year cohorts</th><th>Brier (raw)</th></tr></thead>
<tbody>
<tr><td>Record age only</td><td>0.715</td><td>0.536</td><td>0.108</td></tr>
<tr><td>+ species and species traits</td><td>0.736</td><td>0.553</td><td>0.116</td></tr>
<tr><td>+ site conditions</td><td><strong>0.779</strong></td><td><strong>0.648</strong></td><td>0.117</td></tr>
</tbody>
</table>
<p><strong>What holds:</strong> within the same record year, site features lift the ranking from 0.55 to 0.65 while species adds 0.02. Paved surroundings and curbside pits go with poorer recorded condition. <strong>What does not:</strong> the probabilities. Record age alone has a lower Brier score than the full model, and a nested isotonic calibration made it worse (0.129), so calibration learned in some neighbourhoods does not transfer. The sample is also biased: selecting trees by present trunk size (≤ 4 in) drops trees that grew, and the poor rate of 2015 records falls from 56% to 36% when the cut-off is widened to 8 in. The score is therefore used only to rank sites, never as a failure probability.</p>

<h2>3. Strong local cooling, modest corridor change</h2>
<p>Afternoon Tmrt (13:00–17:00) was simulated at 1 m with SOLWEIG for the hottest clear summer day of 2019–2025 (24 June 2025, air temperature ≈ 37.8 °C), with a ground-material map and weather and sun position on one clock. Trees were added at the 98 candidate sites with assumed crown sizes; no growth model is used.</p>
<ul>
<li><strong>Plausibility:</strong> sidewalk under existing canopy averages 45.3 °C against 62.3 °C in the open. This compares the model with itself; it is not validation.</li>
<li><strong>Locally:</strong> the sidewalk nearest a new tree cools by a median <strong>−2.6 °C with a 5 m crown</strong> and <strong>−4.8 °C with an 8 m crown</strong>.</li>
<li><strong>Corridor-wide:</strong> 8 m crowns cool <strong>2,167 m²</strong> of sidewalk by more than 10 °C, each square metre counted once. Mean core sidewalk Tmrt moves from <strong>58.7 to 57.9 °C</strong>; the share above 60 °C from 53.1% to 50.1%.</li>
<li><strong>Air and water:</strong> first-order per-canopy rates (Nowak et al., 2018) give about 15 kg O₃, 5 kg NO₂ and 0.8 kg PM₂.₅ removed and 45 m³ of avoided runoff per year for the 3,761 m² of simulated new canopy. These are removal estimates, not changes in the air people breathe.</li>
</ul>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Urban-Forestry-GEOAI/main/docs/images/benefits_map.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/urban-forestry/cooling-benefit.webp' | relative_url }}" alt="SOLWEIG afternoon mean radiant temperature now, and change after planting 98 trees with 8 m crowns" loading="lazy"></a>
<figcaption><strong>Pedestrian heat.</strong> Left: afternoon Tmrt on current surfaces. Right: change with 98 new trees with assumed 8 m crowns.</figcaption>
</figure>

<h2>4. The optimiser ties a simple rule on cooling; its value is the trade-off</h2>
<p>An NSGA-II optimiser chose one of 41 NYC-approved species and optional expanded rooting soil for each site, with four separate goals (cooling, a pollen-allergy plus isoprene index, an ecology index, condition risk) and NYC constraints: diversity limits of 10% species, 20% genus and 30% family including existing trees, no large trees under known wires, and narrow-sidewalk and location rules. Every plan in the table was then <strong>re-simulated as a whole</strong> with each tree at its own assumed crown size.</p>
<table>
<thead><tr><th>Plan (cap of 30 expanded-soil sites)</th><th>Cooled sidewalk, m² (simulated)</th><th>Allergy + isoprene index ↓</th><th>Ecology index ↑</th></tr></thead>
<tbody>
<tr><td>Optimiser: maximum cooling</td><td><strong>2,004</strong></td><td>348</td><td>76</td></tr>
<tr><td><strong>Optimiser: balanced</strong></td><td>1,739</td><td><strong>249</strong></td><td><strong>132</strong></td></tr>
<tr><td>Rule: biggest tree that fits</td><td><strong>2,004</strong></td><td>351</td><td>67</td></tr>
<tr><td>Rule: NYC's commonly planted mix</td><td>1,989</td><td>342</td><td>72</td></tr>
<tr><td>Random approved species</td><td>1,588</td><td>299</td><td>95</td></tr>
</tbody>
</table>
<p><strong>On cooling alone the optimiser adds nothing</strong>: its best plan ties the one-line rule. The balanced plan keeps <strong>87%</strong> of the maximum cooling with a <strong>29% lower</strong> allergy/isoprene index and about <strong>double</strong> the ecology index. These are constructed indices from published categories, not measured health or biodiversity outcomes.</p>
<div class="research-evidence-grid">
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Urban-Forestry-GEOAI/main/docs/images/plan_balanced_K30.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/urban-forestry/balanced-plan.webp' | relative_url }}" alt="Balanced planting plan: assumed crown class and expanded soil at each candidate site, with deferred sites shown separately" loading="lazy"></a>
<figcaption><strong>Balanced plan.</strong> 97 trees of 29 species; grey squares are the 24 deferred sites; red crosses mark large trees where wire status is unknown.</figcaption>
</figure>
<figure class="research-evidence">
<a href="https://raw.githubusercontent.com/Bipul-roy-AI/Urban-Forestry-GEOAI/main/docs/images/interface_site.png" target="_blank" rel="noopener noreferrer"><img src="{{ '/assets/images/research/urban-forestry/planner-interface.webp' | relative_url }}" alt="Planner interface showing a selected site with its recommendation and outstanding field checks" loading="lazy"></a>
<figcaption><strong>Planner interface.</strong> Each site shows its recommendation, the evidence behind it and the checks still required. Model outputs, not planting approvals.</figcaption>
</figure>
</div>

<h2>What the audit changed</h2>
<p>An external review found a one-hour mismatch between weather and sun position, cooling double-counted where tree buffers overlap (3,783 m² reported against 2,277 m² unique), unharmonised and duplicated Sentinel-2 products, conflicting site records treated as plantable, a missing ground-material map, and a "5-year failure probability" label the data cannot support. All were corrected and rerun. The headline trade-off fell from "95% of the cooling" to 87%, and the optimiser's apparent cooling advantage disappeared. The <a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI#what-changed-in-the-november-2026-revision">full list of fixes</a> is in the repository.</p>

<h2>Data and code</h2>
<ul>
<li><a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Data_Audit_Area_A.md">Data audit</a> and <a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Site_Features.md">site features</a></li>
<li><a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Species_KB.md">Species knowledge base</a> with an evidence table and source registry</li>
<li><a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Condition_Risk_Model.md">Condition-risk model</a>, <a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Benefits_Model.md">benefit modelling</a> and <a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/blob/main/docs/Optimiser.md">optimiser</a> write-ups</li>
<li><a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/tree/main/scripts">Reproducible Python scripts</a> and the <a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI/tree/main/interface">planner interface</a></li>
</ul>

<h2>What this does not show</h2>
<p>Nothing here is measured in the field. Tmrt is simulated pedestrian radiant heat on one day from an experimental port of SOLWEIG; it is not air temperature. Crown sizes are assumptions, and the gain from expanded soil follows from an assumed crown cap. The condition-risk score is cross-sectional and biased by how the sample is drawn; it is not survival. Pit dimensions, most wire and ownership records, and underground utilities are unknown, so no site is confirmed plantable. Geometry dates differ (LiDAR 2017, imagery 2022–23, records 2026). ECOSTRESS quality filtering is still incomplete.</p>
<p class="research-links"><a href="https://github.com/Bipul-roy-AI/Urban-Forestry-GEOAI">Explore the complete pipeline, maps, models and data →</a></p>
</section>

<section class="research-ongoing" markdown="0">
<h2>Ongoing research</h2>
<p>Next steps are a <strong>tree-level history</strong> from inspections and work orders for a real survival model; <strong>species growth curves</strong> from the USFS Urban Tree Database to replace assumed crowns; <strong>street-level imagery</strong> to resolve occupancy, wires and pit size at the 121 sites; a <strong>benchmark against the published SOLWEIG/TreePlanter test case</strong>; and a <strong>field campaign</strong> with radiation or globe-thermometer measurements and pit-soil sampling. A study of which missing observation would most change the plan is a candidate research contribution.</p>
</section>
