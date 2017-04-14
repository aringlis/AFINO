---
datatable: true
---

<script>
$(document).ready(function(){
    $('table.display').DataTable( {
        paging: true,
        stateSave: true,
        searching: true
    }
        );
});
</script>

Welcome to the AFINO flare catalogue




<table class="display">
<thead>
<tr class="header">
<th>Date</th>
<th>GOES class</th>
<th>Instrument</th>
<th>Wavelength</th>
<th>Detection</th>
<th>Period</th>
</tr>
</thead>
<tbody>

{% for row in site.data.afino_master_record %}
  <tr>
  <td> {{ row.Date }} </td>
  <td> {{row.GOES_class}}</td>
  <td> {{ row.Instrument}} </td>
  <td> {{ row.Wavelength}} </td>
  <td> {{ row.Detection}} </td>
  <td> {{ row.period }} </td>
  </tr>
{% endfor %}
</tbody>
</table>


{%for row in site.data.afino_master_record %}
<p> {{"row.GOES class"}} </p>
{% endfor %}

 
