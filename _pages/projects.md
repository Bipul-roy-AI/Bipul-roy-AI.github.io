---
title: "Projects"
layout: page
permalink: /projects/
---

# Projects

{% for project in site.data.projects %}
<div class="section-card project-card" markdown="0">
<h2>{{ project.name }}</h2>
<p class="project-desc">{{ project.description }}</p>
{% if project.website or project.repo or project.docs or project.paper %}
<div class="pub-actions project-links">
{% if project.repo %}<a href="{{ project.repo }}" target="_blank" rel="noopener noreferrer" class="btn-pill btn-git">Code</a>{% endif %}
{% if project.website %}<a href="{{ project.website }}" target="_blank" rel="noopener noreferrer" class="btn-pill btn-website">Website</a>{% endif %}
{% if project.docs %}<a href="{{ project.docs }}" target="_blank" rel="noopener noreferrer" class="btn-pill btn-link">Docs</a>{% endif %}
{% if project.paper %}<a href="{{ project.paper }}" target="_blank" rel="noopener noreferrer" class="btn-pill btn-link">Paper</a>{% endif %}
</div>
{% endif %}
{% if project.screenshots and project.screenshots.size > 0 %}
<div class="project-demos{% if project.name == 'Automated Land Surface Temperature (LST) Mapping' %} lst-demo-pair{% endif %}">
{% for shot in project.screenshots %}
<figure class="project-demo">
<a href="{{ shot.src | relative_url }}" target="_blank" rel="noopener noreferrer"><img src="{{ shot.src | relative_url }}" alt="{{ project.name }}: {{ shot.caption | default: 'demo screenshot' | escape }}" loading="lazy" decoding="async"></a>
{% if shot.caption %}<figcaption>{{ shot.caption }}</figcaption>{% endif %}
</figure>
{% endfor %}
</div>
{% endif %}
</div>
{% endfor %}

{% unless site.data.projects.size > 0 %}
<p class="text-muted">No projects listed yet. Add entries to <code>_data/projects.yml</code>.</p>
{% endunless %}
