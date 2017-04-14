
Welcome to the AFINO flare catalogue

<table>
<thead>
<tr class="header">
<th>Date</th>
<th>Instrument</th>
<th>Period</th>
</tr>
</thead>
<tbody>

{% for row in site.data.afino_master_record %}
  <tr>
  <td> {{ item.Date }} </td>
  <td> {{ item.Instrument}} </td>
  <td> {{ item. period }} </td>
  </tr>
{% endfor %}
</tbody>
</table>






 
