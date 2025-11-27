---
title: Index A-Z
nav_order: 5
---

{: .note }
Kijk gerust rond! Aan deze website wordt momenteel nog gewerkt.

# Alfabetisch overzicht

{% assign entries_string = "" %}

{% comment %} --- STAP 1: Bouwen --- {% endcomment %}
{% for p in site.documents %}
  {% assign url = p.url | relative_url %}
  
  {% comment %} Maak de standaard Markdown link vast 1x aan: [Titel](/url) {% endcomment %}
  {% assign md_link = "[" | append: p.title | append: "](" | append: url | append: ")" %}

  {% comment %} 1. Hoofd-item {% endcomment %}
  {% assign entry = p.title | append: "::" | append: md_link %}
  {% assign entries_string = entries_string | append: entry | append: "|||" %}

  {% comment %} 2. Alt-items {% endcomment %}
  {% if p.alt_labels %}
    {% for alt in p.alt_labels %}
      {% assign alt_span = '<span class="text-grey-dk-100">' | append: alt | append: '</span>' %}
      {% assign display_string = alt_span | append: " &rarr; " | append: md_link %}
      {% assign entry = alt | append: "::" | append: display_string %}
      {% assign entries_string = entries_string | append: entry | append: "|||" %}
    {% endfor %}
  {% endif %}
{% endfor %}

{% comment %} --- STAP 2: Sorteren --- {% endcomment %}
{% assign sorted_entries = entries_string | split: "|||" | sort_natural %}
{% assign current_letter = "" %}

{% comment %} --- STAP 3: Output --- {% endcomment %}
{% for item in sorted_entries %}
  {% if item == "" %}{% continue %}{% endif %}

  {% assign parts = item | split: "::" %}
  {% assign sort_name = parts[0] %}
  {% assign display_string = parts[1] %}

  {% assign char = sort_name | slice: 0, 1 | slugify | upcase %}

  {% if char != current_letter %}
    {% assign current_letter = char %}
## {{ char }}

  {% endif %}
{{ display_string }}
{: .lh-tight}

{% endfor %}
