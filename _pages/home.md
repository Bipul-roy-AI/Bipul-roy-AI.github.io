---
title: "Home"
layout: homelay
permalink: /
---

<h1 class="home-hero">{{ site.name }}</h1>
<p class="home-hero-sub">{{ site.title }}, {{ site.institution }}</p>

<div class="chip-container" markdown="0">
<a href="{{ '/research/' | relative_url }}" class="chip">Hydrodynamic Modelling</a>
<a href="{{ '/research/' | relative_url }}" class="chip">Remote Sensing</a>
<a href="{{ '/research/' | relative_url }}" class="chip">Geospatial Risk Analysis</a>
<a href="{{ '/research/' | relative_url }}" class="chip">Environmental Modelling</a>
<a href="{{ '/software/' | relative_url }}" class="chip">GIS &amp; Automation</a>
</div>

I am a computational geographer working at the intersection of hydrology, remote sensing, and environmental data science. I use geospatial modelling and statistical analysis to study floods, wetlands, land-cover change, and environmental health risks. My work combines satellite observations, GIS, field data, and reproducible computational workflows to support research and applied decision-making.

<div class="callout callout-success" markdown="0">
<div class="callout-title">Current research &amp; professional work</div>
<p>I work on coupled 1D/2D flood modelling and geospatial infrastructure analysis, and contribute to research on wetland and agricultural greenhouse-gas dynamics. My work includes projects in Bangladesh and remote collaboration with an environmental modelling team in Germany.</p>
</div>

<div class="banner-frame" markdown="0">
<img src="{{ '/images/geospatial-banner.svg' | relative_url }}" alt="Abstract map of river channels, terrain contours, and geospatial coordinates" width="1400" height="430" style="width:100%; height:145px; object-fit:cover; object-position:center;" loading="lazy">
<div class="banner-caption">Hydrology, Earth observation, and geospatial modelling.</div>
</div>

{% capture selected %}{% bibliography --query @*[selected=true] %}{% endcapture %}
{% if selected contains "pub-entry" %}
## Selected manuscripts

<div class="section-card selected-pubs" markdown="0">
{{ selected }}
<p style="margin: var(--space-4) 0 0;"><a href="{{ '/publications/' | relative_url }}">All publications &rarr;</a></p>
</div>
{% endif %}

## About me

I am a GIS Analyst working with hydrodynamic models and spatial infrastructure data, and a Research Assistant at the Space and Environment Research Centre (SERC), Bangladesh. I am pursuing an M.S. in GIS for Environment and Development at Jahangirnagar University.

My interests include river and urban flood processes, satellite-based land and water monitoring, environmental change, spatial epidemiology, and open-source geospatial software.

Read more [about my work]({{ '/about/' | relative_url }}) or explore my [research]({{ '/research/' | relative_url }}) and [software projects]({{ '/software/' | relative_url }}).
