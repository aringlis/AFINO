
Welcome to the AFINO flare catalogue

<table>
<colgroup>
<col width="30%" />
<col width="70%" />
</colgroup>
<thead>
<tr class="header">
<th>Field</th>
<th>Description</th>
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






 
