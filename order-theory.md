# Order theory

<pre class="Agda"><a id="25" class="Symbol">{-#</a> <a id="29" class="Keyword">OPTIONS</a> <a id="37" class="Pragma">--without-K</a> <a id="49" class="Pragma">--exact-split</a> <a id="63" class="Symbol">#-}</a>

<a id="68" class="Keyword">module</a> <a id="75" href="order-theory.html" class="Module">order-theory</a> <a id="88" class="Keyword">where</a>

<a id="95" class="Keyword">open</a> <a id="100" class="Keyword">import</a> <a id="107" href="order-theory.chains-posets.html" class="Module">order-theory.chains-posets</a> <a id="134" class="Keyword">public</a>
<a id="141" class="Keyword">open</a> <a id="146" class="Keyword">import</a> <a id="153" href="order-theory.chains-preorders.html" class="Module">order-theory.chains-preorders</a> <a id="183" class="Keyword">public</a>
<a id="190" class="Keyword">open</a> <a id="195" class="Keyword">import</a> <a id="202" href="order-theory.decidable-subposets.html" class="Module">order-theory.decidable-subposets</a> <a id="235" class="Keyword">public</a>
<a id="242" class="Keyword">open</a> <a id="247" class="Keyword">import</a> <a id="254" href="order-theory.decidable-subpreorders.html" class="Module">order-theory.decidable-subpreorders</a> <a id="290" class="Keyword">public</a>
<a id="297" class="Keyword">open</a> <a id="302" class="Keyword">import</a> <a id="309" href="order-theory.directed-complete-posets.html" class="Module">order-theory.directed-complete-posets</a> <a id="347" class="Keyword">public</a>
<a id="354" class="Keyword">open</a> <a id="359" class="Keyword">import</a> <a id="366" href="order-theory.directed-families.html" class="Module">order-theory.directed-families</a> <a id="397" class="Keyword">public</a>
<a id="404" class="Keyword">open</a> <a id="409" class="Keyword">import</a> <a id="416" href="order-theory.finite-posets.html" class="Module">order-theory.finite-posets</a> <a id="443" class="Keyword">public</a>
<a id="450" class="Keyword">open</a> <a id="455" class="Keyword">import</a> <a id="462" href="order-theory.finite-preorders.html" class="Module">order-theory.finite-preorders</a> <a id="492" class="Keyword">public</a>
<a id="499" class="Keyword">open</a> <a id="504" class="Keyword">import</a> <a id="511" href="order-theory.finitely-graded-posets.html" class="Module">order-theory.finitely-graded-posets</a> <a id="547" class="Keyword">public</a>
<a id="554" class="Keyword">open</a> <a id="559" class="Keyword">import</a> <a id="566" href="order-theory.greatest-lower-bounds-posets.html" class="Module">order-theory.greatest-lower-bounds-posets</a> <a id="608" class="Keyword">public</a>
<a id="615" class="Keyword">open</a> <a id="620" class="Keyword">import</a> <a id="627" href="order-theory.interval-subposets.html" class="Module">order-theory.interval-subposets</a> <a id="659" class="Keyword">public</a>
<a id="666" class="Keyword">open</a> <a id="671" class="Keyword">import</a> <a id="678" href="order-theory.large-posets.html" class="Module">order-theory.large-posets</a> <a id="704" class="Keyword">public</a>
<a id="711" class="Keyword">open</a> <a id="716" class="Keyword">import</a> <a id="723" href="order-theory.large-preorders.html" class="Module">order-theory.large-preorders</a> <a id="752" class="Keyword">public</a>
<a id="759" class="Keyword">open</a> <a id="764" class="Keyword">import</a> <a id="771" href="order-theory.largest-elements-posets.html" class="Module">order-theory.largest-elements-posets</a> <a id="808" class="Keyword">public</a>
<a id="815" class="Keyword">open</a> <a id="820" class="Keyword">import</a> <a id="827" href="order-theory.largest-elements-preorders.html" class="Module">order-theory.largest-elements-preorders</a> <a id="867" class="Keyword">public</a>
<a id="874" class="Keyword">open</a> <a id="879" class="Keyword">import</a> <a id="886" href="order-theory.least-elements-posets.html" class="Module">order-theory.least-elements-posets</a> <a id="921" class="Keyword">public</a>
<a id="928" class="Keyword">open</a> <a id="933" class="Keyword">import</a> <a id="940" href="order-theory.least-elements-preorders.html" class="Module">order-theory.least-elements-preorders</a> <a id="978" class="Keyword">public</a>
<a id="985" class="Keyword">open</a> <a id="990" class="Keyword">import</a> <a id="997" href="order-theory.locally-finite-posets.html" class="Module">order-theory.locally-finite-posets</a> <a id="1032" class="Keyword">public</a>
<a id="1039" class="Keyword">open</a> <a id="1044" class="Keyword">import</a> <a id="1051" href="order-theory.maximal-chains-posets.html" class="Module">order-theory.maximal-chains-posets</a> <a id="1086" class="Keyword">public</a>
<a id="1093" class="Keyword">open</a> <a id="1098" class="Keyword">import</a> <a id="1105" href="order-theory.maximal-chains-preorders.html" class="Module">order-theory.maximal-chains-preorders</a> <a id="1143" class="Keyword">public</a>
<a id="1150" class="Keyword">open</a> <a id="1155" class="Keyword">import</a> <a id="1162" href="order-theory.meet-semilattices.html" class="Module">order-theory.meet-semilattices</a> <a id="1193" class="Keyword">public</a>
<a id="1200" class="Keyword">open</a> <a id="1205" class="Keyword">import</a> <a id="1212" href="order-theory.planar-binary-trees.html" class="Module">order-theory.planar-binary-trees</a> <a id="1245" class="Keyword">public</a>
<a id="1252" class="Keyword">open</a> <a id="1257" class="Keyword">import</a> <a id="1264" href="order-theory.posets.html" class="Module">order-theory.posets</a> <a id="1284" class="Keyword">public</a>
<a id="1291" class="Keyword">open</a> <a id="1296" class="Keyword">import</a> <a id="1303" href="order-theory.preorders.html" class="Module">order-theory.preorders</a> <a id="1326" class="Keyword">public</a>
<a id="1333" class="Keyword">open</a> <a id="1338" class="Keyword">import</a> <a id="1345" href="order-theory.subposets.html" class="Module">order-theory.subposets</a> <a id="1368" class="Keyword">public</a>
<a id="1375" class="Keyword">open</a> <a id="1380" class="Keyword">import</a> <a id="1387" href="order-theory.subpreorders.html" class="Module">order-theory.subpreorders</a> <a id="1413" class="Keyword">public</a>
<a id="1420" class="Keyword">open</a> <a id="1425" class="Keyword">import</a> <a id="1432" href="order-theory.total-posets.html" class="Module">order-theory.total-posets</a> <a id="1458" class="Keyword">public</a>
<a id="1465" class="Keyword">open</a> <a id="1470" class="Keyword">import</a> <a id="1477" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a> <a id="1506" class="Keyword">public</a>
</pre>