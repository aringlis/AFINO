
Welcome to this site for hosting the AFINO flare catalogue. 

<ul>
  {% for item in site.data.afino_master_record %}
    <li>
      {{ item.Date }}-{{ item.GOES class }}
    </li>
  {% endfor %}
</ul>
