---
title: "ShasthoPath: Healthcare Accessibility and Flood-Disrupted Access in Bangladesh"
layout: page
permalink: /research/shasthopath-access/
---

<p><a href="{{ '/research/' | relative_url }}">← Back to all research projects</a></p>

# ShasthoPath | Who can reach care in Bangladesh, and who loses it in a flood?

<section class="research-feature" id="shasthopath-results" markdown="0">
<p class="research-feature-intro">How far do people in Bangladesh live from listed health care, how unevenly is that care spread, where do under-served areas cluster, and how much access do floods take away? This study links <strong>39,442 DGHS facility-registry records</strong> to the <strong>BBS Population and Housing Census 2022</strong> on a 1 km population grid, from division to union. It measures straight-line distance and modelled travel time, inequality and spatial clustering, and then stress-tests access against <strong>satellite flood maps for 2000–2025</strong>. It is published as an English–Bangla public site with facility search, routing and emergency helplines.</p>
<div class="research-stats">
<div><strong>7.2 min</strong><span>Median motorised travel time to any listed hospital</span></div>
<div><strong>49.6 min</strong><span>Median travel time to a blood bank; 58.6% within 60 min</span></div>
<div><strong>0.36–0.58</strong><span>Upazila Gini of government hospitals and beds per person</span></div>
<div><strong>8.4 M</strong><span>People losing a hospital within 60 min in the 2020 flood scenario</span></div>
</div>

<h2>Research questions and data</h2>
<ul>
<li>How many people live within a given distance and travel time of government hospitals, any hospital, upazila health complexes, primary care and blood banks?</li>
<li>How unequal is facility provision per person across districts and upazilas, and where do under-served areas cluster?</li>
<li>Which places flood most often, and how many people lose timely access to a hospital or primary care during observed floods?</li>
</ul>
<p><strong>Population:</strong> BBS Census 2022 community tables (8 divisions, 64 districts, 600 upazilas/thanas, 8,198 unions/wards), adjusted to the post-enumeration check (national 169.8 million), placed on 2015 geoBoundaries units through an explicit crosswalk and spread over 1 km UTM cells. <strong>Facilities:</strong> DGHS Facility Registry snapshot (39,442 institutions; 28,464 pass the national-boundary location check). <strong>Travel:</strong> Malaria Atlas Project 2019 motorised and walking friction surfaces (Weiss et al., 2020) with least-cost routing. <strong>Floods:</strong> Global Flood Database for 2000–2018 (Tellman et al., 2021) and Sentinel-1 VH change detection in Google Earth Engine for 2019–2025, following UN-SPIDER practice, with JRC permanent water removed. <strong>Tools:</strong> Python, Google Earth Engine, GIS.</p>

