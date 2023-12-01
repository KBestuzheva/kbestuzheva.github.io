---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# About me

I am a postdoctoral researcher at Zuse Institute Berlin and the Interactive Optimization and Learning (IOL) Lab, leading the Global Optimization research area within IOL and coordinating the development of the open-source constraint integer programming solver SCIP.

I completed a Ph.D. in computer science at the Australian National University under the supervision of Dr. Hassan Hijazi, Prof. Sylvie Thiebaux and Prof. Markus Hegland. In my thesis titled "Global Optimization for Energy Systems" I developed convex relaxations and generalized convexity conditions for nonconvex nonlinear programming problems and mixed-integer nonlinear programming problems, in particular the optimal power flow problem and a mixed-integer extension of it known as the optimal transmission switching problem. Prior to this, I obtained a diploma in applied mathematics and informatics from the State Management University in Moscow.

I work on creating new techniques to efficiently solve mixed-integer nonlinear programs to global optimality and to improve the performance of branch-and-bound methods. I develop relaxations and cutting planes for convex and nonconvex MINLPs, in particular problems involving bilinear products, disjunctive structures and polynomials. Furthermore, I am interested in generalized convexity and its applications to global optimization. I implement these methods within SCIP, ensuring their computational usefulness in addition to the theoretical results.

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

{% comment %}
<a href="publications.html">See all publications</a>
{% endcomment %}

# Contact

Email: bestuzheva@zib.de
