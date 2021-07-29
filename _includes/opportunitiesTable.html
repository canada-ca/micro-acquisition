{%- assign aPost = site.posts | where:"lang", page.lang | sort:"closing_date" -%}
<link rel='stylesheet' href='../assets/css/gridify.css' />

<div>
  <details open>
    <summary>
      <h2>{{ site.data.i18n.general.opportunities.open[page.lang] }}</h2>
    </summary>
    <section>
      <div class="row wb-eqht">
        {% assign openPostCount = 0 %}
        {%- for post in aPost -%}
        {%- capture nowXML -%}{{ 'now' | date_to_xmlschema }}{%- endcapture -%}
        {%- capture closeXML -%}{{ post.closing_date | date_to_xmlschema }}{%- endcapture -%}
        {%- if closeXML > nowXML -%}
        {% assign openPostCount = openPostCount | plus: 1 %}
        <div class="col-xs-12 col-md-6">
          <div class="panel panel-default position-relative">
            <div class="panel-heading">
              <p><a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></p>
            </div>
            <div class="panel-body">
              <p>
                <span class="label label-success">{{ site.data.i18n.general.opportunities.open[page.lang] }}</span>
                {% if post.update | find:"closing_date" != nil %}
                <span class="label label-info">{{ site.data.i18n.general.opportunities.updated[page.lang] }}</span>
                {% endif %}
              </p>
              <p>
                {%- assign closeDate = post.closing_date | date: "%e %B %Y %H:%M" -%}
                {%- if page.lang == "fr" -%}
                {% include replaceFrenchMonth.md %}
                {%- endif -%}
                <span class="glyphicon glyphicon-calendar"></span>&nbsp;<strong>{{
                  site.data.i18n.general.opportunities.closing[page.lang] }}:</strong>&nbsp;{{ closeDate }}, {{
                site.data.i18n.general.opportunities.easternTime[page.lang] }}
              </p>
              <p><strong>{{ site.data.i18n.general.opportunities.value[page.lang] }}:</strong>&nbsp;{{ post.value }}
              </p>
              <p>{{ post.short_desc }}</p>
              <p>{{ site.data.i18n.general.opportunities.skills[page.lang] }}:&nbsp;
                {%- assign skills = post.skills | split: ", " -%}
                {%- for skill in skills -%}
                <span class="label label-primary">{{ skill }}</span>&nbsp;
                {%- endfor -%}
              </p>
            </div>
          </div>
        </div>
        {%- endif -%}
        {%- endfor -%}
      </div>
      {% if openPostCount == 0 %}
      <p class="brdr-bttm">{{ site.data.i18n.general.opportunities.noOpen[page.lang] }}</p>
      {% endif %}
    </section>
  </details>
  <details>
    <summary>
      <h2>{{ site.data.i18n.general.opportunities.closed[page.lang] }}</h2>
    </summary>
    <section>
      <div class="row wb-eqht">
        {%- for post in aPost -%}
        {%- capture nowXML -%}{{ 'now' | date_to_xmlschema }}{%- endcapture -%}
        {%- capture closeXML -%}{{ post.closing_date | date_to_xmlschema }}{%- endcapture -%}
        {%- if closeXML < nowXML -%} <div class="col-xs-12 col-md-6">
          <div class="panel panel-default position-relative">
            <div class="panel-heading">
              <p><a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></p>
            </div>
            <div class="panel-body">
              <p>
                {%- assign closeDate = post.closing_date | date: "%e %B %Y %H:%M" -%}
                {%- if page.lang == "fr" -%}
                {% include replaceFrenchMonth.md %}
                {%- endif -%}
                <span class="label label-danger">{{ site.data.i18n.general.opportunities.closed[page.lang] }}</span>
                {{ site.data.i18n.general.opportunities.closed[page.lang] }}:&nbsp;{{ closeDate }}
              </p>
              <p>{{ post.value }}</p>
              <p>{{ post.short_desc }}</p>
              <p>{{ site.data.i18n.general.opportunities.skills[page.lang] }}:&nbsp;
                {%- assign skills = post.skills | split: ", " -%}
                {%- for skill in skills -%}
                <span class="label label-primary">{{ skill }}</span>&nbsp;
                {%- endfor -%}
              </p>
            </div>
          </div>
      </div>
      {%- endif -%}
      {%- endfor -%}
    </section>
  </details>
</div>