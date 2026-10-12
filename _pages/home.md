---
title: "Home"
layout: homelay
permalink: /
---

<p class="hero-eyebrow">GEOSPATIAL SCIENCE &nbsp;/&nbsp; HYDROLOGY &nbsp;/&nbsp; EARTH OBSERVATION</p>
<h1 class="home-hero">{{ site.name }}<span class="geo-dot">.</span></h1>
<p class="home-hero-sub">Computational Geographer · GIS Analyst &amp; Graduate Researcher</p>

<div class="chip-container" markdown="0">
<a href="{{ '/research/' | relative_url }}" class="chip">Flood modelling</a>
<a href="{{ '/research/' | relative_url }}" class="chip">Remote sensing</a>
<a href="{{ '/research/' | relative_url }}" class="chip">Climate &amp; environmental risk</a>
<a href="{{ '/software/' | relative_url }}" class="chip">Python &amp; Earth Engine</a>
</div>

<div class="geospatial-lede">I turn satellite observations, field data and spatial models into useful evidence for environmental decisions.</div>

My work brings together **hydrodynamic modelling, GIS, remote sensing and environmental data science**. I develop reproducible workflows to investigate floods and drainage networks, wetland emissions, land-cover change and spatial public-health risks.

<div class="geo-hero-actions" markdown="0"><a class="geo-primary" href="{{ '/research/' | relative_url }}">Explore my research &rarr;</a><a class="geo-secondary" href="{{ '/contact/' | relative_url }}">Get in touch &rarr;</a></div>

<div class="banner-frame" markdown="0">
<img src="{{ '/images/geospatial-banner.svg' | relative_url }}" alt="Illustrated river delta, topographic contours and Earth observation grids" width="1400" height="430">
<div class="banner-caption">Geospatial thinking: from satellite pixels and terrain models to spatial insight.</div>
</div>

## Research directions

<div class="focus-grid" markdown="0">
<a class="focus-card" href="{{ '/research/' | relative_url }}"><span class="focus-index">01 / WATER</span><h3>Floods &amp; hydrodynamics</h3><p>Hydraulic connectivity, flood simulations, watershed rainfall and water-balance diagnostics.</p><span class="focus-arrow">Explore research &rarr;</span></a>
<a class="focus-card" href="{{ '/research/' | relative_url }}"><span class="focus-index">02 / EARTH OBSERVATION</span><h3>Climate &amp; land systems</h3><p>Satellite monitoring of wetlands, land cover, surface temperature and environmental change.</p><span class="focus-arrow">Explore research &rarr;</span></a>
<a class="focus-card" href="{{ '/software/' | relative_url }}"><span class="focus-index">03 / OPEN SCIENCE</span><h3>Geospatial methods</h3><p>Python, QGIS and Earth Engine tools designed for transparent, reproducible spatial analysis.</p><span class="focus-arrow">View code &rarr;</span></a>
</div>

## Current areas of work

- **Wetland greenhouse gases:** investigating methane dynamics in Bangladesh's Haor region.
- **Flood modelling:** terrain, drainage-network data and 1D/2D model integration.
- **Geospatial health:** environmental drivers of dengue risk in Chattogram.
- **Reproducible software:** open-source tools for satellite and hydrological analysis.

<div class="geo-inline-cta">Browse the <a href="{{ '/research/' | relative_url }}">research portfolio</a> or see <a href="{{ '/software/' | relative_url }}">open-source projects</a>.</div>

{% capture selected %}{% bibliography --query @*[selected=true] %}{% endcapture %}
{% if selected contains "pub-entry" %}
## Selected manuscripts
<div class="section-card selected-pubs" markdown="0">
{{ selected }}
<p style="margin: var(--space-4) 0 0;"><a href="{{ '/publications/' | relative_url }}">All publication details &rarr;</a></p>
</div>
{% endif %}
