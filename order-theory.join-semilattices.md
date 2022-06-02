# Join-semilattices

<pre class="Agda"><a id="30" class="Symbol">{-#</a> <a id="34" class="Keyword">OPTIONS</a> <a id="42" class="Pragma">--without-K</a> <a id="54" class="Pragma">--exact-split</a> <a id="68" class="Symbol">#-}</a>

<a id="73" class="Keyword">module</a> <a id="80" href="order-theory.join-semilattices.html" class="Module">order-theory.join-semilattices</a> <a id="111" class="Keyword">where</a>

<a id="118" class="Keyword">open</a> <a id="123" class="Keyword">import</a> <a id="130" href="foundation.cartesian-product-types.html" class="Module">foundation.cartesian-product-types</a> <a id="165" class="Keyword">using</a> <a id="171" class="Symbol">(</a><a id="172" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">_×_</a><a id="175" class="Symbol">)</a>
<a id="177" class="Keyword">open</a> <a id="182" class="Keyword">import</a> <a id="189" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="221" class="Keyword">using</a> <a id="227" class="Symbol">(</a><a id="228" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="229" class="Symbol">;</a> <a id="231" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="235" class="Symbol">;</a> <a id="237" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="240" class="Symbol">;</a> <a id="242" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="245" class="Symbol">)</a>
<a id="247" class="Keyword">open</a> <a id="252" class="Keyword">import</a> <a id="259" href="foundation.identity-types.html" class="Module">foundation.identity-types</a> <a id="285" class="Keyword">using</a> <a id="291" class="Symbol">(</a><a id="292" href="foundation-core.identity-types.html#641" class="Datatype">Id</a><a id="294" class="Symbol">)</a>
<a id="296" class="Keyword">open</a> <a id="301" class="Keyword">import</a> <a id="308" href="foundation.propositions.html" class="Module">foundation.propositions</a> <a id="332" class="Keyword">using</a>
  <a id="340" class="Symbol">(</a> <a id="342" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a><a id="349" class="Symbol">;</a> <a id="351" href="foundation-core.propositions.html#6683" class="Function">Π-Prop</a><a id="357" class="Symbol">;</a> <a id="359" href="foundation-core.propositions.html#1482" class="Function">type-Prop</a><a id="368" class="Symbol">;</a> <a id="370" href="foundation-core.propositions.html#1295" class="Function">is-prop</a><a id="377" class="Symbol">;</a> <a id="379" href="foundation-core.propositions.html#1549" class="Function">is-prop-type-Prop</a><a id="396" class="Symbol">)</a>
<a id="398" class="Keyword">open</a> <a id="403" class="Keyword">import</a> <a id="410" href="foundation.sets.html" class="Module">foundation.sets</a> <a id="426" class="Keyword">using</a> <a id="432" class="Symbol">(</a><a id="433" href="foundation-core.sets.html#1099" class="Function">is-set</a><a id="439" class="Symbol">;</a> <a id="441" href="foundation-core.sets.html#1177" class="Function">UU-Set</a><a id="447" class="Symbol">)</a>
<a id="449" class="Keyword">open</a> <a id="454" class="Keyword">import</a> <a id="461" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="488" class="Keyword">using</a> <a id="494" class="Symbol">(</a><a id="495" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="500" class="Symbol">;</a> <a id="502" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="504" class="Symbol">;</a> <a id="506" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="509" class="Symbol">;</a> <a id="511" href="Agda.Primitive.html#780" class="Primitive">lsuc</a><a id="515" class="Symbol">)</a>

<a id="518" class="Keyword">open</a> <a id="523" class="Keyword">import</a> <a id="530" href="group-theory.semigroups.html" class="Module">group-theory.semigroups</a> <a id="554" class="Keyword">using</a>
  <a id="562" class="Symbol">(</a> <a id="564" href="group-theory.semigroups.html#737" class="Function">Semigroup</a><a id="573" class="Symbol">;</a> <a id="575" href="group-theory.semigroups.html#933" class="Function">type-Semigroup</a><a id="589" class="Symbol">;</a> <a id="591" href="group-theory.semigroups.html#1215" class="Function">mul-Semigroup</a><a id="604" class="Symbol">)</a>

<a id="607" class="Keyword">open</a> <a id="612" class="Keyword">import</a> <a id="619" href="order-theory.least-upper-bounds-posets.html" class="Module">order-theory.least-upper-bounds-posets</a> <a id="658" class="Keyword">using</a>
  <a id="666" class="Symbol">(</a> <a id="668" href="order-theory.least-upper-bounds-posets.html#3317" class="Function">has-least-binary-upper-bound-poset-Prop</a><a id="707" class="Symbol">)</a>
<a id="709" class="Keyword">open</a> <a id="714" class="Keyword">import</a> <a id="721" href="order-theory.posets.html" class="Module">order-theory.posets</a> <a id="741" class="Keyword">using</a>
  <a id="749" class="Symbol">(</a> <a id="751" href="order-theory.posets.html#731" class="Function">Poset</a><a id="756" class="Symbol">;</a> <a id="758" href="order-theory.posets.html#1145" class="Function">element-Poset</a><a id="771" class="Symbol">;</a> <a id="773" href="order-theory.posets.html#1194" class="Function">leq-poset-Prop</a><a id="787" class="Symbol">;</a> <a id="789" href="order-theory.posets.html#1280" class="Function">leq-Poset</a><a id="798" class="Symbol">;</a> <a id="800" href="order-theory.posets.html#1375" class="Function">is-prop-leq-Poset</a><a id="817" class="Symbol">;</a>
    <a id="823" href="order-theory.posets.html#1511" class="Function">refl-leq-Poset</a><a id="837" class="Symbol">;</a> <a id="839" href="order-theory.posets.html#1983" class="Function">antisymmetric-leq-Poset</a><a id="862" class="Symbol">;</a> <a id="864" href="order-theory.posets.html#1610" class="Function">transitive-leq-Poset</a><a id="884" class="Symbol">;</a>
    <a id="890" href="order-theory.posets.html#2125" class="Function">is-set-element-Poset</a><a id="910" class="Symbol">;</a> <a id="912" href="order-theory.posets.html#2464" class="Function">element-poset-Set</a><a id="929" class="Symbol">)</a>
</pre>
## Idea

A join-semilattice is a poset in which every pair of elements has a least binary-upper bound.

## Definitions

### Order theoretic join-semilattices

<pre class="Agda"><a id="1103" class="Keyword">module</a> <a id="1110" href="order-theory.join-semilattices.html#1110" class="Module">_</a>
  <a id="1114" class="Symbol">{</a><a id="1115" href="order-theory.join-semilattices.html#1115" class="Bound">l1</a> <a id="1118" href="order-theory.join-semilattices.html#1118" class="Bound">l2</a> <a id="1121" class="Symbol">:</a> <a id="1123" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1128" class="Symbol">}</a> <a id="1130" class="Symbol">(</a><a id="1131" href="order-theory.join-semilattices.html#1131" class="Bound">P</a> <a id="1133" class="Symbol">:</a> <a id="1135" href="order-theory.posets.html#731" class="Function">Poset</a> <a id="1141" href="order-theory.join-semilattices.html#1115" class="Bound">l1</a> <a id="1144" href="order-theory.join-semilattices.html#1118" class="Bound">l2</a><a id="1146" class="Symbol">)</a>
  <a id="1150" class="Keyword">where</a>

  <a id="1159" href="order-theory.join-semilattices.html#1159" class="Function">is-join-semilattice-poset-Prop</a> <a id="1190" class="Symbol">:</a> <a id="1192" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a> <a id="1200" class="Symbol">(</a><a id="1201" href="order-theory.join-semilattices.html#1115" class="Bound">l1</a> <a id="1204" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1206" href="order-theory.join-semilattices.html#1118" class="Bound">l2</a><a id="1208" class="Symbol">)</a>
  <a id="1212" href="order-theory.join-semilattices.html#1159" class="Function">is-join-semilattice-poset-Prop</a> <a id="1243" class="Symbol">=</a>
    <a id="1249" href="foundation-core.propositions.html#6683" class="Function">Π-Prop</a>
      <a id="1262" class="Symbol">(</a> <a id="1264" href="order-theory.posets.html#1145" class="Function">element-Poset</a> <a id="1278" href="order-theory.join-semilattices.html#1131" class="Bound">P</a><a id="1279" class="Symbol">)</a>
      <a id="1287" class="Symbol">(</a> <a id="1289" class="Symbol">λ</a> <a id="1291" href="order-theory.join-semilattices.html#1291" class="Bound">x</a> <a id="1293" class="Symbol">→</a>
        <a id="1303" href="foundation-core.propositions.html#6683" class="Function">Π-Prop</a>
          <a id="1320" class="Symbol">(</a> <a id="1322" href="order-theory.posets.html#1145" class="Function">element-Poset</a> <a id="1336" href="order-theory.join-semilattices.html#1131" class="Bound">P</a><a id="1337" class="Symbol">)</a>
          <a id="1349" class="Symbol">(</a> <a id="1351" href="order-theory.least-upper-bounds-posets.html#3317" class="Function">has-least-binary-upper-bound-poset-Prop</a> <a id="1391" href="order-theory.join-semilattices.html#1131" class="Bound">P</a> <a id="1393" href="order-theory.join-semilattices.html#1291" class="Bound">x</a><a id="1394" class="Symbol">))</a>

  <a id="1400" href="order-theory.join-semilattices.html#1400" class="Function">is-join-semilattice-Poset</a> <a id="1426" class="Symbol">:</a> <a id="1428" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1431" class="Symbol">(</a><a id="1432" href="order-theory.join-semilattices.html#1115" class="Bound">l1</a> <a id="1435" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1437" href="order-theory.join-semilattices.html#1118" class="Bound">l2</a><a id="1439" class="Symbol">)</a>
  <a id="1443" href="order-theory.join-semilattices.html#1400" class="Function">is-join-semilattice-Poset</a> <a id="1469" class="Symbol">=</a> <a id="1471" href="foundation-core.propositions.html#1482" class="Function">type-Prop</a> <a id="1481" href="order-theory.join-semilattices.html#1159" class="Function">is-join-semilattice-poset-Prop</a>

  <a id="1515" href="order-theory.join-semilattices.html#1515" class="Function">is-prop-is-join-semilattice-Poset</a> <a id="1549" class="Symbol">:</a>
    <a id="1555" href="foundation-core.propositions.html#1295" class="Function">is-prop</a> <a id="1563" href="order-theory.join-semilattices.html#1400" class="Function">is-join-semilattice-Poset</a>
  <a id="1591" href="order-theory.join-semilattices.html#1515" class="Function">is-prop-is-join-semilattice-Poset</a> <a id="1625" class="Symbol">=</a>
    <a id="1631" href="foundation-core.propositions.html#1549" class="Function">is-prop-type-Prop</a> <a id="1649" href="order-theory.join-semilattices.html#1159" class="Function">is-join-semilattice-poset-Prop</a>

<a id="Join-Semilattice"></a><a id="1681" href="order-theory.join-semilattices.html#1681" class="Function">Join-Semilattice</a> <a id="1698" class="Symbol">:</a> <a id="1700" class="Symbol">(</a><a id="1701" href="order-theory.join-semilattices.html#1701" class="Bound">l1</a> <a id="1704" href="order-theory.join-semilattices.html#1704" class="Bound">l2</a> <a id="1707" class="Symbol">:</a> <a id="1709" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1714" class="Symbol">)</a> <a id="1716" class="Symbol">→</a> <a id="1718" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1721" class="Symbol">(</a><a id="1722" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="1727" href="order-theory.join-semilattices.html#1701" class="Bound">l1</a> <a id="1730" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1732" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="1737" href="order-theory.join-semilattices.html#1704" class="Bound">l2</a><a id="1739" class="Symbol">)</a>
<a id="1741" href="order-theory.join-semilattices.html#1681" class="Function">Join-Semilattice</a> <a id="1758" href="order-theory.join-semilattices.html#1758" class="Bound">l1</a> <a id="1761" href="order-theory.join-semilattices.html#1761" class="Bound">l2</a> <a id="1764" class="Symbol">=</a> <a id="1766" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="1768" class="Symbol">(</a><a id="1769" href="order-theory.posets.html#731" class="Function">Poset</a> <a id="1775" href="order-theory.join-semilattices.html#1758" class="Bound">l1</a> <a id="1778" href="order-theory.join-semilattices.html#1761" class="Bound">l2</a><a id="1780" class="Symbol">)</a> <a id="1782" href="order-theory.join-semilattices.html#1400" class="Function">is-join-semilattice-Poset</a>

<a id="1809" class="Keyword">module</a> <a id="1816" href="order-theory.join-semilattices.html#1816" class="Module">_</a>
  <a id="1820" class="Symbol">{</a><a id="1821" href="order-theory.join-semilattices.html#1821" class="Bound">l1</a> <a id="1824" href="order-theory.join-semilattices.html#1824" class="Bound">l2</a> <a id="1827" class="Symbol">:</a> <a id="1829" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1834" class="Symbol">}</a> <a id="1836" class="Symbol">(</a><a id="1837" href="order-theory.join-semilattices.html#1837" class="Bound">A</a> <a id="1839" class="Symbol">:</a> <a id="1841" href="order-theory.join-semilattices.html#1681" class="Function">Join-Semilattice</a> <a id="1858" href="order-theory.join-semilattices.html#1821" class="Bound">l1</a> <a id="1861" href="order-theory.join-semilattices.html#1824" class="Bound">l2</a><a id="1863" class="Symbol">)</a>
  <a id="1867" class="Keyword">where</a>

  <a id="1876" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a> <a id="1899" class="Symbol">:</a> <a id="1901" href="order-theory.posets.html#731" class="Function">Poset</a> <a id="1907" href="order-theory.join-semilattices.html#1821" class="Bound">l1</a> <a id="1910" href="order-theory.join-semilattices.html#1824" class="Bound">l2</a>
  <a id="1915" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a> <a id="1938" class="Symbol">=</a> <a id="1940" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1944" href="order-theory.join-semilattices.html#1837" class="Bound">A</a>

  <a id="1949" href="order-theory.join-semilattices.html#1949" class="Function">element-Join-Semilattice</a> <a id="1974" class="Symbol">:</a> <a id="1976" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1979" href="order-theory.join-semilattices.html#1821" class="Bound">l1</a>
  <a id="1984" href="order-theory.join-semilattices.html#1949" class="Function">element-Join-Semilattice</a> <a id="2009" class="Symbol">=</a> <a id="2011" href="order-theory.posets.html#1145" class="Function">element-Poset</a> <a id="2025" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a>

  <a id="2051" href="order-theory.join-semilattices.html#2051" class="Function">leq-join-semilattice-Prop</a> <a id="2077" class="Symbol">:</a> <a id="2079" class="Symbol">(</a><a id="2080" href="order-theory.join-semilattices.html#2080" class="Bound">x</a> <a id="2082" href="order-theory.join-semilattices.html#2082" class="Bound">y</a> <a id="2084" class="Symbol">:</a> <a id="2086" href="order-theory.join-semilattices.html#1949" class="Function">element-Join-Semilattice</a><a id="2110" class="Symbol">)</a> <a id="2112" class="Symbol">→</a> <a id="2114" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a> <a id="2122" href="order-theory.join-semilattices.html#1824" class="Bound">l2</a>
  <a id="2127" href="order-theory.join-semilattices.html#2051" class="Function">leq-join-semilattice-Prop</a> <a id="2153" class="Symbol">=</a> <a id="2155" href="order-theory.posets.html#1194" class="Function">leq-poset-Prop</a> <a id="2170" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a>

  <a id="2196" href="order-theory.join-semilattices.html#2196" class="Function">leq-Join-Semilattice</a> <a id="2217" class="Symbol">:</a> <a id="2219" class="Symbol">(</a><a id="2220" href="order-theory.join-semilattices.html#2220" class="Bound">x</a> <a id="2222" href="order-theory.join-semilattices.html#2222" class="Bound">y</a> <a id="2224" class="Symbol">:</a> <a id="2226" href="order-theory.join-semilattices.html#1949" class="Function">element-Join-Semilattice</a><a id="2250" class="Symbol">)</a> <a id="2252" class="Symbol">→</a> <a id="2254" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2257" href="order-theory.join-semilattices.html#1824" class="Bound">l2</a>
  <a id="2262" href="order-theory.join-semilattices.html#2196" class="Function">leq-Join-Semilattice</a> <a id="2283" class="Symbol">=</a> <a id="2285" href="order-theory.posets.html#1280" class="Function">leq-Poset</a> <a id="2295" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a>

  <a id="2321" href="order-theory.join-semilattices.html#2321" class="Function">is-prop-leq-Join-Semilattice</a> <a id="2350" class="Symbol">:</a>
    <a id="2356" class="Symbol">(</a><a id="2357" href="order-theory.join-semilattices.html#2357" class="Bound">x</a> <a id="2359" href="order-theory.join-semilattices.html#2359" class="Bound">y</a> <a id="2361" class="Symbol">:</a> <a id="2363" href="order-theory.join-semilattices.html#1949" class="Function">element-Join-Semilattice</a><a id="2387" class="Symbol">)</a> <a id="2389" class="Symbol">→</a> <a id="2391" href="foundation-core.propositions.html#1295" class="Function">is-prop</a> <a id="2399" class="Symbol">(</a><a id="2400" href="order-theory.join-semilattices.html#2196" class="Function">leq-Join-Semilattice</a> <a id="2421" href="order-theory.join-semilattices.html#2357" class="Bound">x</a> <a id="2423" href="order-theory.join-semilattices.html#2359" class="Bound">y</a><a id="2424" class="Symbol">)</a>
  <a id="2428" href="order-theory.join-semilattices.html#2321" class="Function">is-prop-leq-Join-Semilattice</a> <a id="2457" class="Symbol">=</a> <a id="2459" href="order-theory.posets.html#1375" class="Function">is-prop-leq-Poset</a> <a id="2477" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a>

  <a id="2503" href="order-theory.join-semilattices.html#2503" class="Function">refl-leq-Join-Semilattice</a> <a id="2529" class="Symbol">:</a>
    <a id="2535" class="Symbol">(</a><a id="2536" href="order-theory.join-semilattices.html#2536" class="Bound">x</a> <a id="2538" class="Symbol">:</a> <a id="2540" href="order-theory.join-semilattices.html#1949" class="Function">element-Join-Semilattice</a><a id="2564" class="Symbol">)</a> <a id="2566" class="Symbol">→</a> <a id="2568" href="order-theory.join-semilattices.html#2196" class="Function">leq-Join-Semilattice</a> <a id="2589" href="order-theory.join-semilattices.html#2536" class="Bound">x</a> <a id="2591" href="order-theory.join-semilattices.html#2536" class="Bound">x</a>
  <a id="2595" href="order-theory.join-semilattices.html#2503" class="Function">refl-leq-Join-Semilattice</a> <a id="2621" class="Symbol">=</a> <a id="2623" href="order-theory.posets.html#1511" class="Function">refl-leq-Poset</a> <a id="2638" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a>

  <a id="2664" href="order-theory.join-semilattices.html#2664" class="Function">antisymmetric-leq-Join-Semilattice</a> <a id="2699" class="Symbol">:</a>
    <a id="2705" class="Symbol">(</a><a id="2706" href="order-theory.join-semilattices.html#2706" class="Bound">x</a> <a id="2708" href="order-theory.join-semilattices.html#2708" class="Bound">y</a> <a id="2710" class="Symbol">:</a> <a id="2712" href="order-theory.join-semilattices.html#1949" class="Function">element-Join-Semilattice</a><a id="2736" class="Symbol">)</a> <a id="2738" class="Symbol">→</a>
    <a id="2744" href="order-theory.join-semilattices.html#2196" class="Function">leq-Join-Semilattice</a> <a id="2765" href="order-theory.join-semilattices.html#2706" class="Bound">x</a> <a id="2767" href="order-theory.join-semilattices.html#2708" class="Bound">y</a> <a id="2769" class="Symbol">→</a> <a id="2771" href="order-theory.join-semilattices.html#2196" class="Function">leq-Join-Semilattice</a> <a id="2792" href="order-theory.join-semilattices.html#2708" class="Bound">y</a> <a id="2794" href="order-theory.join-semilattices.html#2706" class="Bound">x</a> <a id="2796" class="Symbol">→</a> <a id="2798" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="2801" href="order-theory.join-semilattices.html#2706" class="Bound">x</a> <a id="2803" href="order-theory.join-semilattices.html#2708" class="Bound">y</a>
  <a id="2807" href="order-theory.join-semilattices.html#2664" class="Function">antisymmetric-leq-Join-Semilattice</a> <a id="2842" class="Symbol">=</a>
    <a id="2848" href="order-theory.posets.html#1983" class="Function">antisymmetric-leq-Poset</a> <a id="2872" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a>

  <a id="2898" href="order-theory.join-semilattices.html#2898" class="Function">transitive-leq-Join-Semilattice</a> <a id="2930" class="Symbol">:</a>
    <a id="2936" class="Symbol">(</a><a id="2937" href="order-theory.join-semilattices.html#2937" class="Bound">x</a> <a id="2939" href="order-theory.join-semilattices.html#2939" class="Bound">y</a> <a id="2941" href="order-theory.join-semilattices.html#2941" class="Bound">z</a> <a id="2943" class="Symbol">:</a> <a id="2945" href="order-theory.join-semilattices.html#1949" class="Function">element-Join-Semilattice</a><a id="2969" class="Symbol">)</a> <a id="2971" class="Symbol">→</a>
    <a id="2977" href="order-theory.join-semilattices.html#2196" class="Function">leq-Join-Semilattice</a> <a id="2998" href="order-theory.join-semilattices.html#2939" class="Bound">y</a> <a id="3000" href="order-theory.join-semilattices.html#2941" class="Bound">z</a> <a id="3002" class="Symbol">→</a> <a id="3004" href="order-theory.join-semilattices.html#2196" class="Function">leq-Join-Semilattice</a> <a id="3025" href="order-theory.join-semilattices.html#2937" class="Bound">x</a> <a id="3027" href="order-theory.join-semilattices.html#2939" class="Bound">y</a> <a id="3029" class="Symbol">→</a>
    <a id="3035" href="order-theory.join-semilattices.html#2196" class="Function">leq-Join-Semilattice</a> <a id="3056" href="order-theory.join-semilattices.html#2937" class="Bound">x</a> <a id="3058" href="order-theory.join-semilattices.html#2941" class="Bound">z</a>
  <a id="3062" href="order-theory.join-semilattices.html#2898" class="Function">transitive-leq-Join-Semilattice</a> <a id="3094" class="Symbol">=</a> <a id="3096" href="order-theory.posets.html#1610" class="Function">transitive-leq-Poset</a> <a id="3117" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a>

  <a id="3143" href="order-theory.join-semilattices.html#3143" class="Function">is-set-element-Join-Semilattice</a> <a id="3175" class="Symbol">:</a> <a id="3177" href="foundation-core.sets.html#1099" class="Function">is-set</a> <a id="3184" href="order-theory.join-semilattices.html#1949" class="Function">element-Join-Semilattice</a>
  <a id="3211" href="order-theory.join-semilattices.html#3143" class="Function">is-set-element-Join-Semilattice</a> <a id="3243" class="Symbol">=</a> <a id="3245" href="order-theory.posets.html#2125" class="Function">is-set-element-Poset</a> <a id="3266" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a>

  <a id="3292" href="order-theory.join-semilattices.html#3292" class="Function">element-join-semilattice-Set</a> <a id="3321" class="Symbol">:</a> <a id="3323" href="foundation-core.sets.html#1177" class="Function">UU-Set</a> <a id="3330" href="order-theory.join-semilattices.html#1821" class="Bound">l1</a>
  <a id="3335" href="order-theory.join-semilattices.html#3292" class="Function">element-join-semilattice-Set</a> <a id="3364" class="Symbol">=</a> <a id="3366" href="order-theory.posets.html#2464" class="Function">element-poset-Set</a> <a id="3384" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a>

  <a id="3410" href="order-theory.join-semilattices.html#3410" class="Function">is-join-semilattice-Join-Semilattice</a> <a id="3447" class="Symbol">:</a>
    <a id="3453" href="order-theory.join-semilattices.html#1400" class="Function">is-join-semilattice-Poset</a> <a id="3479" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a>
  <a id="3504" href="order-theory.join-semilattices.html#3410" class="Function">is-join-semilattice-Join-Semilattice</a> <a id="3541" class="Symbol">=</a> <a id="3543" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="3547" href="order-theory.join-semilattices.html#1837" class="Bound">A</a>

  <a id="3552" href="order-theory.join-semilattices.html#3552" class="Function">join-semilattice-Join-Semilattice</a> <a id="3586" class="Symbol">:</a> <a id="3588" href="order-theory.join-semilattices.html#1681" class="Function">Join-Semilattice</a> <a id="3605" href="order-theory.join-semilattices.html#1821" class="Bound">l1</a> <a id="3608" href="order-theory.join-semilattices.html#1824" class="Bound">l2</a>
  <a id="3613" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="3617" href="order-theory.join-semilattices.html#3552" class="Function">join-semilattice-Join-Semilattice</a> <a id="3651" class="Symbol">=</a> <a id="3653" href="order-theory.join-semilattices.html#1876" class="Function">poset-Join-Semilattice</a>
  <a id="3678" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="3682" href="order-theory.join-semilattices.html#3552" class="Function">join-semilattice-Join-Semilattice</a> <a id="3716" class="Symbol">=</a> <a id="3718" href="order-theory.join-semilattices.html#3410" class="Function">is-join-semilattice-Join-Semilattice</a>
</pre>
### Algebraic join-semilattices

<pre class="Agda"><a id="Algebraic-Join-Semilattice"></a><a id="3801" href="order-theory.join-semilattices.html#3801" class="Function">Algebraic-Join-Semilattice</a> <a id="3828" class="Symbol">:</a> <a id="3830" class="Symbol">(</a><a id="3831" href="order-theory.join-semilattices.html#3831" class="Bound">l</a> <a id="3833" class="Symbol">:</a> <a id="3835" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3840" class="Symbol">)</a> <a id="3842" class="Symbol">→</a> <a id="3844" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="3847" class="Symbol">(</a><a id="3848" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="3853" href="order-theory.join-semilattices.html#3831" class="Bound">l</a><a id="3854" class="Symbol">)</a>
<a id="3856" href="order-theory.join-semilattices.html#3801" class="Function">Algebraic-Join-Semilattice</a> <a id="3883" href="order-theory.join-semilattices.html#3883" class="Bound">l</a> <a id="3885" class="Symbol">=</a>
  <a id="3889" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="3891" class="Symbol">(</a> <a id="3893" href="group-theory.semigroups.html#737" class="Function">Semigroup</a> <a id="3903" href="order-theory.join-semilattices.html#3883" class="Bound">l</a><a id="3904" class="Symbol">)</a>
    <a id="3910" class="Symbol">(</a> <a id="3912" class="Symbol">λ</a> <a id="3914" href="order-theory.join-semilattices.html#3914" class="Bound">X</a> <a id="3916" class="Symbol">→</a>
      <a id="3924" class="Symbol">(</a> <a id="3926" class="Symbol">(</a><a id="3927" href="order-theory.join-semilattices.html#3927" class="Bound">x</a> <a id="3929" href="order-theory.join-semilattices.html#3929" class="Bound">y</a> <a id="3931" class="Symbol">:</a> <a id="3933" href="group-theory.semigroups.html#933" class="Function">type-Semigroup</a> <a id="3948" href="order-theory.join-semilattices.html#3914" class="Bound">X</a><a id="3949" class="Symbol">)</a> <a id="3951" class="Symbol">→</a>
        <a id="3961" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="3964" class="Symbol">(</a><a id="3965" href="group-theory.semigroups.html#1215" class="Function">mul-Semigroup</a> <a id="3979" href="order-theory.join-semilattices.html#3914" class="Bound">X</a> <a id="3981" href="order-theory.join-semilattices.html#3927" class="Bound">x</a> <a id="3983" href="order-theory.join-semilattices.html#3929" class="Bound">y</a><a id="3984" class="Symbol">)</a> <a id="3986" class="Symbol">(</a><a id="3987" href="group-theory.semigroups.html#1215" class="Function">mul-Semigroup</a> <a id="4001" href="order-theory.join-semilattices.html#3914" class="Bound">X</a> <a id="4003" href="order-theory.join-semilattices.html#3929" class="Bound">y</a> <a id="4005" href="order-theory.join-semilattices.html#3927" class="Bound">x</a><a id="4006" class="Symbol">))</a> <a id="4009" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">×</a>
      <a id="4017" class="Symbol">(</a> <a id="4019" class="Symbol">(</a><a id="4020" href="order-theory.join-semilattices.html#4020" class="Bound">x</a> <a id="4022" class="Symbol">:</a> <a id="4024" href="group-theory.semigroups.html#933" class="Function">type-Semigroup</a> <a id="4039" href="order-theory.join-semilattices.html#3914" class="Bound">X</a><a id="4040" class="Symbol">)</a> <a id="4042" class="Symbol">→</a> <a id="4044" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="4047" class="Symbol">(</a><a id="4048" href="group-theory.semigroups.html#1215" class="Function">mul-Semigroup</a> <a id="4062" href="order-theory.join-semilattices.html#3914" class="Bound">X</a> <a id="4064" href="order-theory.join-semilattices.html#4020" class="Bound">x</a> <a id="4066" href="order-theory.join-semilattices.html#4020" class="Bound">x</a><a id="4067" class="Symbol">)</a> <a id="4069" href="order-theory.join-semilattices.html#4020" class="Bound">x</a><a id="4070" class="Symbol">))</a>
</pre>