<h2>1. Distance and travel time: hospitals are near most people; blood banks are not</h2>
<table>
<thead><tr><th>Facilities</th><th>Travel</th><th>Median min</th><th>≤ 30 min</th><th>≤ 60 min</th><th>Mean straight-line km</th></tr></thead>
<tbody>
<tr><td>Any hospital</td><td>motorised</td><td><strong>7.2</strong></td><td>94.2%</td><td>98.9%</td><td>3.92</td></tr>
<tr><td>Government hospitals</td><td>motorised</td><td>12.5</td><td>89.0%</td><td>98.4%</td><td>6.51</td></tr>
<tr><td>Upazila health complexes</td><td>motorised</td><td>16.1</td><td>87.0%</td><td>98.4%</td><td>8.18</td></tr>
<tr><td>Blood banks</td><td>motorised</td><td><strong>49.6</strong></td><td>33.2%</td><td>58.6%</td><td>31.06</td></tr>
<tr><td>Primary care</td><td>walking</td><td>17.0</td><td>74.5%</td><td>92.9%</td><td>1.92</td></tr>
</tbody>
</table>
<p>The least-served upazilas within 60 minutes of any hospital are in the <strong>Chittagong Hill Tracts</strong> (Barkal, Belai Chhari, Baghai Chhari, Langadu and Jurai Chhari in Rangamati; Thanchi and Ruma in Bandarban) and the <strong>haor basin</strong> (Mithamain, Itna). People sit nearer to facilities than land does: the median person is 5.9 km from a government hospital, the median square kilometre 7.6 km.</p>
<div class="research-evidence-grid">
<figure class="research-evidence">
<a href="{{ '/images/projects/shasthopath/access-travel-map.png' | relative_url }}" target="_blank" rel="noopener noreferrer"><img src="{{ '/images/projects/shasthopath/access-travel-map.png' | relative_url }}" alt="Average motorised travel time to the nearest hospital by upazila" loading="lazy"></a>
<figcaption><strong>Travel time by upazila.</strong> Average motorised travel time to the nearest listed hospital; the Chittagong Hill Tracts and haor basin are among the slowest.</figcaption>
</figure>
<figure class="research-evidence">
<a href="{{ '/images/projects/shasthopath/access-travel-time.png' | relative_url }}" target="_blank" rel="noopener noreferrer"><img src="{{ '/images/projects/shasthopath/access-travel-time.png' | relative_url }}" alt="Share of people within each travel time of the nearest hospital, blood bank and primary care" loading="lazy"></a>
<figcaption><strong>Population within each travel time.</strong> Cumulative share of people by minutes to the nearest hospital, blood bank and primary care.</figcaption>
</figure>
</div>

<h2>2. Provision is unequal, and district averages hide most of it</h2>
<ul>
<li><strong>Inequality.</strong> The population-weighted Gini across upazilas is <strong>0.36</strong> for government hospitals per person, <strong>0.40</strong> for all hospitals, <strong>0.26</strong> for primary care and <strong>0.58</strong> for government beds. District Gini values are lower (0.18–0.30), so district summaries mask local gaps.</li>
<li><strong>Clustering.</strong> Global Moran's I is <strong>0.54</strong> for people within 5 km of a government hospital and <strong>0.69</strong> for primary care per person. Low–low LISA clusters for hospital access appear in the Chittagong Hill Tracts, the Sylhet–Netrokona haor belt and the north-west.</li>
<li><strong>Primary care norm.</strong> Nationally there are about <strong>9,004 union residents per listed community clinic</strong>, against a planning norm of about one per 6,000; 207 of 483 upazilas with unions exceed 9,000 per clinic.</li>
</ul>

