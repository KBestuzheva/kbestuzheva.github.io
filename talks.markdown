---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Talks

{% for talk in site.data.talks %}
  <b>{{ talk[1].title }}</b>.
  {{ talk[1].conference }}
  ({{ talk[1].date }}, {{ talk[1].location }}).
  {%- if talk[1].slides -%}
    &nbsp;<a href="{{ site.url }}{{ site.baseurl }}/assets/slides/{{ talk[0] }}.pdf" target="_blank">[slides]</a>
  {%- endif -%}
  <br />
{% endfor %}
