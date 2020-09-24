{%- assign aPost = site.posts | where:"lang", page.lang -%}
{%- if aPost.size > 0 -%}
<div class="row">

<!-- Filter dropdowns -->
<div class="col-md-3">
  <details open>
    <summary><h4 class="h4">{{ site.data.i18n.general.filterOptions[page.lang] }}</h4></summary>
    <form class="wb-tables-filter" data-bind-to="dataset-filter">

      <div class="form-group">
        <label for="dt_status">Status</label>
        <select class="form-control" id="dt_status" name="dt_status" data-column="2">
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

      <div class="form-group">
        <label for="dt_skills">Skills</label>
        <select class="form-control" id="dt_skills" name="dt_skills" data-column="1">
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

      <div class="row">
        <div class="col-xs-6">
          <button type="submit" class="btn btn-primary" aria-controls="dataset-filter">{{ site.data.i18n.general.filter[page.lang] }}</button>
        </div>
        <div class="col-xs-6">
          <button type="reset" class="btn btn-default">{{ site.data.i18n.general.clear[page.lang] }}</button>
        </div>
      </div>

    </form>
  </details>
</div>

<!-- Data Table -->
<div class="col-md-9 mrgn-bttm-lg">
  <table class="wb-tables table table-striped table-hover" id="dataset-filter" data-wb-tables='{"order": [3, "desc"], "columnDefs": [{"targets": [4,5], "visible": false}], "paging": true}'>
    <thead>
      <tr>
        <th>Opportunity</th>
        <th>Skills</th>
        <th>Status</th>
        <th>Posted</th>
        <th>Team</th>
        <th>Department</th>
      </tr>
    </thead>
    <tbody>
      {%- for post in aPost -%}
        <tr>
          <td><a class="post-link" href="/devex-pages{{ post.url }}">{{ post.title }}</a></td>
          <td>{{ post.skills }}</td>
          {%- if post.status == "Open" or post.status == "Ouvert" -%}
            <td><span class="bg-success">{{ post.status }}</span></td>
          {%- elsif post.status == "Closed" or post.status == "Fermé" -%}
            <td><span class="bg-danger">{{ post.status }}</span></td>
          {%- else -%}
            <td>{{ post.status }}</td>
          {% endif %}
          <td>{{ post.date | date: "%Y-%m-%d" }}</td>
          <td>{{ post.team }}</td>
          <td>{{ post.department }}</td>
        </tr>
      {%- endfor -%}
    </tbody>
  </table>
</div>

</div>
{%- else -%}
No opportunities, check back later..
{%- endif -%}
