---
datatable: true
---

<head>
<script type="text/javascript" class="init">
 $(document).ready(function() {
    $('#catalogue').DataTable( {
    "ordering": true
    } );
} );
</script>
</head>

# About this catalogue

AFINO was designed to search for signatures consistent with quasi-periodic pulsations (QPP) in solar flares. It uses a model comparison technique to analyse the Fourier Power Spectral Density (PSD) of solar flares in GOES 1-8A X-ray data. Events showing a strong preference for a localized frequency enhancement in the PSD are flagged as flares of interest (see bold entries).

These results are freely available for reference by anyone interested. If you do make use of this list, please cite the following papers where the AFINO techniques and results were published: [Inglis et al. ApJ, 798, 108, (2015)](http://iopscience.iop.org/article/10.1088/0004-637X/798/2/108) , [Inglis et al., ApJ, 833, 284, (2016)](http://iopscience.iop.org/article/10.3847/1538-4357/833/2/284/). 

<div style="height:100%; width:140%; font-size:	12px; overflow:auto;">

<table id="catalogue" class="display" data-order='[[ 1, "asc" ]]'>
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
<th>&chi;<sup>2</sup><sub>S0</sub> &nbsp;</th>
<th>p<sub>S0</sub></th>
<th>&chi;<sup>2</sup><sub>S1</sub> &nbsp;</th>
<th>p<sub>S1</sub></th>
<th>&chi;<sup>2</sup><sub>S2</sub> &nbsp;</th>
<th>p<sub>S2</sub></th>
<th>P (s)</th>
<th>Width</th>
<th>Flags</th>
</tr>
</thead>
<tbody>

{% for row in site.data.afino_master_record %}
  <tr>
  <td> {{ row.Date }} </td>
  <td> {{row.GOES_class}}</td>
  <td> {{ row.Instrument}} </td>
  <td> {{row.Start_time}} </td>
  <td> {{row.End_time}} </td>
  <td> {{row.Wavelength}} </td>
  <td> {{row.dBIC_0v1 | round:1 }} </td>
  <td> {{row.dBIC_0v2 | round:1 }} </td>
  <td> {{row.dBIC_2v1 | round:1 }} </td>
  <td> {{row.Detection}} </td>
  <td> {{row.rchi2_m0 | round:2 }} </td>
  <td> {{row.probability_m0 | round:3 }}  </td>
  <td> {{row.rchi2_m1 | round:2}} </td>
  <td> {{row.probability_m2 | round:3}} </td>
  <td> {{row.rchi2_m2 | round:2}} </td>
  <td> {{row.probability_m2 | round:3}} </td>
  <td> {{row.period}} </td>
  <td> {{row.width | round:2}} </td>
  <td> {{row.Flags}} </td>
  </tr>
{% endfor %}
</tbody>
</table>

</div>
