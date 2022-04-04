# Directed graphs

<pre class="Agda"><a id="28" class="Symbol">{-#</a> <a id="32" class="Keyword">OPTIONS</a> <a id="40" class="Pragma">--without-K</a> <a id="52" class="Pragma">--exact-split</a> <a id="66" class="Symbol">#-}</a>

<a id="71" class="Keyword">module</a> <a id="78" href="graph-theory.directed-graphs.html" class="Module">graph-theory.directed-graphs</a> <a id="107" class="Keyword">where</a>

<a id="114" class="Keyword">open</a> <a id="119" class="Keyword">import</a> <a id="126" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a>
<a id="153" class="Keyword">open</a> <a id="158" class="Keyword">import</a> <a id="165" href="foundation.cartesian-product-types.html" class="Module">foundation.cartesian-product-types</a>
<a id="200" class="Keyword">open</a> <a id="205" class="Keyword">import</a> <a id="212" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a>
<a id="244" class="Keyword">open</a> <a id="249" class="Keyword">import</a> <a id="256" href="foundation.functions.html" class="Module">foundation.functions</a>
<a id="277" class="Keyword">open</a> <a id="282" class="Keyword">import</a> <a id="289" href="foundation.identity-types.html" class="Module">foundation.identity-types</a>
<a id="315" class="Keyword">open</a> <a id="320" class="Keyword">import</a> <a id="327" href="foundation.equivalences.html" class="Module">foundation.equivalences</a>
</pre>
## Idea

A graph consists of a type of vertices equipped with a binary, type valued relation of edges.

## Definition

<pre class="Agda"><a id="Graph"></a><a id="483" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a> <a id="489" class="Symbol">:</a> <a id="491" class="Symbol">(</a><a id="492" href="graph-theory.directed-graphs.html#492" class="Bound">l1</a> <a id="495" href="graph-theory.directed-graphs.html#495" class="Bound">l2</a> <a id="498" class="Symbol">:</a> <a id="500" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="505" class="Symbol">)</a> <a id="507" class="Symbol">→</a> <a id="509" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="512" class="Symbol">(</a><a id="513" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="518" href="graph-theory.directed-graphs.html#492" class="Bound">l1</a> <a id="521" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="523" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="528" href="graph-theory.directed-graphs.html#495" class="Bound">l2</a><a id="530" class="Symbol">)</a>
<a id="532" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a> <a id="538" href="graph-theory.directed-graphs.html#538" class="Bound">l1</a> <a id="541" href="graph-theory.directed-graphs.html#541" class="Bound">l2</a> <a id="544" class="Symbol">=</a> <a id="546" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="548" class="Symbol">(</a><a id="549" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="552" href="graph-theory.directed-graphs.html#538" class="Bound">l1</a><a id="554" class="Symbol">)</a> <a id="556" class="Symbol">(λ</a> <a id="559" href="graph-theory.directed-graphs.html#559" class="Bound">V</a> <a id="561" class="Symbol">→</a> <a id="563" href="graph-theory.directed-graphs.html#559" class="Bound">V</a> <a id="565" class="Symbol">→</a> <a id="567" href="graph-theory.directed-graphs.html#559" class="Bound">V</a> <a id="569" class="Symbol">→</a> <a id="571" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="574" href="graph-theory.directed-graphs.html#541" class="Bound">l2</a><a id="576" class="Symbol">)</a>

<a id="579" class="Keyword">module</a> <a id="586" href="graph-theory.directed-graphs.html#586" class="Module">_</a>
  <a id="590" class="Symbol">{</a><a id="591" href="graph-theory.directed-graphs.html#591" class="Bound">l1</a> <a id="594" href="graph-theory.directed-graphs.html#594" class="Bound">l2</a> <a id="597" class="Symbol">:</a> <a id="599" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="604" class="Symbol">}</a> <a id="606" class="Symbol">(</a><a id="607" href="graph-theory.directed-graphs.html#607" class="Bound">G</a> <a id="609" class="Symbol">:</a> <a id="611" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a> <a id="617" href="graph-theory.directed-graphs.html#591" class="Bound">l1</a> <a id="620" href="graph-theory.directed-graphs.html#594" class="Bound">l2</a><a id="622" class="Symbol">)</a>
  <a id="626" class="Keyword">where</a>

  <a id="635" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="648" class="Symbol">:</a> <a id="650" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="653" href="graph-theory.directed-graphs.html#591" class="Bound">l1</a>
  <a id="658" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="671" class="Symbol">=</a> <a id="673" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="677" href="graph-theory.directed-graphs.html#607" class="Bound">G</a>

  <a id="682" href="graph-theory.directed-graphs.html#682" class="Function">edge-Graph</a> <a id="693" class="Symbol">:</a> <a id="695" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="708" class="Symbol">→</a> <a id="710" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="723" class="Symbol">→</a> <a id="725" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="728" href="graph-theory.directed-graphs.html#594" class="Bound">l2</a>
  <a id="733" href="graph-theory.directed-graphs.html#682" class="Function">edge-Graph</a> <a id="744" class="Symbol">=</a> <a id="746" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="750" href="graph-theory.directed-graphs.html#607" class="Bound">G</a>
</pre>
### Alternative definition

<pre class="Agda"><a id="793" class="Keyword">module</a> <a id="alternative"></a><a id="800" href="graph-theory.directed-graphs.html#800" class="Module">alternative</a> <a id="812" class="Keyword">where</a>

  <a id="alternative.Graph&#39;"></a><a id="821" href="graph-theory.directed-graphs.html#821" class="Function">Graph&#39;</a> <a id="828" class="Symbol">:</a> <a id="830" class="Symbol">(</a><a id="831" href="graph-theory.directed-graphs.html#831" class="Bound">l1</a> <a id="834" href="graph-theory.directed-graphs.html#834" class="Bound">l2</a> <a id="837" class="Symbol">:</a> <a id="839" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="844" class="Symbol">)</a>  <a id="847" class="Symbol">→</a> <a id="849" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="852" class="Symbol">(</a><a id="853" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="858" href="graph-theory.directed-graphs.html#831" class="Bound">l1</a> <a id="861" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="863" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="868" href="graph-theory.directed-graphs.html#834" class="Bound">l2</a><a id="870" class="Symbol">)</a>
  <a id="874" href="graph-theory.directed-graphs.html#821" class="Function">Graph&#39;</a> <a id="881" href="graph-theory.directed-graphs.html#881" class="Bound">l1</a> <a id="884" href="graph-theory.directed-graphs.html#884" class="Bound">l2</a> <a id="887" class="Symbol">=</a> <a id="889" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="891" class="Symbol">(</a><a id="892" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="895" href="graph-theory.directed-graphs.html#881" class="Bound">l1</a><a id="897" class="Symbol">)</a>  <a id="900" class="Symbol">λ</a> <a id="902" href="graph-theory.directed-graphs.html#902" class="Bound">V</a> <a id="904" class="Symbol">→</a> <a id="906" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="908" class="Symbol">(</a><a id="909" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="912" href="graph-theory.directed-graphs.html#884" class="Bound">l2</a><a id="914" class="Symbol">)</a> <a id="916" class="Symbol">(λ</a> <a id="919" href="graph-theory.directed-graphs.html#919" class="Bound">E</a> <a id="921" class="Symbol">→</a> <a id="923" class="Symbol">(</a><a id="924" href="graph-theory.directed-graphs.html#919" class="Bound">E</a> <a id="926" class="Symbol">→</a> <a id="928" href="graph-theory.directed-graphs.html#902" class="Bound">V</a><a id="929" class="Symbol">)</a> <a id="931" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">×</a> <a id="933" class="Symbol">(</a><a id="934" href="graph-theory.directed-graphs.html#919" class="Bound">E</a> <a id="936" class="Symbol">→</a> <a id="938" href="graph-theory.directed-graphs.html#902" class="Bound">V</a><a id="939" class="Symbol">))</a>

  <a id="945" class="Keyword">module</a> <a id="952" href="graph-theory.directed-graphs.html#952" class="Module">_</a> <a id="954" class="Symbol">{</a><a id="955" href="graph-theory.directed-graphs.html#955" class="Bound">l1</a> <a id="958" href="graph-theory.directed-graphs.html#958" class="Bound">l2</a> <a id="961" class="Symbol">:</a> <a id="963" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="968" class="Symbol">}</a> <a id="970" class="Symbol">(</a><a id="971" href="graph-theory.directed-graphs.html#971" class="Bound">G</a> <a id="973" class="Symbol">:</a> <a id="975" href="graph-theory.directed-graphs.html#821" class="Function">Graph&#39;</a> <a id="982" href="graph-theory.directed-graphs.html#955" class="Bound">l1</a> <a id="985" href="graph-theory.directed-graphs.html#958" class="Bound">l2</a><a id="987" class="Symbol">)</a> <a id="989" class="Keyword">where</a>

    <a id="1000" href="graph-theory.directed-graphs.html#1000" class="Function">vertex-Graph&#39;</a> <a id="1014" class="Symbol">:</a> <a id="1016" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1019" href="graph-theory.directed-graphs.html#955" class="Bound">l1</a>
    <a id="1026" href="graph-theory.directed-graphs.html#1000" class="Function">vertex-Graph&#39;</a> <a id="1040" class="Symbol">=</a> <a id="1042" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1046" href="graph-theory.directed-graphs.html#971" class="Bound">G</a>

    <a id="1053" href="graph-theory.directed-graphs.html#1053" class="Function">edge-Graph&#39;</a> <a id="1065" class="Symbol">:</a> <a id="1067" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1070" href="graph-theory.directed-graphs.html#958" class="Bound">l2</a>
    <a id="1077" href="graph-theory.directed-graphs.html#1053" class="Function">edge-Graph&#39;</a> <a id="1089" class="Symbol">=</a> <a id="1091" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1095" class="Symbol">(</a><a id="1096" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1100" href="graph-theory.directed-graphs.html#971" class="Bound">G</a><a id="1101" class="Symbol">)</a>

    <a id="1108" href="graph-theory.directed-graphs.html#1108" class="Function">source-edge-Graph</a> <a id="1126" class="Symbol">:</a> <a id="1128" href="graph-theory.directed-graphs.html#1053" class="Function">edge-Graph&#39;</a> <a id="1140" class="Symbol">-&gt;</a> <a id="1143" href="graph-theory.directed-graphs.html#1000" class="Function">vertex-Graph&#39;</a>
    <a id="1161" href="graph-theory.directed-graphs.html#1108" class="Function">source-edge-Graph</a> <a id="1179" class="Symbol">=</a> <a id="1181" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1185" class="Symbol">(</a><a id="1186" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1190" class="Symbol">(</a><a id="1191" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1195" href="graph-theory.directed-graphs.html#971" class="Bound">G</a><a id="1196" class="Symbol">))</a>

    <a id="1204" href="graph-theory.directed-graphs.html#1204" class="Function">target-edge-Graph</a> <a id="1222" class="Symbol">:</a> <a id="1224" href="graph-theory.directed-graphs.html#1053" class="Function">edge-Graph&#39;</a> <a id="1236" class="Symbol">-&gt;</a> <a id="1239" href="graph-theory.directed-graphs.html#1000" class="Function">vertex-Graph&#39;</a>
    <a id="1257" href="graph-theory.directed-graphs.html#1204" class="Function">target-edge-Graph</a> <a id="1275" class="Symbol">=</a> <a id="1277" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1281" class="Symbol">(</a><a id="1282" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1286" class="Symbol">(</a><a id="1287" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1291" href="graph-theory.directed-graphs.html#971" class="Bound">G</a><a id="1292" class="Symbol">))</a>
</pre>
<pre class="Agda"><a id="1308" class="Keyword">module</a> <a id="equiv"></a><a id="1315" href="graph-theory.directed-graphs.html#1315" class="Module">equiv</a> <a id="1321" class="Symbol">{</a><a id="1322" href="graph-theory.directed-graphs.html#1322" class="Bound">l1</a> <a id="1325" href="graph-theory.directed-graphs.html#1325" class="Bound">l2</a> <a id="1328" class="Symbol">:</a> <a id="1330" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1335" class="Symbol">}</a> <a id="1337" class="Keyword">where</a>
  <a id="1345" class="Keyword">open</a> <a id="1350" href="graph-theory.directed-graphs.html#800" class="Module">alternative</a>

  <a id="equiv.Graph-to-Graph&#39;"></a><a id="1365" href="graph-theory.directed-graphs.html#1365" class="Function">Graph-to-Graph&#39;</a> <a id="1381" class="Symbol">:</a> <a id="1383" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a> <a id="1389" href="graph-theory.directed-graphs.html#1322" class="Bound">l1</a> <a id="1392" href="graph-theory.directed-graphs.html#1325" class="Bound">l2</a> <a id="1395" class="Symbol">-&gt;</a> <a id="1398" href="graph-theory.directed-graphs.html#821" class="Function">Graph&#39;</a> <a id="1405" href="graph-theory.directed-graphs.html#1322" class="Bound">l1</a> <a id="1408" class="Symbol">(</a><a id="1409" href="graph-theory.directed-graphs.html#1322" class="Bound">l1</a> <a id="1412" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1414" href="graph-theory.directed-graphs.html#1325" class="Bound">l2</a><a id="1416" class="Symbol">)</a>
  <a id="1420" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1424" class="Symbol">(</a><a id="1425" href="graph-theory.directed-graphs.html#1365" class="Function">Graph-to-Graph&#39;</a> <a id="1441" href="graph-theory.directed-graphs.html#1441" class="Bound">G</a><a id="1442" class="Symbol">)</a> <a id="1444" class="Symbol">=</a> <a id="1446" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="1459" href="graph-theory.directed-graphs.html#1441" class="Bound">G</a>
  <a id="1463" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1467" class="Symbol">(</a><a id="1468" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1472" class="Symbol">(</a><a id="1473" href="graph-theory.directed-graphs.html#1365" class="Function">Graph-to-Graph&#39;</a> <a id="1489" href="graph-theory.directed-graphs.html#1489" class="Bound">G</a><a id="1490" class="Symbol">))</a>
    <a id="1497" class="Symbol">=</a> <a id="1499" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="1501" class="Symbol">(</a><a id="1502" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="1515" href="graph-theory.directed-graphs.html#1489" class="Bound">G</a><a id="1516" class="Symbol">)</a> <a id="1518" class="Symbol">(λ</a> <a id="1521" href="graph-theory.directed-graphs.html#1521" class="Bound">x</a> <a id="1523" class="Symbol">→</a> <a id="1525" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="1527" class="Symbol">(</a><a id="1528" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="1541" href="graph-theory.directed-graphs.html#1489" class="Bound">G</a><a id="1542" class="Symbol">)</a> <a id="1544" class="Symbol">λ</a> <a id="1546" href="graph-theory.directed-graphs.html#1546" class="Bound">y</a> <a id="1548" class="Symbol">→</a> <a id="1550" href="graph-theory.directed-graphs.html#682" class="Function">edge-Graph</a> <a id="1561" href="graph-theory.directed-graphs.html#1489" class="Bound">G</a>  <a id="1564" href="graph-theory.directed-graphs.html#1521" class="Bound">x</a> <a id="1566" href="graph-theory.directed-graphs.html#1546" class="Bound">y</a><a id="1567" class="Symbol">)</a>
  <a id="1571" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1575" class="Symbol">(</a><a id="1576" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1580" class="Symbol">(</a><a id="1581" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1585" class="Symbol">(</a><a id="1586" href="graph-theory.directed-graphs.html#1365" class="Function">Graph-to-Graph&#39;</a> <a id="1602" href="graph-theory.directed-graphs.html#1602" class="Bound">G</a><a id="1603" class="Symbol">)))</a> <a id="1607" class="Symbol">=</a> <a id="1609" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a>
  <a id="1615" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1619" class="Symbol">(</a><a id="1620" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1624" class="Symbol">(</a><a id="1625" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1629" class="Symbol">(</a><a id="1630" href="graph-theory.directed-graphs.html#1365" class="Function">Graph-to-Graph&#39;</a> <a id="1646" href="graph-theory.directed-graphs.html#1646" class="Bound">G</a><a id="1647" class="Symbol">)))</a> <a id="1651" class="Symbol">=</a> <a id="1653" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1657" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="1659" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a>

  <a id="equiv.Graph&#39;-to-Graph"></a><a id="1666" href="graph-theory.directed-graphs.html#1666" class="Function">Graph&#39;-to-Graph</a> <a id="1682" class="Symbol">:</a> <a id="1684" href="graph-theory.directed-graphs.html#821" class="Function">Graph&#39;</a> <a id="1691" href="graph-theory.directed-graphs.html#1322" class="Bound">l1</a> <a id="1694" href="graph-theory.directed-graphs.html#1325" class="Bound">l2</a> <a id="1697" class="Symbol">-&gt;</a> <a id="1700" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a> <a id="1706" href="graph-theory.directed-graphs.html#1322" class="Bound">l1</a> <a id="1709" class="Symbol">(</a><a id="1710" href="graph-theory.directed-graphs.html#1322" class="Bound">l1</a> <a id="1713" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1715" href="graph-theory.directed-graphs.html#1325" class="Bound">l2</a><a id="1717" class="Symbol">)</a>
  <a id="1721" href="graph-theory.directed-graphs.html#1666" class="Function">Graph&#39;-to-Graph</a> <a id="1737" class="Symbol">(</a><a id="1738" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1743" href="graph-theory.directed-graphs.html#1743" class="Bound">V</a> <a id="1745" class="Symbol">(</a><a id="1746" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1751" href="graph-theory.directed-graphs.html#1751" class="Bound">E</a> <a id="1753" class="Symbol">(</a><a id="1754" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1759" href="graph-theory.directed-graphs.html#1759" class="Bound">st</a> <a id="1762" href="graph-theory.directed-graphs.html#1762" class="Bound">tg</a><a id="1764" class="Symbol">)))</a>
    <a id="1772" class="Symbol">=</a> <a id="1774" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1779" href="graph-theory.directed-graphs.html#1743" class="Bound">V</a> <a id="1781" class="Symbol">λ</a> <a id="1783" href="graph-theory.directed-graphs.html#1783" class="Bound">x</a> <a id="1785" href="graph-theory.directed-graphs.html#1785" class="Bound">y</a> <a id="1787" class="Symbol">→</a> <a id="1789" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="1791" href="graph-theory.directed-graphs.html#1751" class="Bound">E</a> <a id="1793" class="Symbol">λ</a> <a id="1795" href="graph-theory.directed-graphs.html#1795" class="Bound">e</a> <a id="1797" class="Symbol">→</a> <a id="1799" class="Symbol">(</a><a id="1800" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1803" class="Symbol">(</a><a id="1804" href="graph-theory.directed-graphs.html#1759" class="Bound">st</a> <a id="1807" href="graph-theory.directed-graphs.html#1795" class="Bound">e</a><a id="1808" class="Symbol">)</a> <a id="1810" href="graph-theory.directed-graphs.html#1783" class="Bound">x</a><a id="1811" class="Symbol">)</a> <a id="1813" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">×</a> <a id="1815" class="Symbol">(</a><a id="1816" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1819" class="Symbol">(</a><a id="1820" href="graph-theory.directed-graphs.html#1762" class="Bound">tg</a> <a id="1823" href="graph-theory.directed-graphs.html#1795" class="Bound">e</a><a id="1824" class="Symbol">)</a> <a id="1826" href="graph-theory.directed-graphs.html#1785" class="Bound">y</a><a id="1827" class="Symbol">)</a>
</pre>
### Results

#### Equivalence between Graph definitions

The two definitions given above for directed graphs are equivalent. $\Sigma$-types preserve equivalences and a type family $A \to U$ is equivalent to $\sum_{(C : U)} C \to A$.
We use these lemmas in the following calculation ASDFASD:

\begin{equation}
\begin{split}
\sum_{(V\,:\,\mathcal{U})} (V \to V \to \mathcal{U}) & \simeq \sum_{(V\,:\,\mathcal{U})}
 (V \times V \to \mathcal{U}) \\
 &\simeq \sum_{(V,E\,:\,\mathcal{U})} (E \to (V \times V)) \\
&\simeq  \sum_{(V,E\,:\,\mathcal{U})} ((E \to V) \times (E \to V))
\end{split}
\end{equation}


<pre class="Agda"><a id="2441" class="Keyword">module</a> <a id="directed-graph-defs-equivalence"></a><a id="2448" href="graph-theory.directed-graphs.html#2448" class="Module">directed-graph-defs-equivalence</a>
  <a id="2482" class="Symbol">{</a><a id="2483" href="graph-theory.directed-graphs.html#2483" class="Bound">l1</a> <a id="2486" href="graph-theory.directed-graphs.html#2486" class="Bound">l2</a> <a id="2489" class="Symbol">:</a> <a id="2491" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2496" class="Symbol">}</a> <a id="2498" class="Keyword">where</a>
  <a id="2506" class="Comment">-- is-equiv-htpy-equiv</a>
  <a id="2531" class="Comment">-- Uses equiv-Fib</a>
  <a id="2551" class="Comment">-- universal-property-cartesian-product-types.lagda</a>
  <a id="2605" class="Comment">-- equiv.</a>

  <a id="2618" class="Comment">-- The canonical (optimal) map for the equivalence.</a>
  <a id="2672" class="Comment">-- Any other map is homotopic to the canonical map.</a>
  <a id="2726" class="Comment">--is-equi</a>
</pre>
#### The type of Graph forms a category

<pre class="Agda"><a id="2790" class="Comment">-- Show that Graph is pre-category</a>
<a id="2825" class="Comment">-- + iso corresponds to equiv.</a>
<a id="2856" class="Comment">-- Instance of</a>
</pre>
#### The type of Graph forms a Topos

<pre class="Agda"><a id="2922" class="Comment">-- Show that Graph is pre-category</a>
<a id="2957" class="Comment">-- + iso corresponds to equiv.</a>
<a id="2988" class="Comment">-- Instance of</a>
</pre>