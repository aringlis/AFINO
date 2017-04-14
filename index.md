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
<th>Start time</th>
<th>End time</th>
<th>Wavelength</th>
<th>&Delta;BIC S<sub>0</sub> vs S<sub>1</sub> </th>
<th>&Delta;BIC S<sub>0</sub> vs S<sub>2</sub> </th>
<th>&Delta;BIC S<sub>2</sub> vs S<sub>1</sub> </th>

<th>Detection</th>
<th>Period</th>
</tr>
</thead>
<tbody>

{% for row in site.data.afino_master_record %}
  <tr>
  <td> {{ row.Date }} </td>
  <td> {{row.GOES_class}}</td>
  <td> {{row.Start_time}} </td>
  <td> {{row.End_time}} </td>
  <td> {{ row.Instrument}} </td>
  <td> {{ row.Wavelength}} </td>
  <td> {{row.dBIC_0v1}} </td>
  <td> {{row.dBIC_0v2}} </td>
  <td> {{row.dBIC_2v1}} </td>
  <td> {{ row.Detection}} </td>
  <td> {{ row.period }} </td>
  </tr>
{% endfor %}
</tbody>
</table>


{%for row in site.data.afino_master_record %}
<p> {{row.GOES\ class}} </p>
{% endfor %}

 
