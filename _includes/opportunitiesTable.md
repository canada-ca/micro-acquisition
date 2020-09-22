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
  <table class="wb-tables table table-striped table-hover" id="dataset-filter" data-wb-tables='{"order": [0, "asc"], "paging": true}'>
    <thead>
      <tr>
        <th>Title</th>
        <th>Team</th>
        <th>Department</th>
        <th>Status</th>
        <th>Posted</th>
      </tr>
    </thead>
    <tbody>
      {%- for post in aPost -%}
        <td><a class="post-link" href="/devex-pages{{ post.url }}">{{ post.title }}</a></td>
        <td>{{ post.team }}</td>
        <td>{{ post.dept_id }}</td>
        <td>{{ post.status }}</td>
        <td>{{ post.date | date: "%Y-%m-%d" }}</td>
      {%- endfor -%}
    </tbody>
  </table>
</div>

</div>
{% else %}
No opportunities, check back later..
{% endif %}
