---
title: Bhajans
layout: default
pdfs: ["Aao Kanhaiya Aao", "Chandi ke Sinhasan", "Choti Choti Gaiya", "Darjee Sim De", "Jay Shri Shyam", "Kirtan Ki Hai Raat", "Shyam Ki Bhakti", "Thane Parde Mein"]
audios: ["160656359","160656349","160656342","160656334","160656325","160656307","160656302","160656294","160656283"]
videos: ["xNPcA-lE64I","6e23YUwWiCM","KSesAwAfyZ8","dca7Rkj-WXY","nS83m_qolBY","JI20M29Eku8","S9lmHetm828","JMVq_bFKTyc"]
---
### PDF
<div id="pdfs">
{% for i in page.pdfs %}
<p><a href="/files/bhajans/{{ i | replace: " ","-" }}.pdf" target="_blank">{{i}}</a></p>
{% endfor %}
</div>

### Audio
<div id="audios">
<ul class="list">
{% for i in page.audios %}
<li class="soundcloud">{% include soundcloud.htm id=i %}</li>
{% endfor %}
</ul>
<ul class="pagination"></ul>
</div>

### Video
<div id="videos">
<ul class="list">
{% for i in page.videos %}
<li class="youtube"><iframe width="340" height="250" src="//www.youtube.com/embed/{{i}}" frameborder="0" allowfullscreen></iframe></li>
{% endfor %}
</ul>
<ul class="pagination"></ul>
</div>
<script src="//cdnjs.cloudflare.com/ajax/libs/fancybox/2.1.5/jquery.fancybox.min.js"></script>
<script src="//cdnjs.cloudflare.com/ajax/libs/list.js/1.1.1/list.min.js"></script>
<script src="//cdnjs.cloudflare.com/ajax/libs/list.pagination.js/0.1.0/list.pagination.min.js"></script>
<script>
var al = new List('audios', {
  valueNames: ['soundcloud'],
  page: 4,
  plugins: [ ListPagination({}) ] 
});
var vl = new List('videos', {
  valueNames: ['youtube'],
  page: 4,
  plugins: [ ListPagination({}) ] 
});
</script>
<script>$(document).ready(function() {
$("#pdfs a").fancybox();
});</script>
