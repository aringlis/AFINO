---
datatable: true
---

Welcome to the AFINO flare catalogue


<div class="datatable-begin"></div>

<table class="display" data-order='[[ 1, "asc" ]]'>
<thead>
<tr class="header">
<th>Date</th>
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
  <td> {{ row.Instrument}} </td>
  <td> {{ row.Wavelength}} </td>
  <td> {{ row.Detection}} </td>
  <td> {{ row.period }} </td>
  </tr>
{% endfor %}
</tbody>
</table>

<div class="datatable-end"></div>




 
