# Morphisms of directed graphs

<pre class="Agda"><a id="41" class="Symbol">{-#</a> <a id="45" class="Keyword">OPTIONS</a> <a id="53" class="Pragma">--without-K</a> <a id="65" class="Pragma">--exact-split</a> <a id="79" class="Symbol">#-}</a>

<a id="84" class="Keyword">module</a> <a id="91" href="graph-theory.morphisms-directed-graphs.html" class="Module">graph-theory.morphisms-directed-graphs</a> <a id="130" class="Keyword">where</a>

<a id="137" class="Keyword">open</a> <a id="142" class="Keyword">import</a> <a id="149" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a> <a id="179" class="Keyword">using</a> <a id="185" class="Symbol">(</a><a id="186" href="foundation-core.contractible-types.html#992" class="Function">is-contr</a><a id="194" class="Symbol">;</a> <a id="196" href="foundation-core.contractible-types.html#3806" class="Function">is-contr-equiv&#39;</a><a id="211" class="Symbol">)</a>
<a id="213" class="Keyword">open</a> <a id="218" class="Keyword">import</a> <a id="225" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="257" class="Keyword">using</a> <a id="263" class="Symbol">(</a><a id="264" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="265" class="Symbol">;</a> <a id="267" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="271" class="Symbol">;</a> <a id="273" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="276" class="Symbol">;</a> <a id="278" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="281" class="Symbol">)</a>
<a id="283" class="Keyword">open</a> <a id="288" class="Keyword">import</a> <a id="295" href="foundation.equality-dependent-function-types.html" class="Module">foundation.equality-dependent-function-types</a> <a id="340" class="Keyword">using</a>
  <a id="348" class="Symbol">(</a> <a id="350" href="foundation.equality-dependent-function-types.html#1038" class="Function">is-contr-total-Eq-Π</a><a id="369" class="Symbol">)</a>
<a id="371" class="Keyword">open</a> <a id="376" class="Keyword">import</a> <a id="383" href="foundation.equivalences.html" class="Module">foundation.equivalences</a> <a id="407" class="Keyword">using</a> <a id="413" class="Symbol">(</a><a id="414" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a><a id="422" class="Symbol">;</a> <a id="424" href="foundation-core.equivalences.html#1607" class="Function Operator">_≃_</a><a id="427" class="Symbol">;</a> <a id="429" href="foundation-core.equivalences.html#4173" class="Function">map-inv-is-equiv</a><a id="445" class="Symbol">)</a>
<a id="447" class="Keyword">open</a> <a id="452" class="Keyword">import</a> <a id="459" href="foundation.functions.html" class="Module">foundation.functions</a> <a id="480" class="Keyword">using</a> <a id="486" class="Symbol">(</a><a id="487" href="foundation-core.functions.html#407" class="Function Operator">_∘_</a><a id="490" class="Symbol">;</a> <a id="492" href="foundation-core.functions.html#309" class="Function">id</a><a id="494" class="Symbol">)</a>
<a id="496" class="Keyword">open</a> <a id="501" class="Keyword">import</a> <a id="508" href="foundation.functoriality-dependent-function-types.html" class="Module">foundation.functoriality-dependent-function-types</a> <a id="558" class="Keyword">using</a>
  <a id="566" class="Symbol">(</a> <a id="568" href="foundation-core.functoriality-dependent-function-types.html#2248" class="Function">equiv-map-Π</a><a id="579" class="Symbol">)</a>
<a id="581" class="Keyword">open</a> <a id="586" class="Keyword">import</a> <a id="593" href="foundation.functoriality-dependent-pair-types.html" class="Module">foundation.functoriality-dependent-pair-types</a> <a id="639" class="Keyword">using</a> <a id="645" class="Symbol">(</a><a id="646" href="foundation-core.functoriality-dependent-pair-types.html#6804" class="Function">equiv-tot</a><a id="655" class="Symbol">)</a>
<a id="657" class="Keyword">open</a> <a id="662" class="Keyword">import</a> <a id="669" href="foundation.fundamental-theorem-of-identity-types.html" class="Module">foundation.fundamental-theorem-of-identity-types</a> <a id="718" class="Keyword">using</a>
  <a id="726" class="Symbol">(</a> <a id="728" href="foundation-core.fundamental-theorem-of-identity-types.html#1888" class="Function">fundamental-theorem-id</a><a id="750" class="Symbol">)</a>
<a id="752" class="Keyword">open</a> <a id="757" class="Keyword">import</a> <a id="764" href="foundation.homotopies.html" class="Module">foundation.homotopies</a> <a id="786" class="Keyword">using</a> <a id="792" class="Symbol">(</a><a id="793" href="foundation-core.homotopies.html#467" class="Function Operator">_~_</a><a id="796" class="Symbol">;</a> <a id="798" href="foundation-core.homotopies.html#632" class="Function">refl-htpy</a><a id="807" class="Symbol">;</a> <a id="809" href="foundation.homotopies.html#3137" class="Function">is-contr-total-htpy</a><a id="828" class="Symbol">)</a>
<a id="830" class="Keyword">open</a> <a id="835" class="Keyword">import</a> <a id="842" href="foundation.identity-types.html" class="Module">foundation.identity-types</a> <a id="868" class="Keyword">using</a> <a id="874" class="Symbol">(</a><a id="875" href="foundation-core.identity-types.html#641" class="Datatype">Id</a><a id="877" class="Symbol">;</a> <a id="879" href="foundation-core.identity-types.html#4583" class="Function">tr</a><a id="881" class="Symbol">;</a> <a id="883" href="foundation-core.identity-types.html#2853" class="Function">ap</a><a id="885" class="Symbol">;</a> <a id="887" href="foundation.identity-types.html#1931" class="Function">equiv-concat</a><a id="899" class="Symbol">;</a> <a id="901" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a><a id="905" class="Symbol">)</a>
<a id="907" class="Keyword">open</a> <a id="912" class="Keyword">import</a> <a id="919" href="foundation.structure-identity-principle.html" class="Module">foundation.structure-identity-principle</a> <a id="959" class="Keyword">using</a>
  <a id="967" class="Symbol">(</a> <a id="969" href="foundation.structure-identity-principle.html#1341" class="Function">is-contr-total-Eq-structure</a><a id="996" class="Symbol">)</a>
<a id="998" class="Keyword">open</a> <a id="1003" class="Keyword">import</a> <a id="1010" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="1037" class="Keyword">using</a> <a id="1043" class="Symbol">(</a><a id="1044" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1049" class="Symbol">;</a> <a id="1051" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="1053" class="Symbol">;</a> <a id="1055" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="1058" class="Symbol">;</a> <a id="1060" href="Agda.Primitive.html#780" class="Primitive">lsuc</a><a id="1064" class="Symbol">;</a> <a id="1066" href="Agda.Primitive.html#764" class="Primitive">lzero</a><a id="1071" class="Symbol">)</a>
<a id="1073" class="Keyword">open</a> <a id="1078" class="Keyword">import</a> <a id="1085" href="foundation.unordered-pairs.html" class="Module">foundation.unordered-pairs</a> <a id="1112" class="Keyword">using</a>
  <a id="1120" class="Symbol">(</a> <a id="1122" href="foundation.unordered-pairs.html#7759" class="Function">map-unordered-pair</a><a id="1140" class="Symbol">;</a> <a id="1142" href="foundation.unordered-pairs.html#8391" class="Function">htpy-unordered-pair</a><a id="1161" class="Symbol">;</a> <a id="1163" href="foundation.unordered-pairs.html#8712" class="Function">preserves-refl-htpy-unordered-pair</a><a id="1197" class="Symbol">)</a>

<a id="1200" class="Keyword">open</a> <a id="1205" class="Keyword">import</a> <a id="1212" href="graph-theory.directed-graphs.html" class="Module">graph-theory.directed-graphs</a> <a id="1241" class="Keyword">using</a>
  <a id="1249" class="Symbol">(</a> <a id="1251" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a><a id="1256" class="Symbol">;</a> <a id="1258" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a><a id="1270" class="Symbol">;</a> <a id="1272" href="graph-theory.directed-graphs.html#682" class="Function">edge-Graph</a><a id="1282" class="Symbol">)</a>
</pre>
## Definitions

### Morphisms graphs

<pre class="Agda"><a id="1335" class="Keyword">module</a> <a id="1342" href="graph-theory.morphisms-directed-graphs.html#1342" class="Module">_</a>
  <a id="1346" class="Symbol">{</a><a id="1347" href="graph-theory.morphisms-directed-graphs.html#1347" class="Bound">l1</a> <a id="1350" href="graph-theory.morphisms-directed-graphs.html#1350" class="Bound">l2</a> <a id="1353" href="graph-theory.morphisms-directed-graphs.html#1353" class="Bound">l3</a> <a id="1356" href="graph-theory.morphisms-directed-graphs.html#1356" class="Bound">l4</a> <a id="1359" class="Symbol">:</a> <a id="1361" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1366" class="Symbol">}</a>
  <a id="1370" class="Symbol">(</a><a id="1371" href="graph-theory.morphisms-directed-graphs.html#1371" class="Bound">G</a> <a id="1373" class="Symbol">:</a> <a id="1375" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a> <a id="1381" href="graph-theory.morphisms-directed-graphs.html#1347" class="Bound">l1</a> <a id="1384" href="graph-theory.morphisms-directed-graphs.html#1350" class="Bound">l2</a><a id="1386" class="Symbol">)</a> <a id="1388" class="Symbol">(</a><a id="1389" href="graph-theory.morphisms-directed-graphs.html#1389" class="Bound">H</a> <a id="1391" class="Symbol">:</a> <a id="1393" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a> <a id="1399" href="graph-theory.morphisms-directed-graphs.html#1353" class="Bound">l3</a> <a id="1402" href="graph-theory.morphisms-directed-graphs.html#1356" class="Bound">l4</a><a id="1404" class="Symbol">)</a>
  <a id="1408" class="Keyword">where</a>

  <a id="1417" href="graph-theory.morphisms-directed-graphs.html#1417" class="Function">hom-Graph</a> <a id="1427" class="Symbol">:</a> <a id="1429" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1432" class="Symbol">(</a><a id="1433" href="graph-theory.morphisms-directed-graphs.html#1347" class="Bound">l1</a> <a id="1436" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1438" href="graph-theory.morphisms-directed-graphs.html#1350" class="Bound">l2</a> <a id="1441" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1443" href="graph-theory.morphisms-directed-graphs.html#1353" class="Bound">l3</a> <a id="1446" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1448" href="graph-theory.morphisms-directed-graphs.html#1356" class="Bound">l4</a><a id="1450" class="Symbol">)</a>
  <a id="1454" href="graph-theory.morphisms-directed-graphs.html#1417" class="Function">hom-Graph</a> <a id="1464" class="Symbol">=</a>
    <a id="1470" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="1472" class="Symbol">(</a> <a id="1474" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="1487" href="graph-theory.morphisms-directed-graphs.html#1371" class="Bound">G</a> <a id="1489" class="Symbol">→</a> <a id="1491" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="1504" href="graph-theory.morphisms-directed-graphs.html#1389" class="Bound">H</a> <a id="1506" class="Symbol">)</a>
      <a id="1514" class="Symbol">λ</a> <a id="1516" href="graph-theory.morphisms-directed-graphs.html#1516" class="Bound">α</a> <a id="1518" class="Symbol">→</a> <a id="1520" class="Symbol">(</a><a id="1521" href="graph-theory.morphisms-directed-graphs.html#1521" class="Bound">x</a> <a id="1523" href="graph-theory.morphisms-directed-graphs.html#1523" class="Bound">y</a> <a id="1525" class="Symbol">:</a> <a id="1527" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="1540" href="graph-theory.morphisms-directed-graphs.html#1371" class="Bound">G</a><a id="1541" class="Symbol">)</a> <a id="1543" class="Symbol">→</a> <a id="1545" class="Symbol">(</a><a id="1546" href="graph-theory.morphisms-directed-graphs.html#1546" class="Bound">e</a> <a id="1548" class="Symbol">:</a> <a id="1550" href="graph-theory.directed-graphs.html#682" class="Function">edge-Graph</a> <a id="1561" href="graph-theory.morphisms-directed-graphs.html#1371" class="Bound">G</a> <a id="1563" href="graph-theory.morphisms-directed-graphs.html#1521" class="Bound">x</a> <a id="1565" href="graph-theory.morphisms-directed-graphs.html#1523" class="Bound">y</a><a id="1566" class="Symbol">)</a>
          <a id="1578" class="Symbol">→</a> <a id="1580" href="graph-theory.directed-graphs.html#682" class="Function">edge-Graph</a> <a id="1591" href="graph-theory.morphisms-directed-graphs.html#1389" class="Bound">H</a> <a id="1593" class="Symbol">(</a><a id="1594" href="graph-theory.morphisms-directed-graphs.html#1516" class="Bound">α</a> <a id="1596" href="graph-theory.morphisms-directed-graphs.html#1521" class="Bound">x</a><a id="1597" class="Symbol">)</a> <a id="1599" class="Symbol">(</a><a id="1600" href="graph-theory.morphisms-directed-graphs.html#1516" class="Bound">α</a> <a id="1602" href="graph-theory.morphisms-directed-graphs.html#1523" class="Bound">y</a><a id="1603" class="Symbol">)</a>

  <a id="1608" class="Keyword">module</a> <a id="1615" href="graph-theory.morphisms-directed-graphs.html#1615" class="Module">_</a> <a id="1617" class="Symbol">(</a><a id="1618" href="graph-theory.morphisms-directed-graphs.html#1618" class="Bound">f</a> <a id="1620" class="Symbol">:</a> <a id="1622" href="graph-theory.morphisms-directed-graphs.html#1417" class="Function">hom-Graph</a><a id="1631" class="Symbol">)</a> <a id="1633" class="Keyword">where</a>

    <a id="1644" href="graph-theory.morphisms-directed-graphs.html#1644" class="Function">vertex-hom-Graph</a> <a id="1661" class="Symbol">:</a> <a id="1663" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="1676" href="graph-theory.morphisms-directed-graphs.html#1371" class="Bound">G</a> <a id="1678" class="Symbol">→</a> <a id="1680" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="1693" href="graph-theory.morphisms-directed-graphs.html#1389" class="Bound">H</a>
    <a id="1699" href="graph-theory.morphisms-directed-graphs.html#1644" class="Function">vertex-hom-Graph</a> <a id="1716" class="Symbol">=</a> <a id="1718" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1722" href="graph-theory.morphisms-directed-graphs.html#1618" class="Bound">f</a>

    <a id="1729" href="graph-theory.morphisms-directed-graphs.html#1729" class="Function">edge-hom-Graph</a> <a id="1744" class="Symbol">:</a>
      <a id="1752" class="Symbol">(</a><a id="1753" href="graph-theory.morphisms-directed-graphs.html#1753" class="Bound">x</a> <a id="1755" href="graph-theory.morphisms-directed-graphs.html#1755" class="Bound">y</a> <a id="1757" class="Symbol">:</a> <a id="1759" href="graph-theory.directed-graphs.html#635" class="Function">vertex-Graph</a> <a id="1772" href="graph-theory.morphisms-directed-graphs.html#1371" class="Bound">G</a><a id="1773" class="Symbol">)</a> <a id="1775" class="Symbol">→</a>
      <a id="1783" class="Symbol">(</a><a id="1784" href="graph-theory.morphisms-directed-graphs.html#1784" class="Bound">e</a> <a id="1786" class="Symbol">:</a> <a id="1788" href="graph-theory.directed-graphs.html#682" class="Function">edge-Graph</a> <a id="1799" href="graph-theory.morphisms-directed-graphs.html#1371" class="Bound">G</a> <a id="1801" href="graph-theory.morphisms-directed-graphs.html#1753" class="Bound">x</a> <a id="1803" href="graph-theory.morphisms-directed-graphs.html#1755" class="Bound">y</a><a id="1804" class="Symbol">)</a> <a id="1806" class="Symbol">→</a>
      <a id="1814" href="graph-theory.directed-graphs.html#682" class="Function">edge-Graph</a> <a id="1825" href="graph-theory.morphisms-directed-graphs.html#1389" class="Bound">H</a> <a id="1827" class="Symbol">(</a><a id="1828" href="graph-theory.morphisms-directed-graphs.html#1644" class="Function">vertex-hom-Graph</a> <a id="1845" href="graph-theory.morphisms-directed-graphs.html#1753" class="Bound">x</a><a id="1846" class="Symbol">)</a> <a id="1848" class="Symbol">(</a><a id="1849" href="graph-theory.morphisms-directed-graphs.html#1644" class="Function">vertex-hom-Graph</a> <a id="1866" href="graph-theory.morphisms-directed-graphs.html#1755" class="Bound">y</a><a id="1867" class="Symbol">)</a>
    <a id="1873" href="graph-theory.morphisms-directed-graphs.html#1729" class="Function">edge-hom-Graph</a> <a id="1888" class="Symbol">=</a> <a id="1890" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1894" href="graph-theory.morphisms-directed-graphs.html#1618" class="Bound">f</a>
</pre>
### Composition of morphisms graphs

<pre class="Agda">
<a id="1947" class="Keyword">module</a> <a id="1954" href="graph-theory.morphisms-directed-graphs.html#1954" class="Module">_</a>
  <a id="1958" class="Symbol">{</a><a id="1959" href="graph-theory.morphisms-directed-graphs.html#1959" class="Bound">l1</a> <a id="1962" href="graph-theory.morphisms-directed-graphs.html#1962" class="Bound">l2</a> <a id="1965" href="graph-theory.morphisms-directed-graphs.html#1965" class="Bound">l3</a> <a id="1968" href="graph-theory.morphisms-directed-graphs.html#1968" class="Bound">l4</a> <a id="1971" href="graph-theory.morphisms-directed-graphs.html#1971" class="Bound">l5</a> <a id="1974" href="graph-theory.morphisms-directed-graphs.html#1974" class="Bound">l6</a> <a id="1977" class="Symbol">:</a> <a id="1979" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1984" class="Symbol">}</a>
  <a id="1988" class="Symbol">(</a><a id="1989" href="graph-theory.morphisms-directed-graphs.html#1989" class="Bound">G</a> <a id="1991" class="Symbol">:</a> <a id="1993" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a> <a id="1999" href="graph-theory.morphisms-directed-graphs.html#1959" class="Bound">l1</a> <a id="2002" href="graph-theory.morphisms-directed-graphs.html#1962" class="Bound">l2</a><a id="2004" class="Symbol">)</a> <a id="2006" class="Symbol">(</a><a id="2007" href="graph-theory.morphisms-directed-graphs.html#2007" class="Bound">H</a> <a id="2009" class="Symbol">:</a> <a id="2011" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a> <a id="2017" href="graph-theory.morphisms-directed-graphs.html#1965" class="Bound">l3</a> <a id="2020" href="graph-theory.morphisms-directed-graphs.html#1968" class="Bound">l4</a><a id="2022" class="Symbol">)</a>
  <a id="2026" class="Symbol">(</a><a id="2027" href="graph-theory.morphisms-directed-graphs.html#2027" class="Bound">K</a> <a id="2029" class="Symbol">:</a> <a id="2031" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a> <a id="2037" href="graph-theory.morphisms-directed-graphs.html#1971" class="Bound">l5</a> <a id="2040" href="graph-theory.morphisms-directed-graphs.html#1974" class="Bound">l6</a><a id="2042" class="Symbol">)</a>
  <a id="2046" class="Keyword">where</a>

  <a id="2055" href="graph-theory.morphisms-directed-graphs.html#2055" class="Function">comp-hom-Graph</a> <a id="2070" class="Symbol">:</a>
    <a id="2076" href="graph-theory.morphisms-directed-graphs.html#1417" class="Function">hom-Graph</a> <a id="2086" href="graph-theory.morphisms-directed-graphs.html#2007" class="Bound">H</a> <a id="2088" href="graph-theory.morphisms-directed-graphs.html#2027" class="Bound">K</a> <a id="2090" class="Symbol">→</a> <a id="2092" href="graph-theory.morphisms-directed-graphs.html#1417" class="Function">hom-Graph</a> <a id="2102" href="graph-theory.morphisms-directed-graphs.html#1989" class="Bound">G</a> <a id="2104" href="graph-theory.morphisms-directed-graphs.html#2007" class="Bound">H</a> <a id="2106" class="Symbol">→</a>
    <a id="2112" href="graph-theory.morphisms-directed-graphs.html#1417" class="Function">hom-Graph</a> <a id="2122" href="graph-theory.morphisms-directed-graphs.html#1989" class="Bound">G</a> <a id="2124" href="graph-theory.morphisms-directed-graphs.html#2027" class="Bound">K</a>
  <a id="2128" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="2132" class="Symbol">(</a><a id="2133" href="graph-theory.morphisms-directed-graphs.html#2055" class="Function">comp-hom-Graph</a> <a id="2148" href="graph-theory.morphisms-directed-graphs.html#2148" class="Bound">g</a> <a id="2150" href="graph-theory.morphisms-directed-graphs.html#2150" class="Bound">f</a><a id="2151" class="Symbol">)</a> <a id="2153" class="Symbol">=</a> <a id="2155" class="Symbol">(</a><a id="2156" href="graph-theory.morphisms-directed-graphs.html#1644" class="Function">vertex-hom-Graph</a> <a id="2173" href="graph-theory.morphisms-directed-graphs.html#2007" class="Bound">H</a> <a id="2175" href="graph-theory.morphisms-directed-graphs.html#2027" class="Bound">K</a> <a id="2177" href="graph-theory.morphisms-directed-graphs.html#2148" class="Bound">g</a><a id="2178" class="Symbol">)</a> <a id="2180" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="2182" class="Symbol">(</a><a id="2183" href="graph-theory.morphisms-directed-graphs.html#1644" class="Function">vertex-hom-Graph</a> <a id="2200" href="graph-theory.morphisms-directed-graphs.html#1989" class="Bound">G</a> <a id="2202" href="graph-theory.morphisms-directed-graphs.html#2007" class="Bound">H</a> <a id="2204" href="graph-theory.morphisms-directed-graphs.html#2150" class="Bound">f</a><a id="2205" class="Symbol">)</a>
  <a id="2209" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="2213" class="Symbol">(</a><a id="2214" href="graph-theory.morphisms-directed-graphs.html#2055" class="Function">comp-hom-Graph</a> <a id="2229" href="graph-theory.morphisms-directed-graphs.html#2229" class="Bound">g</a> <a id="2231" href="graph-theory.morphisms-directed-graphs.html#2231" class="Bound">f</a><a id="2232" class="Symbol">)</a> <a id="2234" class="Symbol">=</a> <a id="2236" class="Symbol">λ</a> <a id="2238" href="graph-theory.morphisms-directed-graphs.html#2238" class="Bound">x</a> <a id="2240" href="graph-theory.morphisms-directed-graphs.html#2240" class="Bound">y</a> <a id="2242" href="graph-theory.morphisms-directed-graphs.html#2242" class="Bound">e</a> <a id="2244" class="Symbol">→</a> <a id="2246" class="Symbol">(</a><a id="2247" href="graph-theory.morphisms-directed-graphs.html#1729" class="Function">edge-hom-Graph</a> <a id="2262" href="graph-theory.morphisms-directed-graphs.html#2007" class="Bound">H</a> <a id="2264" href="graph-theory.morphisms-directed-graphs.html#2027" class="Bound">K</a> <a id="2266" href="graph-theory.morphisms-directed-graphs.html#2229" class="Bound">g</a><a id="2267" class="Symbol">)</a> <a id="2269" class="Symbol">(</a><a id="2270" href="graph-theory.morphisms-directed-graphs.html#2305" class="Function">α</a> <a id="2272" href="graph-theory.morphisms-directed-graphs.html#2238" class="Bound">x</a><a id="2273" class="Symbol">)</a> <a id="2275" class="Symbol">(</a><a id="2276" href="graph-theory.morphisms-directed-graphs.html#2305" class="Function">α</a> <a id="2278" href="graph-theory.morphisms-directed-graphs.html#2240" class="Bound">y</a><a id="2279" class="Symbol">)</a> <a id="2281" class="Symbol">(</a><a id="2282" href="graph-theory.morphisms-directed-graphs.html#2336" class="Function">β</a> <a id="2284" href="graph-theory.morphisms-directed-graphs.html#2238" class="Bound">x</a> <a id="2286" href="graph-theory.morphisms-directed-graphs.html#2240" class="Bound">y</a> <a id="2288" href="graph-theory.morphisms-directed-graphs.html#2242" class="Bound">e</a><a id="2289" class="Symbol">)</a>
    <a id="2295" class="Keyword">where</a>
    <a id="2305" href="graph-theory.morphisms-directed-graphs.html#2305" class="Function">α</a> <a id="2307" class="Symbol">=</a> <a id="2309" href="graph-theory.morphisms-directed-graphs.html#1644" class="Function">vertex-hom-Graph</a> <a id="2326" href="graph-theory.morphisms-directed-graphs.html#1989" class="Bound">G</a> <a id="2328" href="graph-theory.morphisms-directed-graphs.html#2007" class="Bound">H</a> <a id="2330" href="graph-theory.morphisms-directed-graphs.html#2231" class="Bound">f</a>
    <a id="2336" href="graph-theory.morphisms-directed-graphs.html#2336" class="Function">β</a> <a id="2338" class="Symbol">=</a> <a id="2340" href="graph-theory.morphisms-directed-graphs.html#1729" class="Function">edge-hom-Graph</a> <a id="2355" href="graph-theory.morphisms-directed-graphs.html#1989" class="Bound">G</a> <a id="2357" href="graph-theory.morphisms-directed-graphs.html#2007" class="Bound">H</a> <a id="2359" href="graph-theory.morphisms-directed-graphs.html#2231" class="Bound">f</a>
</pre>
### Identity morphisms graphs

<pre class="Agda"><a id="2405" class="Keyword">module</a> <a id="2412" href="graph-theory.morphisms-directed-graphs.html#2412" class="Module">_</a>
  <a id="2416" class="Symbol">{</a><a id="2417" href="graph-theory.morphisms-directed-graphs.html#2417" class="Bound">l1</a> <a id="2420" href="graph-theory.morphisms-directed-graphs.html#2420" class="Bound">l2</a> <a id="2423" class="Symbol">:</a> <a id="2425" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2430" class="Symbol">}</a> <a id="2432" class="Symbol">(</a><a id="2433" href="graph-theory.morphisms-directed-graphs.html#2433" class="Bound">G</a> <a id="2435" class="Symbol">:</a> <a id="2437" href="graph-theory.directed-graphs.html#483" class="Function">Graph</a> <a id="2443" href="graph-theory.morphisms-directed-graphs.html#2417" class="Bound">l1</a> <a id="2446" href="graph-theory.morphisms-directed-graphs.html#2420" class="Bound">l2</a><a id="2448" class="Symbol">)</a>
  <a id="2452" class="Keyword">where</a>

  <a id="2461" href="graph-theory.morphisms-directed-graphs.html#2461" class="Function">id-hom-Graph</a> <a id="2474" class="Symbol">:</a> <a id="2476" href="graph-theory.morphisms-directed-graphs.html#1417" class="Function">hom-Graph</a> <a id="2486" href="graph-theory.morphisms-directed-graphs.html#2433" class="Bound">G</a> <a id="2488" href="graph-theory.morphisms-directed-graphs.html#2433" class="Bound">G</a>
  <a id="2492" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="2496" href="graph-theory.morphisms-directed-graphs.html#2461" class="Function">id-hom-Graph</a> <a id="2509" class="Symbol">=</a> <a id="2511" href="foundation-core.functions.html#309" class="Function">id</a>
  <a id="2516" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="2520" href="graph-theory.morphisms-directed-graphs.html#2461" class="Function">id-hom-Graph</a> <a id="2533" class="Symbol">_</a> <a id="2535" class="Symbol">_</a> <a id="2537" class="Symbol">=</a> <a id="2539" href="foundation-core.functions.html#309" class="Function">id</a>
</pre>

## Properties

### Characterizing the identity type of morphisms graphs

<pre class="Agda"><a id="2629" class="Comment">{-
module _
  {l1 l2 l3 l4 : Level}
  (G : Graph l1 l2) (H : Graph l3 l4)
  where

  htpy-hom-Graph :
    (f g : hom-Graph G H) → UU (lsuc lzero ⊔ l1 ⊔ l2 ⊔ l3 ⊔ l4)
  htpy-hom-Graph f g =
    Σ ( vertex-hom-Graph G H f ~ vertex-hom-Graph G H g)
      ( λ α →
        ( p : unordered-pair-vertices-Graph G) →
        ( e : edge-Graph G p) →
        Id ( tr
             ( edge-Graph H)
             ( htpy-unordered-pair α p)
             ( edge-hom-Graph G H f p e))
           ( edge-hom-Graph G H g p e))

  refl-htpy-hom-Graph :
    (f : hom-Graph G H) → htpy-hom-Graph f f
  pr1 (refl-htpy-hom-Graph f) = refl-htpy
  pr2 (refl-htpy-hom-Graph f) p e =
    ap ( λ t →
         tr (edge-Graph H) t (edge-hom-Graph G H f p e))
       ( preserves-refl-htpy-unordered-pair
         ( vertex-hom-Graph G H f) p)

  htpy-eq-hom-Graph :
    (f g : hom-Graph G H) → Id f g → htpy-hom-Graph f g
  htpy-eq-hom-Graph f .f refl = refl-htpy-hom-Graph f

  abstract
    is-contr-total-htpy-hom-Graph :
      (f : hom-Graph G H) →
      is-contr (Σ (hom-Graph G H) (htpy-hom-Graph f))
    is-contr-total-htpy-hom-Graph f =
      is-contr-total-Eq-structure
        ( λ gV gE α →
          ( p : unordered-pair-vertices-Graph G) →
          ( e : edge-Graph G p) →
          Id ( tr
               ( edge-Graph H)
               ( htpy-unordered-pair α p)
               ( edge-hom-Graph G H f p e))
             ( gE p e))
        ( is-contr-total-htpy (vertex-hom-Graph G H f))
        ( pair (vertex-hom-Graph G H f) refl-htpy)
        ( is-contr-equiv&#39;
          ( Σ ( (p : unordered-pair-vertices-Graph G) →
                edge-Graph G p →
                edge-Graph H
                  ( unordered-pair-vertices-hom-Graph G H f p))
              ( λ gE →
                (p : unordered-pair-vertices-Graph G) →
                (e : edge-Graph G p) →
                Id (edge-hom-Graph G H f p e) (gE p e)))
          ( equiv-tot
            ( λ gE →
              equiv-map-Π
                ( λ p →
                  equiv-map-Π
                    ( λ e →
                      equiv-concat
                        ( pr2 (refl-htpy-hom-Graph f) p e)
                        ( gE p e)))))
          ( is-contr-total-Eq-Π
            ( λ p gE →
              ( e : edge-Graph G p) →
              Id (edge-hom-Graph G H f p e) (gE e))
            ( λ p → is-contr-total-htpy (edge-hom-Graph G H f p))))

  is-equiv-htpy-eq-hom-Graph :
    (f g : hom-Graph G H) →
    is-equiv (htpy-eq-hom-Graph f g)
  is-equiv-htpy-eq-hom-Graph f =
    fundamental-theorem-id f
      ( refl-htpy-hom-Graph f)
      ( is-contr-total-htpy-hom-Graph f)
      ( htpy-eq-hom-Graph f)

  extensionality-hom-Graph :
    (f g : hom-Graph G H) → Id f g ≃ htpy-hom-Graph f g
  pr1 (extensionality-hom-Graph f g) =
    htpy-eq-hom-Graph f g
  pr2 (extensionality-hom-Graph f g) =
    is-equiv-htpy-eq-hom-Graph f g

  eq-htpy-hom-Graph :
    (f g : hom-Graph G H) → htpy-hom-Graph f g → Id f g
  eq-htpy-hom-Graph f g =
    map-inv-is-equiv (is-equiv-htpy-eq-hom-Graph f g)
-}</a>
</pre>