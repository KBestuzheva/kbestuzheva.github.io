---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Publications

{% for article in site.data.publications %}
  {%- for author in article[1].authors -%}
    {{ author.first_name | slice: 0 }}. {{ author.last_name }}
    {%- if forloop.index == forloop.length -%}
      .
    {%- else -%}
      ,&nbsp;
    {%- endif -%}
  {% endfor %}
  <i>{{ article[1].title }}.&nbsp;</i>
  {%- for journal in article[1].journals -%}
    {{ journal[0] }}
    {%- if journal[1].volume -%}
      &nbsp;<b>{{ journal[1].volume }}</b>
    {%- endif -%}
    {%- if journal[1].issue -%}
      &nbsp;({{ journal[1].issue }})
    {%- endif -%}
    {%- if journal[1].pages -%}
      ,&nbsp;pp.&nbsp;{{ journal[1].pages }}
    {%- endif -%}
    {%- if journal[1].year -%}
      &nbsp;({{ journal[1].year }})
    {%- endif -%}
    .
    {%- if journal[1].doi -%}
      {% capture doilink %}
      https://doi.org/{{journal[1].doi}}
      {% endcapture %}
      <a style="white-space: nowrap" href="{{doilink}}">{{doilink}}</a>
    {%- endif -%}
    {%- if journal[1].note -%}
      &nbsp;{{ journal[1].note }}
    {%- endif -%}
  {%- endfor -%}
  {%- for proc in article[1].proceedings -%}
    {{ proc[0] }}
    {%- if proc[1].pages -%}
      ,&nbsp;pp.&nbsp;{{ proc[1].pages }}
    {%- endif -%}
    {%- if proc[1].year -%}
      &nbsp;({{ proc[1].year }})
    {%- endif -%}
    .
    {%- if proc[1].doi -%}
      {% capture doilink %}
      https://doi.org/{{proc[1].doi}}
      {% endcapture %}
      <a style="white-space: nowrap" href="{{doilink}}">{{doilink}}</a>
    {%- endif -%}
  {%- endfor -%}
  {%- for preprint in article[1].preprints -%}
    {%- if preprint[0] == "arxiv" -%}
      {% capture arxivlink %}
      https://arxiv.org/abs/{{preprint[1].id}}
      {% endcapture %}
      [<a href="{{doilink}}">arXiv</a>]
    {%- endif -%}
  {%- endfor -%}
  <br /><br />
{% endfor %}
