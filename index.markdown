---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# About me

A paragraph or two about my research interests.

# Recent publications

{% for article in site.data.publications limit:10 %}
  {%- for author in article[1].authors -%}
    {{ author.first_name }} {{ author.last_name }}
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
      ,&nbsp;{{ journal[1].pages }}
    {%- endif -%}
    {%- if journal[1].year -%}
      &nbsp;({{ journal[1].year }})
    {%- endif -%}
    .
    {%- if journal[1].doi -%}
      {% capture doilink %}
      https://doi.org/{{journal[1].doi}}
      {% endcapture %}
      &nbsp;<a style="white-space: nowrap" href="{{doilink}}">{{doilink}}</a>
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



# Contact

Email: bestuzheva@zib.de
