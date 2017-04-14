
Welcome to the AFINO flare catalogue

<table>
<thead>
<tr class="header">
<th>Date</th>
<th>GOES Class</th>
<th>Instrument</th>
<th>Period</th>
</tr>
</thead>
<tbody>

{% for row in site.data.afino_master_record %}
  <tr>
  <td> {{ row.Date }} </td>
  <td> {{ row.GOES_class}} <td>
  <td> {{ row.Instrument}} </td>
  <td> {{ row.period }} </td>
  </tr>
{% endfor %}
</tbody>
</table>






 
