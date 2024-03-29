---
layout: default
datatable: true
---

<div class="topnav" style="background-color: #333; font-weight: bold; width:100%; padding: 4px; font-size: 18px; display: block">
<ul style="list-style-type: None">
    <li style="display: inline; padding-right: 20px"><a href="/AFINO/about">How it works</a></li>
    <li style="display: inline; padding-right: 20px"><a href="/AFINO/publications">AFINO Publications</a></li>
    </ul>
</div>


# About this catalogue

AFINO was designed to automatically search solar X-ray data for signatures consistent with quasi-periodic pulsations (QPP) in solar flares. Currently, AFINO runs daily, analysing any new substantial solar flares observed by the GOES (Geostationary Operational Environmental Satellite) X-ray sensor. Over 800 analysed flares are in the results database, which begins in early 2011.

Events between 2011 and 2019 were observed by GOES-15/XRS data at 2s cadence. Since the beginning of 2020, observations were made by GOES-16/XRS with a cadence of 1s.

The main feature of AFINO is the use of a model comparison technique to analyse the Fourier Power Spectral Density (PSD) of solar flare time series data. Events showing a strong preference for a localized frequency enhancement in the PSD are flagged as flares of interest (see the Detection column).

These results are freely available for reference by anyone interested. If you do make use of this list, please cite the following papers where the AFINO techniques and results were published: [Inglis et al. ApJ, 798, 108, (2015)](http://iopscience.iop.org/article/10.1088/0004-637X/798/2/108) , [Inglis et al., ApJ, 833, 284, (2016)](http://iopscience.iop.org/article/10.3847/1538-4357/833/2/284/).
  


<table id="keys" class="display compact">
<colgroup>
<col width="20%" />
<col width="80%" />
</colgroup>
<thead>
<tr class="header">
<th>Key</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td markdown="span">Model S0</td>
<td markdown="span">A single power-law plus constant model of the Power Spectral Density (PSD) </td>
</tr>
<tr>
<td markdown="span">Model S1</td>
<td markdown="span">A single power-law plus constant, plus a localized enhancement consistent with a QPP signature </td>
</tr>
<tr>
<td markdown="span">Model S2</td>
<td markdown="span">A broken-power law plus a constant </td>
</tr>
<tr>
<td markdown="span">BIC</td>
<td markdown="span">The Bayesian Information Criterion. BIC = -2 Ln(L) + k Ln(n), where L is the likelihood function  </td>
</tr>
<tr>
<td markdown="span">\\( \Delta BIC \ S_0 \ vs \ S_1 \\) </td>
<td markdown="span">The difference in BIC between models S0 and S1. A positive value >10 indicates a strong preference for S1 over S0 </td>
</tr>
<tr>
<td markdown="span">\\( \Delta BIC \ S_0 \ vs \ S_2 \\)</td>
<td markdown="span">The difference in BIC between models S0 and S2. A positive value >10 indicates a strong preference for S2 over S0 </td>
</tr>
<tr>
<td markdown="span">\\( \Delta BIC \ S_2 \ vs \ S_1 \\)</td>
<td markdown="span">The difference in BIC between models S2 and S1. A positive value >10 indicates a strong preference for S1 over S2 </td>
</tr>
<tr>
<td markdown="span">Detection</td>
<td markdown="span">If model S1 is preferred over all others by ΔBIC > 10, the criteria are met for a QPP detection  </td>
</tr>
<tr>
<td markdown="span"> \\( p_n \\)</td>
<td markdown="span">p-value associated with goodness-of-fit estimate for each model n=0,1,2  </td>
</tr>
<tr>
<td markdown="span">P (s)</td>
<td markdown="span">Best-fit period, in seconds, of the localized enhancement, where appropriate   </td>
</tr>
<tr>
<td markdown="span">width</td>
<td markdown="span">Best-fit width, in log-f space, of the localized enhancement, where appropriate    </td>
</tr>
<tr>
<td markdown="span">Flags</td>
<td markdown="span">S = short data series (less than 200 data points), B0 = bad fit to model S0 (pS0 less than 0.01), B1 = bad fit to model S1 (pS1 less than 0.01), B2 = bad fit to model S2 (pS2 less than 0.01)    </td>
</tr>

</tbody>
</table>

The full AFINO results table is shown below. The results are searchable and sortable by column. Please note that new events may take up to a few days to appear in this list, depending on data availability.


<div class="display compact" style="height:100%; width:140%; font-size:	12px; overflow:auto;">

<table id="catalogue" class="display">
<thead>
<tr class="header">
<th style="font-size: 16px" data-sort>Date</th>
<th style="font-size: 16px">GOES class</th>
<th style="font-size: 16px">Instr.</th>
<th style="font-size: 16px">Start time</th>
<th style="font-size: 16px">End time</th>
<th style="font-size: 16px">Wavelength</th>
<th style="font-size: 16px">&Delta;BIC S<sub>0</sub> vs S<sub>1</sub> </th>
<th style="font-size: 16px">&Delta;BIC S<sub>0</sub> vs S<sub>2</sub> </th>
<th style="font-size: 16px">&Delta;BIC S<sub>2</sub> vs S<sub>1</sub></th>
<th style="font-size: 16px">Detection</th>
<th style="font-size: 16px"> p<sub>0</sub></th>
<th style="font-size: 16px"> p<sub>1</sub> </th>
<th style="font-size: 16px"> p<sub>2</sub> </th>
<th style="font-size: 16px">P(s)</th>
<th style="font-size: 16px">Width</th>
<th style="font-size: 16px">Flags</th>
<th style="font-size: 16px">Plot</th>
<th style="font-size: 16px">Helioviewer</th>
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
  
  {% assign prob_m0 = row.probability_m0 | round:3 %}
  {% if prob_m0 >= 1 %}
      <td> {{0.000}} </td>
  {% else %}
      <td> {{prob_m0}} </td>
  {% endif %}
  
  {% assign prob_m1 = row.probability_m1 | round:3 %}
  {% if prob_m1 >= 1 %}
      <td> {{0.000}} </td>
  {% else %}
      <td> {{prob_m1}} </td>
  {% endif %}
  
  {% assign prob_m2 = row.probability_m2 | round:3 %}
  {% if prob_m2 >= 1 %}
      <td> {{0.000}} </td>
  {% else %}
      <td> {{prob_m2}} </td>
  {% endif %}
  
  <td> {{row.period}} </td>
  <td> {{row.width | round:2}} </td>
  <td> {{row.Flags}} </td>
  
  {% assign baseurl = '/AFINO/plots/summary_plot' %}
  {% assign sep = '_' %}
  {% assign end_url = '_GOES_long.pdf' %}
  {% capture full_url %}{{baseurl}}{{sep}}{{row.Date}}{{sep}}{{row.Start_time}}{{sep}}{{row.Date}}{{sep}}{{row.End_time}}{{end_url}} {% endcapture %}
  <td> <a href= '{{full_url}}'>Show</a> </td>
  
  {% assign hv_base_url = 'https://helioviewer.org/?date='%}
  {% assign hv_end_url = '&imageScale=2.42044088&imageLayers=%5BSDO,AIA,171,1,100%5D&eventLayers=%5BFL,all,1%5D&eventLabels=true'%}
  {% capture hv_date %}{{row.Date | slice: 0,4}}{{'-'}}{{row.Date | slice: 4,2}}{{'-'}}{{row.Date | slice: 6,2}}{{'T'}}{{row.Start_time | slice:0,2}}{{':'}}{{row.Start_time | slice:2,2}}{{':'}}{{row.Start_time | slice: 4,2}}{% endcapture %}
  {% capture hv_full_url %}{{hv_base_url}}{{hv_date}}{{hv_end_url}} {% endcapture %}
  <td> <a href= '{{hv_full_url}}'>Show</a> </td>
  
  </tr>
{% endfor %}
</tbody>
</table>

</div>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
<script type="text/javascript" charset="utf8" src="https://cdn.datatables.net/1.10.13/js/jquery.dataTables.min.js"></script>

<script type="text/javascript"
        src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

<script>
 
$(document).ready(function() {
    $("#catalogue").dataTable( {
        paging: true,
        pageLength: 100,
        'data-sort': true,
        order: [[ 0, "desc" ], [3, "desc"]],
        stateSave: true,
        searching: true
    });
});
</script>

