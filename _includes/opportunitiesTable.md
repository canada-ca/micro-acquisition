{%- assign aPost = site.posts | where:"lang", page.lang | sort:"closing_date" -%}

<link rel='stylesheet' href='../assets/css/gridify.css' />

<!-- Filter dropdowns -->
<!-- Commenting out the filter for now until we have enough opportunities to warrant it
  <details open>
    <summary><h4 class="h4">{{ site.data.i18n.general.filterOptions[page.lang] }}</h4></summary>
    <form class="wb-tables-filter form-inline" data-bind-to="dataset-filter">
    <div class="row">
      <div class="form-group col-md-4">
        <label for="dt_status">{{ site.data.i18n.general.opportunities.status[page.lang] }}</label>
        <select class="form-control" id="dt_status" name="dt_status" data-column="1">
          <option value="">&nbsp;</option>
          <option value="{{ site.data.i18n.general.opportunities.open[page.lang] }}">{{ site.data.i18n.general.opportunities.open[page.lang] }}</option>
          <option value="{{ site.data.i18n.general.opportunities.closed[page.lang] }}">{{ site.data.i18n.general.opportunities.closed[page.lang] }}</option>
        </select>
      </div>
      <div class="form-group col-md-4">
        <label for="dt_skills">{{ site.data.i18n.general.opportunities.skill[page.lang] }}</label>
        <select class="form-control" id="dt_skills" name="dt_skills" data-column="5">
          <option value="">&nbsp;</option>
          {%- assign skills_arr = "" | split: ',' -%}
          {%- for post in aPost -%}
            {%- assign skills_arr1 = post.skills | split: ',' -%}
            {%- for skill in skills_arr1 -%}
              {%- assign skills_arr = skills_arr | push: skill -%}
            {%- endfor -%}
          {%- endfor -%}
          {%- assign skills_arr = skills_arr | uniq -%}
          {%- for skills in skills_arr -%}
            <option value="{{ skills }}">{{ skills }}</option>
          {%- endfor -%}
        </select>
      </div>
      <div class="form-group col-md-4">
          <button type="submit" class="btn btn-primary" aria-controls="dataset-filter">{{ site.data.i18n.general.filter[page.lang] }}</button>
          <button type="reset" class="btn btn-default">{{ site.data.i18n.general.clear[page.lang] }}</button>
      </div>
    </div>
    </form>
  </details>
-->
<div>

<details open>
  <summary><h2>{{ site.data.i18n.general.opportunities.open[page.lang] }}</h2></summary>
  <!-- Data Table open opportunities-->

  <div class="mrgn-bttm-lg">
   <!-- > <table class="wb-tables tbl-gridify" id="dataset-filter" data-wb-tables='{"order": [3, "desc"], "language": {"emptyTable": "{{ site.data.i18n.general.opportunities.noOpen[page.lang] }}"}, "searching": false, "columnDefs": [{"targets": [], "visible": false}], "paging": false, "info": false}'>
      <thead>
        <tr>
          <th>{{ site.data.i18n.general.Opportunities[page.lang] }}</th>
          <th></th>
          <th>{{ site.data.i18n.general.opportunities.closing[page.lang] }}</th>
          <th>{{ site.data.i18n.general.opportunities.value[page.lang] }}</th>
          <th>{{ site.data.i18n.general.opportunities.short_desc[page.lang] }}</th>
          <th>{{ site.data.i18n.general.opportunities.skills[page.lang] }}</th>
        </tr>
      </thead>
      <tbody class="row wb-eqht"> -->
        {%- for post in aPost -%}
          {%- capture nowXML -%}{{ 'now' | date_to_xmlschema }}{%- endcapture -%}
          {%- capture closeXML -%}{{ post.closing_date | date_to_xmlschema }}{%- endcapture -%}
            {%- if closeXML > nowXML -%}
              <div class="col-xs-12 col-md-6">
              <div class="panel panel-default position-relative">
              <div class="panel-heading">
                <p><a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></p>
                <div class="panel-body"><p>
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
                <span class="glyphicon glyphicon-calendar"></span>&nbsp;<strong>{{ site.data.i18n.general.opportunities.closing[page.lang] }}:</strong>&nbsp;{{ closeDate }}, {{ site.data.i18n.general.opportunities.easternTime[page.lang] }}
                </p>
                <p><strong>{{ site.data.i18n.general.opportunities.value[page.lang] }}:</strong>&nbsp;{{ post.value }}</p>
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
      <!-- ></tbody>
    </table> <-->
  </div>
  </details>

  <details>
    <summary><h2>{{ site.data.i18n.general.opportunities.closed[page.lang] }}</h2></summary>
    <section>
    <!-- > <div class="mrgn-bttm-lg">
      <table class="wb-tables tbl-gridify" data-wb-tables='{"order": [3, "desc"], "language": {"emptyTable": "{{ site.data.i18n.general.opportunities.noClosed[page.lang] }}"}, "searching": false, "columnDefs": [{"targets": [], "visible": false}], "paging": false, "info": false}'>
        <thead>
          <tr>
            <th>{{ site.data.i18n.general.Opportunities[page.lang] }}</th>
            <th>{{ site.data.i18n.general.opportunities.closing[page.lang] }}</th>
            <th>{{ site.data.i18n.general.opportunities.value[page.lang] }}</th>
            <th>{{ site.data.i18n.general.opportunities.short_desc[page.lang] }}</th>
            <th>{{ site.data.i18n.general.opportunities.skills[page.lang] }}</th>
          </tr>
        </thead>
        <tbody class="row wb-eqht"><-->
        <div class="row wb-eqht">
          {%- for post in aPost -%}
            {%- capture nowXML -%}{{ 'now' | date_to_xmlschema }}{%- endcapture -%}
            {%- capture closeXML -%}{{ post.closing_date | date_to_xmlschema }}{%- endcapture -%}
            {%- if closeXML < nowXML -%}
              <div class="col-xs-12 col-md-6">
              <div class="panel panel-default position-relative">
              <div class="panel-heading">
                <p><a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></p></div>
                <div class="panel-body"><p>
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
          <!-- >
        </tbody>
      </table> <-->
    </div>
    </section>
  </details>
</div>
