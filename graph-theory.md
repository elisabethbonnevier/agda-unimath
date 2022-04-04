# Graph theory

<pre class="Agda"><a id="25" class="Symbol">{-#</a> <a id="29" class="Keyword">OPTIONS</a> <a id="37" class="Pragma">--without-K</a> <a id="49" class="Pragma">--exact-split</a> <a id="63" class="Symbol">#-}</a>

<a id="68" class="Keyword">module</a> <a id="75" href="graph-theory.html" class="Module">graph-theory</a> <a id="88" class="Keyword">where</a>
</pre>
<pre class="Agda"><a id="107" class="Keyword">open</a> <a id="112" class="Keyword">import</a> <a id="119" href="graph-theory.connected-undirected-graphs.html" class="Module">graph-theory.connected-undirected-graphs</a> <a id="160" class="Keyword">public</a>
<a id="167" class="Keyword">open</a> <a id="172" class="Keyword">import</a> <a id="179" href="graph-theory.directed-graphs.html" class="Module">graph-theory.directed-graphs</a> <a id="208" class="Keyword">public</a>
<a id="215" class="Keyword">open</a> <a id="220" class="Keyword">import</a> <a id="227" href="graph-theory.edge-coloured-undirected-graphs.html" class="Module">graph-theory.edge-coloured-undirected-graphs</a> <a id="272" class="Keyword">public</a>
<a id="279" class="Keyword">open</a> <a id="284" class="Keyword">import</a> <a id="291" href="graph-theory.equivalences-undirected-graphs.html" class="Module">graph-theory.equivalences-undirected-graphs</a> <a id="335" class="Keyword">public</a>
<a id="342" class="Keyword">open</a> <a id="347" class="Keyword">import</a> <a id="354" href="graph-theory.finite-graphs.html" class="Module">graph-theory.finite-graphs</a> <a id="381" class="Keyword">public</a>
<a id="388" class="Keyword">open</a> <a id="393" class="Keyword">import</a> <a id="400" href="graph-theory.incidence-undirected-graphs.html" class="Module">graph-theory.incidence-undirected-graphs</a> <a id="441" class="Keyword">public</a>
<a id="448" class="Keyword">open</a> <a id="453" class="Keyword">import</a> <a id="460" href="graph-theory.matchings.html" class="Module">graph-theory.matchings</a> <a id="483" class="Keyword">public</a>
<a id="490" class="Keyword">open</a> <a id="495" class="Keyword">import</a> <a id="502" href="graph-theory.mere-equivalences-undirected-graphs.html" class="Module">graph-theory.mere-equivalences-undirected-graphs</a> <a id="551" class="Keyword">public</a>
<a id="558" class="Keyword">open</a> <a id="563" class="Keyword">import</a> <a id="570" href="graph-theory.morphisms-directed-graphs.html" class="Module">graph-theory.morphisms-directed-graphs</a> <a id="609" class="Keyword">public</a>
<a id="616" class="Keyword">open</a> <a id="621" class="Keyword">import</a> <a id="628" href="graph-theory.morphisms-undirected-graphs.html" class="Module">graph-theory.morphisms-undirected-graphs</a> <a id="669" class="Keyword">public</a>
<a id="676" class="Keyword">open</a> <a id="681" class="Keyword">import</a> <a id="688" href="graph-theory.orientations-undirected-graphs.html" class="Module">graph-theory.orientations-undirected-graphs</a> <a id="732" class="Keyword">public</a>
<a id="739" class="Keyword">open</a> <a id="744" class="Keyword">import</a> <a id="751" href="graph-theory.paths-undirected-graphs.html" class="Module">graph-theory.paths-undirected-graphs</a> <a id="788" class="Keyword">public</a>
<a id="795" class="Keyword">open</a> <a id="800" class="Keyword">import</a> <a id="807" href="graph-theory.polygons.html" class="Module">graph-theory.polygons</a> <a id="829" class="Keyword">public</a>
<a id="836" class="Keyword">open</a> <a id="841" class="Keyword">import</a> <a id="848" href="graph-theory.reflexive-graphs.html" class="Module">graph-theory.reflexive-graphs</a> <a id="878" class="Keyword">public</a>
<a id="885" class="Keyword">open</a> <a id="890" class="Keyword">import</a> <a id="897" href="graph-theory.regular-undirected-graphs.html" class="Module">graph-theory.regular-undirected-graphs</a> <a id="936" class="Keyword">public</a>
<a id="943" class="Keyword">open</a> <a id="948" class="Keyword">import</a> <a id="955" href="graph-theory.simple-undirected-graphs.html" class="Module">graph-theory.simple-undirected-graphs</a> <a id="993" class="Keyword">public</a>
<a id="1000" class="Keyword">open</a> <a id="1005" class="Keyword">import</a> <a id="1012" href="graph-theory.undirected-graphs.html" class="Module">graph-theory.undirected-graphs</a> <a id="1043" class="Keyword">public</a>
</pre>