<h2>3. Floods: a third of people live where it has flooded</h2>
<p>Across 26 yearly satellite flood maps (2000–2025), <strong>34.7%</strong> of people live in a 1 km cell flooded at least once, <strong>12.8%</strong> in five or more years and <strong>6.7%</strong> in ten or more. For eight named floods, normal monsoon water (pixels flooded in at least 4 of the other 6 Sentinel-1 years) is removed so that each event appears where it was reported: Feni and Cumilla in August 2024, Sherpur and Netrokona in October 2024, Sylhet division in 2022.</p>
<p>In the flood scenario, flooded facilities close, flooded cells slow travel to wading speed, and travel time is recomputed. A person loses access if they were within 60 minutes of a hospital before the flood but not during it.</p>
<table>
<thead><tr><th>Flood</th><th>Flooded beyond normal monsoon, km²</th><th>People in flooded cells</th><th>Hospitals flooded</th><th>Lose hospital ≤ 60 min</th></tr></thead>
<tbody>
<tr><td>Jul–Aug 2019</td><td>12,485</td><td>13.7 M</td><td>110</td><td>3.0 M</td></tr>
<tr><td>Jun–Aug 2020</td><td>26,010</td><td>28.4 M</td><td>197</td><td><strong>8.4 M</strong></td></tr>
<tr><td>Jun 2022</td><td>6,297</td><td>7.0 M</td><td>47</td><td>2.0 M</td></tr>
<tr><td>Jun 2024</td><td>5,097</td><td>4.7 M</td><td>42</td><td>1.3 M</td></tr>
<tr><td>Aug 2024</td><td>3,941</td><td>4.0 M</td><td>77</td><td>0.4 M</td></tr>
</tbody>
</table>
<p>In June–August 2020, <strong>1,511 km</strong> of main road and <strong>361 km</strong> of railway were under water; in August 2024, 336 km and 92 km.</p>
<div class="research-evidence-grid">
<figure class="research-evidence">
<a href="{{ '/images/projects/shasthopath/access-flood-inundation.png' | relative_url }}" target="_blank" rel="noopener noreferrer"><img src="{{ '/images/projects/shasthopath/access-flood-inundation.png' | relative_url }}" alt="How often each place flooded in 26 yearly satellite maps, 2000–2025" loading="lazy"></a>
<figcaption><strong>Flood frequency, 2000–2025.</strong> How often each place flooded in 26 yearly maps (Global Flood Database and Sentinel-1). The two eras use different sensors and are not directly comparable.</figcaption>
</figure>
<figure class="research-evidence">
<a href="{{ '/images/projects/shasthopath/access-flood-event.png' | relative_url }}" target="_blank" rel="noopener noreferrer"><img src="{{ '/images/projects/shasthopath/access-flood-event.png' | relative_url }}" alt="August 2024 eastern flash flood from Sentinel-1 radar with normal monsoon water shown separately" loading="lazy"></a>
<figcaption><strong>August 2024 eastern flash flood.</strong> Sentinel-1 flooding beyond normal monsoon water, shown separately from the water present every monsoon.</figcaption>
</figure>
<figure class="research-evidence">
<a href="{{ '/images/projects/shasthopath/access-flood-impact.png' | relative_url }}" target="_blank" rel="noopener noreferrer"><img src="{{ '/images/projects/shasthopath/access-flood-impact.png' | relative_url }}" alt="Share of people losing a hospital within 60 minutes by district in the June–August 2020 flood" loading="lazy"></a>
<figcaption><strong>Access lost in the 2020 flood.</strong> Share of people losing a hospital within 60 minutes, by district. A stress test of network fragility, not a count of people cut off.</figcaption>
</figure>
<figure class="research-evidence">
<a href="{{ '/images/projects/shasthopath/access-dark-mode.png' | relative_url }}" target="_blank" rel="noopener noreferrer"><img src="{{ '/images/projects/shasthopath/access-dark-mode.png' | relative_url }}" alt="The ShasthoPath Access study page in dark mode" loading="lazy"></a>
<figcaption><strong>Public site.</strong> The Access study is published bilingually (English–Bangla) alongside facility search, routing and emergency helplines.</figcaption>
</figure>
</div>

<h2>Data and code</h2>
<ul>
<li><a href="https://bipul-roy-ai.github.io/Health_care_accessibility/">ShasthoPath live site</a> (Access study, facility search, helplines)</li>
<li><a href="https://github.com/Bipul-roy-AI/Health_care_accessibility/blob/main/docs/ACCESS_STUDY.md">Access study methods, results and references</a></li>
<li><a href="https://github.com/Bipul-roy-AI/Health_care_accessibility/tree/main/scripts">Build scripts</a> (census matching, distance, travel time, flood overlays) and <a href="https://github.com/Bipul-roy-AI/Health_care_accessibility/tree/main/data">derived data</a></li>
</ul>

<h2>What this does not show</h2>
<p>A registry listing is not service availability, staffing or quality, and facilities with missing coordinates make the within-distance shares lower bounds. The friction surface describes 2019 roads (the 2022 Padma Bridge is missing) and ignores ferry waits, so island times are optimistic. People are assumed evenly spread within each union, and 15.9% of population is placed by area estimation. Flood losses are a stress test that ignores boats, embankments and raised roads; Sentinel-1 revisit gaps can miss short flash floods. Results describe areas, not individuals, and LISA p-values are not corrected for multiple testing.</p>
<p class="research-links"><a href="https://github.com/Bipul-roy-AI/Health_care_accessibility">Explore the complete study, data and code →</a></p>
</section>
