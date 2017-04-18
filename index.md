---
layout: default
datatable: true
---


<nav>
<ul>
<li><a href="/AFINO/about">More Information</a></li>
</ul>
    </nav>


# About this catalogue

AFINO was designed to automatically search solar X-ray data for signatures consistent with quasi-periodic pulsations (QPP) in solar flares. Currently, AFINO runs daily, analysing any new substantial solar flares observed by the GOES-15 (Geostationary Operational Environmental Satellite) X-ray sensor. Over 600 analysed flares are in the results database, which begins in early 2011.

The main feature of AFINO is the use of a model comparison technique to analyse the Fourier Power Spectral Density (PSD) of solar flare time series data. Events showing a strong preference for a localized frequency enhancement in the PSD are flagged as flares of interest (see bold entries).

These results are freely available for reference by anyone interested. If you do make use of this list, please cite the following papers where the AFINO techniques and results were published: [Inglis et al. ApJ, 798, 108, (2015)](http://iopscience.iop.org/article/10.1088/0004-637X/798/2/108) , [Inglis et al., ApJ, 833, 284, (2016)](http://iopscience.iop.org/article/10.3847/1538-4357/833/2/284/). 


<table id="keys" class="display">
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
<td markdown="span">&Delta;BIC S<sub>0</sub> vs S<sub>1</sub></td>
<td markdown="span">The difference in BIC between models S0 and S1. A positive value >10 indicates a strong preference for S1 over S0 </td>
</tr>
<tr>
<td markdown="span">&Delta;BIC S<sub>0</sub> vs S<sub>2</sub></td>
<td markdown="span">The difference in BIC between models S0 and S2. A positive value >10 indicates a strong preference for S2 over S0 </td>
</tr>
<tr>
<td markdown="span">&Delta;BIC S<sub>2</sub> vs S<sub>1</sub></td>
<td markdown="span">The difference in BIC between models S2 and S1. A positive value >10 indicates a strong preference for S1 over S2 </td>
</tr>
<tr>
<td markdown="span">Detection</td>
<td markdown="span">If model S1 is preferred over all others by ΔBIC > 10, the criteria are met for a QPP detection  </td>
</tr>
<tr>
<td markdown="span"> p<sub>Sn</sub></td>
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


<div class="display" style="height:100%; width:140%; font-size:	12px; overflow:auto;">

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
<th style="font-size: 16px">&Delta;BIC S<sub>2</sub> vs S<sub>1</sub> </th>
<th style="font-size: 16px">Detection</th>
<th style="font-size: 16px">p<sub>S0</sub></th>
<th style="font-size: 16px">p<sub>S1</sub></th>
<th style="font-size: 16px">p<sub>S2</sub></th>
<th style="font-size: 16px">P(s)</th>
<th style="font-size: 16px">Width</th>
<th style="font-size: 16px">Flags</th>
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
  <td> {{row.probability_m0 | round:3 }}  </td>
  <td> {{row.probability_m2 | round:3}} </td>
  <td> {{row.probability_m2 | round:3}} </td>
  <td> {{row.period}} </td>
  <td> {{row.width | round:2}} </td>
  <td> {{row.Flags}} </td>
  </tr>
{% endfor %}
</tbody>
</table>

</div>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
<script type="text/javascript" charset="utf8" src="https://cdn.datatables.net/1.10.13/js/jquery.dataTables.min.js"></script>

<script type="text/javascript"
        src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

<script>
 
$(document).ready(function() {
    $("#catalogue").dataTable( {
        paging: false,
        'data-sort': true,
        order: [[ 0, "desc" ]],
        stateSave: true,
        searching: true
    });
});
</script>

