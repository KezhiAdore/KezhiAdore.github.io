---
layout: default
title: Publications
permalink: /publications/
---

<section id="publications">
    <h3 class="section-title">Publications</h3>
    {% if site.data.publications %}
        {% for pub in site.data.publications %}
        <div class="publication-item">
            <div class="pub-image">
                {% if pub.image %}
                <img src="{{ pub.image | relative_url }}" alt="{{ pub.title }}" onerror="this.style.display='none'">
                {% endif %}
            </div>
            <div class="pub-details">
                <a href="{{ pub.links[0].url }}" class="pub-title">{{ pub.title }}</a>
                <div class="pub-authors">{{ pub.authors | markdownify | remove: '<p>' | remove: '</p>' }}</div>
                <div class="pub-venue">
                    {{ pub.venue }} 
                    {% if pub.highlight %}
                    <span class="pub-highlight">({{ pub.highlight }})</span>
                    {% endif %}
                </div>
                <div class="pub-links">
                    {% for link in pub.links %}
                    <a href="{{ link.url }}">{{ link.name }}</a>
                    {% endfor %}
                </div>
            </div>
        </div>
        {% endfor %}
    {% else %}
        <p>No publications found.</p>
    {% endif %}
</section>
