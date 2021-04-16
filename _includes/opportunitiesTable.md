{%- assign aPost = site.posts | where:"lang", page.lang -%}
{%- if aPost.size > 0 -%}

<!-- Filter dropdowns -->

  <details open>
    <summary><h4 class="h4">{{ site.data.i18n.general.filterOptions[page.lang] }}</h4></summary>
    <form class="wb-tables-filter form-inline" data-bind-to="dataset-filter">
<div class="row">
      <div class="form-group col-md-4">
        <label for="dt_status">{{ site.data.i18n.general.opportunities.status[page.lang] }}</label>
        <select class="form-control" id="dt_status" name="dt_status" data-column="3">
          <option value="">&nbsp;</option>
          {%- assign status_arr = "" | split: ',' -%}
          {%- for post in aPost -%}
            {%- assign status_arr = status_arr | push: post.status -%}
          {%- endfor -%}
          {%- assign status_arr = status_arr | uniq -%}
          {%- for status in status_arr -%}
            <option value="{{ status }}">{{ status }}</option>
          {%- endfor -%}
        </select>
      </div>

  <div class="form-group col-md-4">
        <label for="dt_skills">{{ site.data.i18n.general.opportunities.skill[page.lang] }}</label>
        <select class="form-control" id="dt_skills" name="dt_skills" data-column="2">
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

<div class="row">

<!-- Data Table -->
<div class="mrgn-bttm-lg">
  <table class="wb-tables tbl-gridify" id="dataset-filter" data-wb-tables='{"order": [3, "desc"], "columnDefs": [{"targets": [6,7], "visible": false}], "paging": false}'>
    <thead>
      <tr>
        <th>{{ site.data.i18n.general.Opportunities[page.lang] }}</th>
        <th>{{ site.data.i18n.general.opportunities.status[page.lang] }}</th>
        <th>{{ site.data.i18n.general.opportunities.closing[page.lang] }}</th>
        <th>{{ site.data.i18n.general.opportunities.value[page.lang] }}</th>
        <th>{{ site.data.i18n.general.opportunities.short_desc[page.lang] }}</th>
        <th>{{ site.data.i18n.general.opportunities.skills[page.lang] }}</th>
      </tr>
    </thead>
    <tbody class="row wb-eqht">
      {%- for post in aPost -%}
        <tr class="col-xs-12 col-md-6">
          <td><a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></td>
          <td>{{ site.data.i18n.general.opportunities.status[page.lang] }}:&nbsp;
            {%- if post.status == "Open" or post.status == "Ouvert" -%}
              <span class="bg-success">{{ post.status }}</span>
          <td>{{ site.data.i18n.general.opportunities.closing[page.lang] }}:&nbsp;{{ post.closing_date | date: "%Y-%m-%d" }}</td>
          <td>{{ post.value }}</td>
          <td>{{ post.short_desc }}</td>
          <td>{{ site.data.i18n.general.opportunities.skills[page.lang] }}:&nbsp;
            {%- assign skills = post.skills | split: ", " -%}
            {%- for skill in skills -%}
            <span class="label label-primary">{{ skill }}</span>&nbsp;
            {%- endfor -%}
          </td>
            {%- elsif post.status == "Closed" or post.status == "Fermé" -%}
            <!-- If status is closed, do not include the closing date -->
              <span class="bg-danger">{{ post.status }}</span>
          <td>{{ post.value }}</td>
          <td>{{ post.short_desc }}</td>
          <td>{{ site.data.i18n.general.opportunities.skills[page.lang] }}:&nbsp;
            {%- assign skills = post.skills | split: ", " -%}
            {%- for skill in skills -%}
            <span class="label label-primary">{{ skill }}</span>&nbsp;
            {%- endfor -%}
          </td>
            {%- else -%}
              {{ post.status }}
            {%- endif -%}
          </td>
        </tr>
      {%- endfor -%}
    </tbody>
  </table>
</div>

</div>
{%- else -%}
No opportunities, check back later..
{%- endif -%}
