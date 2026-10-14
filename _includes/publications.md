<h2 id="publications">Publications</h2>

<div class="publications">
  <ol class="bibliography">
    {% for paper in site.data.publications.main %}
    <li class="publication-item">
      <article class="publication-entry{% unless paper.image %} publication-entry--text-only{% endunless %}">
        {% if paper.image %}
        <figure class="publication-visual">
          <img src="{{ paper.image | relative_url }}" alt="{{ paper.image_alt | default: paper.title | escape }}" loading="lazy" decoding="async" />
          {% if paper.conference_short %}
          <span class="publication-venue">{{ paper.conference_short }}</span>
          {% endif %}
          {% if paper.figure_caption %}<figcaption>{{ paper.figure_caption }}</figcaption>{% endif %}
        </figure>
        {% endif %}
        <div class="publication-details">
          <h3 class="publication-title"><a href="{{ paper.pdf }}" target="_blank" rel="noopener noreferrer">{{ paper.title }}</a></h3>
          <p class="publication-authors">{{ paper.authors }}</p>
          <p class="publication-journal">{{ paper.conference }}</p>
          <div class="publication-actions">
            {% if paper.pdf %}<a href="{{ paper.pdf }}" target="_blank" rel="noopener noreferrer">PDF</a>{% endif %}
            {% if paper.code %}<a href="{{ paper.code }}" target="_blank" rel="noopener noreferrer">Code</a>{% endif %}
            {% if paper.doi %}<a href="{{ paper.doi }}" target="_blank" rel="noopener noreferrer">DOI</a>{% endif %}
            {% if paper.page %}<a href="{{ paper.page }}" target="_blank" rel="noopener noreferrer">Project page</a>{% endif %}
            {% if paper.bibtex %}<a href="{{ paper.bibtex }}" target="_blank" rel="noopener noreferrer">BibTeX</a>{% endif %}
            {% if paper.notes %}<span class="publication-status">{{ paper.notes }}</span>{% endif %}
          </div>
        </div>
      </article>
    </li>
    {% endfor %}
  </ol>
</div>
