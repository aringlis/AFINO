
Welcome to this site for hosting the AFINO flare catalogue. 

<ul>
<table border="1" cellpadding="4" cellspacing="1" style="border-collapse: collapse">
  {% for item in site.data.afino_master_record %}
    <tr>
      {{ item.Date }},{{ item.Instrument }},{{ item.Detection }},{{ item.period }}
    </tr>
  {% endfor %}
</table>
</ul>
