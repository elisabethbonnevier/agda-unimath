# Decidable dependent function types

<pre class="Agda"><a id="47" class="Symbol">{-#</a> <a id="51" class="Keyword">OPTIONS</a> <a id="59" class="Pragma">--without-K</a> <a id="71" class="Pragma">--exact-split</a> <a id="85" class="Symbol">#-}</a>

<a id="90" class="Keyword">module</a> <a id="97" href="univalent-combinatorics.decidable-dependent-function-types.html" class="Module">univalent-combinatorics.decidable-dependent-function-types</a> <a id="156" class="Keyword">where</a>

<a id="163" class="Keyword">open</a> <a id="168" class="Keyword">import</a> <a id="175" href="elementary-number-theory.decidable-dependent-function-types.html" class="Module">elementary-number-theory.decidable-dependent-function-types</a> <a id="235" class="Keyword">public</a>

<a id="243" class="Keyword">open</a> <a id="248" class="Keyword">import</a> <a id="255" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a> <a id="296" class="Keyword">using</a> <a id="302" class="Symbol">(</a><a id="303" href="elementary-number-theory.natural-numbers.html#1444" class="Datatype">ℕ</a><a id="304" class="Symbol">;</a> <a id="306" href="elementary-number-theory.natural-numbers.html#1478" class="InductiveConstructor">succ-ℕ</a><a id="312" class="Symbol">;</a> <a id="314" href="elementary-number-theory.natural-numbers.html#1465" class="InductiveConstructor">zero-ℕ</a><a id="320" class="Symbol">)</a>

<a id="323" class="Keyword">open</a> <a id="328" class="Keyword">import</a> <a id="335" href="foundation.coproduct-types.html" class="Module">foundation.coproduct-types</a> <a id="362" class="Keyword">using</a> <a id="368" class="Symbol">(</a><a id="369" href="foundation.coproduct-types.html#1168" class="Datatype">coprod</a><a id="375" class="Symbol">;</a> <a id="377" href="foundation.coproduct-types.html#1239" class="InductiveConstructor">inl</a><a id="380" class="Symbol">;</a> <a id="382" href="foundation.coproduct-types.html#1262" class="InductiveConstructor">inr</a><a id="385" class="Symbol">)</a>
<a id="387" class="Keyword">open</a> <a id="392" class="Keyword">import</a> <a id="399" href="foundation.decidable-types.html" class="Module">foundation.decidable-types</a> <a id="426" class="Keyword">using</a>
  <a id="434" class="Symbol">(</a> <a id="436" href="foundation.decidable-types.html#1741" class="Function">is-decidable</a><a id="448" class="Symbol">;</a> <a id="450" href="foundation.decidable-types.html#5377" class="Function">is-decidable-iff</a><a id="466" class="Symbol">;</a> <a id="468" href="foundation.decidable-types.html#7858" class="Function">is-decidable-Prop</a><a id="485" class="Symbol">)</a>
<a id="487" class="Keyword">open</a> <a id="492" class="Keyword">import</a> <a id="499" href="foundation.empty-types.html" class="Module">foundation.empty-types</a> <a id="522" class="Keyword">using</a> <a id="528" class="Symbol">(</a><a id="529" href="foundation-core.empty-types.html#1068" class="Function">ind-empty</a><a id="538" class="Symbol">)</a>
<a id="540" class="Keyword">open</a> <a id="545" class="Keyword">import</a> <a id="552" href="foundation.equivalences.html" class="Module">foundation.equivalences</a> <a id="576" class="Keyword">using</a> <a id="582" class="Symbol">(</a><a id="583" href="foundation-core.equivalences.html#2480" class="Function">id-equiv</a><a id="591" class="Symbol">)</a>
<a id="593" class="Keyword">open</a> <a id="598" class="Keyword">import</a> <a id="605" href="foundation.functions.html" class="Module">foundation.functions</a> <a id="626" class="Keyword">using</a> <a id="632" class="Symbol">(</a><a id="633" href="foundation-core.functions.html#1230" class="Function">map-Π</a><a id="638" class="Symbol">)</a>
<a id="640" class="Keyword">open</a> <a id="645" class="Keyword">import</a> <a id="652" href="foundation.global-choice.html" class="Module">foundation.global-choice</a> <a id="677" class="Keyword">using</a> <a id="683" class="Symbol">(</a><a id="684" href="foundation.global-choice.html#1779" class="Function">elim-trunc-Prop-is-decidable</a><a id="712" class="Symbol">)</a>
<a id="714" class="Keyword">open</a> <a id="719" class="Keyword">import</a> <a id="726" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a> <a id="763" class="Keyword">using</a>
  <a id="771" class="Symbol">(</a> <a id="773" href="foundation.propositional-truncations.html#1701" class="Postulate">type-trunc-Prop</a><a id="788" class="Symbol">;</a> <a id="790" href="foundation.propositional-truncations.html#4789" class="Function">map-universal-property-trunc-Prop</a><a id="823" class="Symbol">;</a> <a id="825" href="foundation.propositional-truncations.html#2133" class="Function">trunc-Prop</a><a id="835" class="Symbol">;</a>
    <a id="841" href="foundation.propositional-truncations.html#1756" class="Postulate">unit-trunc-Prop</a><a id="856" class="Symbol">;</a> <a id="858" href="foundation.propositional-truncations.html#5148" class="Function">apply-universal-property-trunc-Prop</a><a id="893" class="Symbol">)</a>
<a id="895" class="Keyword">open</a> <a id="900" class="Keyword">import</a> <a id="907" href="foundation.propositions.html" class="Module">foundation.propositions</a> <a id="931" class="Keyword">using</a> <a id="937" class="Symbol">(</a><a id="938" href="foundation.propositions.html#1941" class="Function">Π-Prop</a><a id="944" class="Symbol">)</a>
<a id="946" class="Keyword">open</a> <a id="951" class="Keyword">import</a> <a id="958" href="foundation.unit-type.html" class="Module">foundation.unit-type</a> <a id="979" class="Keyword">using</a> <a id="985" class="Symbol">(</a><a id="986" href="foundation.unit-type.html#999" class="InductiveConstructor">star</a><a id="990" class="Symbol">)</a>
<a id="992" class="Keyword">open</a> <a id="997" class="Keyword">import</a> <a id="1004" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="1031" class="Keyword">using</a> <a id="1037" class="Symbol">(</a><a id="1038" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1043" class="Symbol">;</a> <a id="1045" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="1047" class="Symbol">)</a>

<a id="1050" class="Keyword">open</a> <a id="1055" class="Keyword">import</a> <a id="1062" href="univalent-combinatorics.counting.html" class="Module">univalent-combinatorics.counting</a> <a id="1095" class="Keyword">using</a>
  <a id="1103" class="Symbol">(</a> <a id="1105" href="univalent-combinatorics.counting.html#1746" class="Function">count</a><a id="1110" class="Symbol">;</a> <a id="1112" href="univalent-combinatorics.counting.html#1943" class="Function">equiv-count</a><a id="1123" class="Symbol">;</a> <a id="1125" href="univalent-combinatorics.counting.html#2017" class="Function">map-equiv-count</a><a id="1140" class="Symbol">)</a>
<a id="1142" class="Keyword">open</a> <a id="1147" class="Keyword">import</a> <a id="1154" href="univalent-combinatorics.finite-choice.html" class="Module">univalent-combinatorics.finite-choice</a> <a id="1192" class="Keyword">using</a> <a id="1198" class="Symbol">(</a><a id="1199" href="univalent-combinatorics.finite-choice.html#3449" class="Function">finite-choice</a><a id="1212" class="Symbol">)</a>
<a id="1214" class="Keyword">open</a> <a id="1219" class="Keyword">import</a> <a id="1226" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a> <a id="1263" class="Keyword">using</a> <a id="1269" class="Symbol">(</a><a id="1270" href="univalent-combinatorics.finite-types.html#3651" class="Function">is-finite</a><a id="1279" class="Symbol">)</a>
<a id="1281" class="Keyword">open</a> <a id="1286" class="Keyword">import</a> <a id="1293" href="univalent-combinatorics.standard-finite-types.html" class="Module">univalent-combinatorics.standard-finite-types</a> <a id="1339" class="Keyword">using</a> <a id="1345" class="Symbol">(</a><a id="1346" href="univalent-combinatorics.standard-finite-types.html#2072" class="Function">Fin</a><a id="1349" class="Symbol">)</a>
</pre>
## Idea

We describe conditions under which dependent products are decidable.

<pre class="Agda"><a id="is-decidable-Π-Fin"></a><a id="1443" href="univalent-combinatorics.decidable-dependent-function-types.html#1443" class="Function">is-decidable-Π-Fin</a> <a id="1462" class="Symbol">:</a>
  <a id="1466" class="Symbol">{</a><a id="1467" href="univalent-combinatorics.decidable-dependent-function-types.html#1467" class="Bound">l1</a> <a id="1470" class="Symbol">:</a> <a id="1472" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1477" class="Symbol">}</a> <a id="1479" class="Symbol">{</a><a id="1480" href="univalent-combinatorics.decidable-dependent-function-types.html#1480" class="Bound">k</a> <a id="1482" class="Symbol">:</a> <a id="1484" href="elementary-number-theory.natural-numbers.html#1444" class="Datatype">ℕ</a><a id="1485" class="Symbol">}</a> <a id="1487" class="Symbol">{</a><a id="1488" href="univalent-combinatorics.decidable-dependent-function-types.html#1488" class="Bound">B</a> <a id="1490" class="Symbol">:</a> <a id="1492" href="univalent-combinatorics.standard-finite-types.html#2072" class="Function">Fin</a> <a id="1496" href="univalent-combinatorics.decidable-dependent-function-types.html#1480" class="Bound">k</a> <a id="1498" class="Symbol">→</a> <a id="1500" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1503" href="univalent-combinatorics.decidable-dependent-function-types.html#1467" class="Bound">l1</a><a id="1505" class="Symbol">}</a> <a id="1507" class="Symbol">→</a>
  <a id="1511" class="Symbol">((</a><a id="1513" href="univalent-combinatorics.decidable-dependent-function-types.html#1513" class="Bound">x</a> <a id="1515" class="Symbol">:</a> <a id="1517" href="univalent-combinatorics.standard-finite-types.html#2072" class="Function">Fin</a> <a id="1521" href="univalent-combinatorics.decidable-dependent-function-types.html#1480" class="Bound">k</a><a id="1522" class="Symbol">)</a> <a id="1524" class="Symbol">→</a> <a id="1526" href="foundation.decidable-types.html#1741" class="Function">is-decidable</a> <a id="1539" class="Symbol">(</a><a id="1540" href="univalent-combinatorics.decidable-dependent-function-types.html#1488" class="Bound">B</a> <a id="1542" href="univalent-combinatorics.decidable-dependent-function-types.html#1513" class="Bound">x</a><a id="1543" class="Symbol">))</a> <a id="1546" class="Symbol">→</a> <a id="1548" href="foundation.decidable-types.html#1741" class="Function">is-decidable</a> <a id="1561" class="Symbol">((</a><a id="1563" href="univalent-combinatorics.decidable-dependent-function-types.html#1563" class="Bound">x</a> <a id="1565" class="Symbol">:</a> <a id="1567" href="univalent-combinatorics.standard-finite-types.html#2072" class="Function">Fin</a> <a id="1571" href="univalent-combinatorics.decidable-dependent-function-types.html#1480" class="Bound">k</a><a id="1572" class="Symbol">)</a> <a id="1574" class="Symbol">→</a> <a id="1576" href="univalent-combinatorics.decidable-dependent-function-types.html#1488" class="Bound">B</a> <a id="1578" href="univalent-combinatorics.decidable-dependent-function-types.html#1563" class="Bound">x</a><a id="1579" class="Symbol">)</a>
<a id="1581" href="univalent-combinatorics.decidable-dependent-function-types.html#1443" class="Function">is-decidable-Π-Fin</a> <a id="1600" class="Symbol">{</a><a id="1601" href="univalent-combinatorics.decidable-dependent-function-types.html#1601" class="Bound">l1</a><a id="1603" class="Symbol">}</a> <a id="1605" class="Symbol">{</a><a id="1606" href="elementary-number-theory.natural-numbers.html#1465" class="InductiveConstructor">zero-ℕ</a><a id="1612" class="Symbol">}</a> <a id="1614" class="Symbol">{</a><a id="1615" href="univalent-combinatorics.decidable-dependent-function-types.html#1615" class="Bound">B</a><a id="1616" class="Symbol">}</a> <a id="1618" href="univalent-combinatorics.decidable-dependent-function-types.html#1618" class="Bound">d</a> <a id="1620" class="Symbol">=</a> <a id="1622" href="foundation.coproduct-types.html#1239" class="InductiveConstructor">inl</a> <a id="1626" href="foundation-core.empty-types.html#1068" class="Function">ind-empty</a>
<a id="1636" href="univalent-combinatorics.decidable-dependent-function-types.html#1443" class="Function">is-decidable-Π-Fin</a> <a id="1655" class="Symbol">{</a><a id="1656" href="univalent-combinatorics.decidable-dependent-function-types.html#1656" class="Bound">l1</a><a id="1658" class="Symbol">}</a> <a id="1660" class="Symbol">{</a><a id="1661" href="elementary-number-theory.natural-numbers.html#1478" class="InductiveConstructor">succ-ℕ</a> <a id="1668" href="univalent-combinatorics.decidable-dependent-function-types.html#1668" class="Bound">k</a><a id="1669" class="Symbol">}</a> <a id="1671" class="Symbol">{</a><a id="1672" href="univalent-combinatorics.decidable-dependent-function-types.html#1672" class="Bound">B</a><a id="1673" class="Symbol">}</a> <a id="1675" href="univalent-combinatorics.decidable-dependent-function-types.html#1675" class="Bound">d</a> <a id="1677" class="Symbol">=</a>
  <a id="1681" href="foundation.decidable-dependent-function-types.html#1393" class="Function">is-decidable-Π-Maybe</a>
    <a id="1706" class="Symbol">(</a> <a id="1708" href="univalent-combinatorics.decidable-dependent-function-types.html#1443" class="Function">is-decidable-Π-Fin</a> <a id="1727" class="Symbol">(λ</a> <a id="1730" href="univalent-combinatorics.decidable-dependent-function-types.html#1730" class="Bound">x</a> <a id="1732" class="Symbol">→</a> <a id="1734" href="univalent-combinatorics.decidable-dependent-function-types.html#1675" class="Bound">d</a> <a id="1736" class="Symbol">(</a><a id="1737" href="foundation.coproduct-types.html#1239" class="InductiveConstructor">inl</a> <a id="1741" href="univalent-combinatorics.decidable-dependent-function-types.html#1730" class="Bound">x</a><a id="1742" class="Symbol">)))</a>
    <a id="1750" class="Symbol">(</a> <a id="1752" href="univalent-combinatorics.decidable-dependent-function-types.html#1675" class="Bound">d</a> <a id="1754" class="Symbol">(</a><a id="1755" href="foundation.coproduct-types.html#1262" class="InductiveConstructor">inr</a> <a id="1759" href="foundation.unit-type.html#999" class="InductiveConstructor">star</a><a id="1763" class="Symbol">))</a>
</pre>
<pre class="Agda"><a id="is-decidable-Π-count"></a><a id="1779" href="univalent-combinatorics.decidable-dependent-function-types.html#1779" class="Function">is-decidable-Π-count</a> <a id="1800" class="Symbol">:</a>
  <a id="1804" class="Symbol">{</a><a id="1805" href="univalent-combinatorics.decidable-dependent-function-types.html#1805" class="Bound">l1</a> <a id="1808" href="univalent-combinatorics.decidable-dependent-function-types.html#1808" class="Bound">l2</a> <a id="1811" class="Symbol">:</a> <a id="1813" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1818" class="Symbol">}</a> <a id="1820" class="Symbol">{</a><a id="1821" href="univalent-combinatorics.decidable-dependent-function-types.html#1821" class="Bound">A</a> <a id="1823" class="Symbol">:</a> <a id="1825" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1828" href="univalent-combinatorics.decidable-dependent-function-types.html#1805" class="Bound">l1</a><a id="1830" class="Symbol">}</a> <a id="1832" class="Symbol">{</a><a id="1833" href="univalent-combinatorics.decidable-dependent-function-types.html#1833" class="Bound">B</a> <a id="1835" class="Symbol">:</a> <a id="1837" href="univalent-combinatorics.decidable-dependent-function-types.html#1821" class="Bound">A</a> <a id="1839" class="Symbol">→</a> <a id="1841" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1844" href="univalent-combinatorics.decidable-dependent-function-types.html#1808" class="Bound">l2</a><a id="1846" class="Symbol">}</a> <a id="1848" class="Symbol">→</a>
  <a id="1852" href="univalent-combinatorics.counting.html#1746" class="Function">count</a> <a id="1858" href="univalent-combinatorics.decidable-dependent-function-types.html#1821" class="Bound">A</a> <a id="1860" class="Symbol">→</a> <a id="1862" class="Symbol">((</a><a id="1864" href="univalent-combinatorics.decidable-dependent-function-types.html#1864" class="Bound">x</a> <a id="1866" class="Symbol">:</a> <a id="1868" href="univalent-combinatorics.decidable-dependent-function-types.html#1821" class="Bound">A</a><a id="1869" class="Symbol">)</a> <a id="1871" class="Symbol">→</a> <a id="1873" href="foundation.decidable-types.html#1741" class="Function">is-decidable</a> <a id="1886" class="Symbol">(</a><a id="1887" href="univalent-combinatorics.decidable-dependent-function-types.html#1833" class="Bound">B</a> <a id="1889" href="univalent-combinatorics.decidable-dependent-function-types.html#1864" class="Bound">x</a><a id="1890" class="Symbol">))</a> <a id="1893" class="Symbol">→</a> <a id="1895" href="foundation.decidable-types.html#1741" class="Function">is-decidable</a> <a id="1908" class="Symbol">((</a><a id="1910" href="univalent-combinatorics.decidable-dependent-function-types.html#1910" class="Bound">x</a> <a id="1912" class="Symbol">:</a> <a id="1914" href="univalent-combinatorics.decidable-dependent-function-types.html#1821" class="Bound">A</a><a id="1915" class="Symbol">)</a> <a id="1917" class="Symbol">→</a> <a id="1919" href="univalent-combinatorics.decidable-dependent-function-types.html#1833" class="Bound">B</a> <a id="1921" href="univalent-combinatorics.decidable-dependent-function-types.html#1910" class="Bound">x</a><a id="1922" class="Symbol">)</a>
<a id="1924" href="univalent-combinatorics.decidable-dependent-function-types.html#1779" class="Function">is-decidable-Π-count</a> <a id="1945" href="univalent-combinatorics.decidable-dependent-function-types.html#1945" class="Bound">e</a> <a id="1947" href="univalent-combinatorics.decidable-dependent-function-types.html#1947" class="Bound">d</a> <a id="1949" class="Symbol">=</a>
  <a id="1953" href="foundation.decidable-dependent-function-types.html#1800" class="Function">is-decidable-Π-equiv</a>
    <a id="1978" class="Symbol">(</a> <a id="1980" href="univalent-combinatorics.counting.html#1943" class="Function">equiv-count</a> <a id="1992" href="univalent-combinatorics.decidable-dependent-function-types.html#1945" class="Bound">e</a><a id="1993" class="Symbol">)</a>
    <a id="1999" class="Symbol">(</a> <a id="2001" class="Symbol">λ</a> <a id="2003" href="univalent-combinatorics.decidable-dependent-function-types.html#2003" class="Bound">x</a> <a id="2005" class="Symbol">→</a> <a id="2007" href="foundation-core.equivalences.html#2480" class="Function">id-equiv</a><a id="2015" class="Symbol">)</a>
    <a id="2021" class="Symbol">(</a> <a id="2023" href="univalent-combinatorics.decidable-dependent-function-types.html#1443" class="Function">is-decidable-Π-Fin</a> <a id="2042" class="Symbol">(λ</a> <a id="2045" href="univalent-combinatorics.decidable-dependent-function-types.html#2045" class="Bound">x</a> <a id="2047" class="Symbol">→</a> <a id="2049" href="univalent-combinatorics.decidable-dependent-function-types.html#1947" class="Bound">d</a> <a id="2051" class="Symbol">(</a><a id="2052" href="univalent-combinatorics.counting.html#2017" class="Function">map-equiv-count</a> <a id="2068" href="univalent-combinatorics.decidable-dependent-function-types.html#1945" class="Bound">e</a> <a id="2070" href="univalent-combinatorics.decidable-dependent-function-types.html#2045" class="Bound">x</a><a id="2071" class="Symbol">)))</a>

<a id="is-decidable-Π-is-finite"></a><a id="2076" href="univalent-combinatorics.decidable-dependent-function-types.html#2076" class="Function">is-decidable-Π-is-finite</a> <a id="2101" class="Symbol">:</a>
  <a id="2105" class="Symbol">{</a><a id="2106" href="univalent-combinatorics.decidable-dependent-function-types.html#2106" class="Bound">l1</a> <a id="2109" href="univalent-combinatorics.decidable-dependent-function-types.html#2109" class="Bound">l2</a> <a id="2112" class="Symbol">:</a> <a id="2114" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2119" class="Symbol">}</a> <a id="2121" class="Symbol">{</a><a id="2122" href="univalent-combinatorics.decidable-dependent-function-types.html#2122" class="Bound">A</a> <a id="2124" class="Symbol">:</a> <a id="2126" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2129" href="univalent-combinatorics.decidable-dependent-function-types.html#2106" class="Bound">l1</a><a id="2131" class="Symbol">}</a> <a id="2133" class="Symbol">{</a><a id="2134" href="univalent-combinatorics.decidable-dependent-function-types.html#2134" class="Bound">B</a> <a id="2136" class="Symbol">:</a> <a id="2138" href="univalent-combinatorics.decidable-dependent-function-types.html#2122" class="Bound">A</a> <a id="2140" class="Symbol">→</a> <a id="2142" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2145" href="univalent-combinatorics.decidable-dependent-function-types.html#2109" class="Bound">l2</a><a id="2147" class="Symbol">}</a> <a id="2149" class="Symbol">→</a> <a id="2151" href="univalent-combinatorics.finite-types.html#3651" class="Function">is-finite</a> <a id="2161" href="univalent-combinatorics.decidable-dependent-function-types.html#2122" class="Bound">A</a> <a id="2163" class="Symbol">→</a>
  <a id="2167" class="Symbol">((</a><a id="2169" href="univalent-combinatorics.decidable-dependent-function-types.html#2169" class="Bound">x</a> <a id="2171" class="Symbol">:</a> <a id="2173" href="univalent-combinatorics.decidable-dependent-function-types.html#2122" class="Bound">A</a><a id="2174" class="Symbol">)</a> <a id="2176" class="Symbol">→</a> <a id="2178" href="foundation.decidable-types.html#1741" class="Function">is-decidable</a> <a id="2191" class="Symbol">(</a><a id="2192" href="univalent-combinatorics.decidable-dependent-function-types.html#2134" class="Bound">B</a> <a id="2194" href="univalent-combinatorics.decidable-dependent-function-types.html#2169" class="Bound">x</a><a id="2195" class="Symbol">))</a> <a id="2198" class="Symbol">→</a> <a id="2200" href="foundation.decidable-types.html#1741" class="Function">is-decidable</a> <a id="2213" class="Symbol">((</a><a id="2215" href="univalent-combinatorics.decidable-dependent-function-types.html#2215" class="Bound">x</a> <a id="2217" class="Symbol">:</a> <a id="2219" href="univalent-combinatorics.decidable-dependent-function-types.html#2122" class="Bound">A</a><a id="2220" class="Symbol">)</a> <a id="2222" class="Symbol">→</a> <a id="2224" href="univalent-combinatorics.decidable-dependent-function-types.html#2134" class="Bound">B</a> <a id="2226" href="univalent-combinatorics.decidable-dependent-function-types.html#2215" class="Bound">x</a><a id="2227" class="Symbol">)</a>
<a id="2229" href="univalent-combinatorics.decidable-dependent-function-types.html#2076" class="Function">is-decidable-Π-is-finite</a> <a id="2254" class="Symbol">{</a><a id="2255" href="univalent-combinatorics.decidable-dependent-function-types.html#2255" class="Bound">l1</a><a id="2257" class="Symbol">}</a> <a id="2259" class="Symbol">{</a><a id="2260" href="univalent-combinatorics.decidable-dependent-function-types.html#2260" class="Bound">l2</a><a id="2262" class="Symbol">}</a> <a id="2264" class="Symbol">{</a><a id="2265" href="univalent-combinatorics.decidable-dependent-function-types.html#2265" class="Bound">A</a><a id="2266" class="Symbol">}</a> <a id="2268" class="Symbol">{</a><a id="2269" href="univalent-combinatorics.decidable-dependent-function-types.html#2269" class="Bound">B</a><a id="2270" class="Symbol">}</a> <a id="2272" href="univalent-combinatorics.decidable-dependent-function-types.html#2272" class="Bound">H</a> <a id="2274" href="univalent-combinatorics.decidable-dependent-function-types.html#2274" class="Bound">d</a> <a id="2276" class="Symbol">=</a>
  <a id="2280" href="foundation.decidable-types.html#5377" class="Function">is-decidable-iff</a>
    <a id="2301" class="Symbol">(</a> <a id="2303" href="foundation-core.functions.html#1230" class="Function">map-Π</a> <a id="2309" class="Symbol">(λ</a> <a id="2312" href="univalent-combinatorics.decidable-dependent-function-types.html#2312" class="Bound">x</a> <a id="2314" class="Symbol">→</a> <a id="2316" href="foundation.global-choice.html#1779" class="Function">elim-trunc-Prop-is-decidable</a> <a id="2345" class="Symbol">(</a><a id="2346" href="univalent-combinatorics.decidable-dependent-function-types.html#2274" class="Bound">d</a> <a id="2348" href="univalent-combinatorics.decidable-dependent-function-types.html#2312" class="Bound">x</a><a id="2349" class="Symbol">)))</a>
    <a id="2357" class="Symbol">(</a> <a id="2359" href="foundation-core.functions.html#1230" class="Function">map-Π</a> <a id="2365" class="Symbol">(λ</a> <a id="2368" href="univalent-combinatorics.decidable-dependent-function-types.html#2368" class="Bound">x</a> <a id="2370" class="Symbol">→</a> <a id="2372" href="foundation.propositional-truncations.html#1756" class="Postulate">unit-trunc-Prop</a><a id="2387" class="Symbol">))</a>
    <a id="2394" class="Symbol">(</a> <a id="2396" href="foundation.decidable-types.html#5377" class="Function">is-decidable-iff</a>
      <a id="2419" class="Symbol">(</a> <a id="2421" href="univalent-combinatorics.decidable-dependent-function-types.html#2869" class="Function">α</a><a id="2422" class="Symbol">)</a>
      <a id="2430" class="Symbol">(</a> <a id="2432" href="univalent-combinatorics.finite-choice.html#3449" class="Function">finite-choice</a> <a id="2446" href="univalent-combinatorics.decidable-dependent-function-types.html#2272" class="Bound">H</a><a id="2447" class="Symbol">)</a>
      <a id="2455" class="Symbol">(</a> <a id="2457" href="foundation.propositional-truncations.html#5148" class="Function">apply-universal-property-trunc-Prop</a> <a id="2493" href="univalent-combinatorics.decidable-dependent-function-types.html#2272" class="Bound">H</a>
        <a id="2503" class="Symbol">(</a> <a id="2505" href="foundation.decidable-types.html#7858" class="Function">is-decidable-Prop</a> <a id="2523" class="Symbol">(</a><a id="2524" href="foundation.propositional-truncations.html#2133" class="Function">trunc-Prop</a> <a id="2535" class="Symbol">((</a><a id="2537" href="univalent-combinatorics.decidable-dependent-function-types.html#2537" class="Bound">x</a> <a id="2539" class="Symbol">:</a> <a id="2541" href="univalent-combinatorics.decidable-dependent-function-types.html#2265" class="Bound">A</a><a id="2542" class="Symbol">)</a> <a id="2544" class="Symbol">→</a> <a id="2546" href="univalent-combinatorics.decidable-dependent-function-types.html#2269" class="Bound">B</a> <a id="2548" href="univalent-combinatorics.decidable-dependent-function-types.html#2537" class="Bound">x</a><a id="2549" class="Symbol">)))</a>
        <a id="2561" class="Symbol">(</a> <a id="2563" class="Symbol">λ</a> <a id="2565" href="univalent-combinatorics.decidable-dependent-function-types.html#2565" class="Bound">e</a> <a id="2567" class="Symbol">→</a>
          <a id="2579" href="foundation.decidable-types.html#5377" class="Function">is-decidable-iff</a>
            <a id="2608" class="Symbol">(</a> <a id="2610" href="univalent-combinatorics.finite-choice.html#3449" class="Function">finite-choice</a> <a id="2624" href="univalent-combinatorics.decidable-dependent-function-types.html#2272" class="Bound">H</a><a id="2625" class="Symbol">)</a>
            <a id="2639" class="Symbol">(</a> <a id="2641" href="univalent-combinatorics.decidable-dependent-function-types.html#2869" class="Function">α</a><a id="2642" class="Symbol">)</a>
            <a id="2656" class="Symbol">(</a> <a id="2658" href="univalent-combinatorics.decidable-dependent-function-types.html#1779" class="Function">is-decidable-Π-count</a> <a id="2679" href="univalent-combinatorics.decidable-dependent-function-types.html#2565" class="Bound">e</a>
              <a id="2695" class="Symbol">(</a> <a id="2697" class="Symbol">λ</a> <a id="2699" href="univalent-combinatorics.decidable-dependent-function-types.html#2699" class="Bound">x</a> <a id="2701" class="Symbol">→</a>
                <a id="2719" href="foundation.decidable-types.html#5377" class="Function">is-decidable-iff</a>
                  <a id="2754" class="Symbol">(</a> <a id="2756" href="foundation.propositional-truncations.html#1756" class="Postulate">unit-trunc-Prop</a><a id="2771" class="Symbol">)</a>
                  <a id="2791" class="Symbol">(</a> <a id="2793" href="foundation.global-choice.html#1779" class="Function">elim-trunc-Prop-is-decidable</a> <a id="2822" class="Symbol">(</a><a id="2823" href="univalent-combinatorics.decidable-dependent-function-types.html#2274" class="Bound">d</a> <a id="2825" href="univalent-combinatorics.decidable-dependent-function-types.html#2699" class="Bound">x</a><a id="2826" class="Symbol">))</a>
                  <a id="2847" class="Symbol">(</a> <a id="2849" href="univalent-combinatorics.decidable-dependent-function-types.html#2274" class="Bound">d</a> <a id="2851" href="univalent-combinatorics.decidable-dependent-function-types.html#2699" class="Bound">x</a><a id="2852" class="Symbol">))))))</a>
  <a id="2861" class="Keyword">where</a>
  <a id="2869" href="univalent-combinatorics.decidable-dependent-function-types.html#2869" class="Function">α</a> <a id="2871" class="Symbol">:</a> <a id="2873" href="foundation.propositional-truncations.html#1701" class="Postulate">type-trunc-Prop</a> <a id="2889" class="Symbol">((</a><a id="2891" href="univalent-combinatorics.decidable-dependent-function-types.html#2891" class="Bound">x</a> <a id="2893" class="Symbol">:</a> <a id="2895" href="univalent-combinatorics.decidable-dependent-function-types.html#2265" class="Bound">A</a><a id="2896" class="Symbol">)</a> <a id="2898" class="Symbol">→</a> <a id="2900" href="univalent-combinatorics.decidable-dependent-function-types.html#2269" class="Bound">B</a> <a id="2902" href="univalent-combinatorics.decidable-dependent-function-types.html#2891" class="Bound">x</a><a id="2903" class="Symbol">)</a> <a id="2905" class="Symbol">→</a> <a id="2907" class="Symbol">(</a><a id="2908" href="univalent-combinatorics.decidable-dependent-function-types.html#2908" class="Bound">x</a> <a id="2910" class="Symbol">:</a> <a id="2912" href="univalent-combinatorics.decidable-dependent-function-types.html#2265" class="Bound">A</a><a id="2913" class="Symbol">)</a> <a id="2915" class="Symbol">→</a> <a id="2917" href="foundation.propositional-truncations.html#1701" class="Postulate">type-trunc-Prop</a> <a id="2933" class="Symbol">(</a><a id="2934" href="univalent-combinatorics.decidable-dependent-function-types.html#2269" class="Bound">B</a> <a id="2936" href="univalent-combinatorics.decidable-dependent-function-types.html#2908" class="Bound">x</a><a id="2937" class="Symbol">)</a>
  <a id="2941" href="univalent-combinatorics.decidable-dependent-function-types.html#2869" class="Function">α</a> <a id="2943" class="Symbol">=</a> <a id="2945" href="foundation.propositional-truncations.html#4789" class="Function">map-universal-property-trunc-Prop</a>
        <a id="2987" class="Symbol">(</a> <a id="2989" href="foundation.propositions.html#1941" class="Function">Π-Prop</a> <a id="2996" href="univalent-combinatorics.decidable-dependent-function-types.html#2265" class="Bound">A</a> <a id="2998" class="Symbol">(λ</a> <a id="3001" href="univalent-combinatorics.decidable-dependent-function-types.html#3001" class="Bound">x</a> <a id="3003" class="Symbol">→</a> <a id="3005" href="foundation.propositional-truncations.html#2133" class="Function">trunc-Prop</a> <a id="3016" class="Symbol">(</a><a id="3017" href="univalent-combinatorics.decidable-dependent-function-types.html#2269" class="Bound">B</a> <a id="3019" href="univalent-combinatorics.decidable-dependent-function-types.html#3001" class="Bound">x</a><a id="3020" class="Symbol">)))</a>
        <a id="3032" class="Symbol">(</a> <a id="3034" class="Symbol">λ</a> <a id="3036" class="Symbol">(</a><a id="3037" href="univalent-combinatorics.decidable-dependent-function-types.html#3037" class="Bound">f</a> <a id="3039" class="Symbol">:</a> <a id="3041" class="Symbol">(</a><a id="3042" href="univalent-combinatorics.decidable-dependent-function-types.html#3042" class="Bound">x</a> <a id="3044" class="Symbol">:</a> <a id="3046" href="univalent-combinatorics.decidable-dependent-function-types.html#2265" class="Bound">A</a><a id="3047" class="Symbol">)</a> <a id="3049" class="Symbol">→</a> <a id="3051" href="univalent-combinatorics.decidable-dependent-function-types.html#2269" class="Bound">B</a> <a id="3053" href="univalent-combinatorics.decidable-dependent-function-types.html#3042" class="Bound">x</a><a id="3054" class="Symbol">)</a> <a id="3056" class="Symbol">(</a><a id="3057" href="univalent-combinatorics.decidable-dependent-function-types.html#3057" class="Bound">x</a> <a id="3059" class="Symbol">:</a> <a id="3061" href="univalent-combinatorics.decidable-dependent-function-types.html#2265" class="Bound">A</a><a id="3062" class="Symbol">)</a> <a id="3064" class="Symbol">→</a> <a id="3066" href="foundation.propositional-truncations.html#1756" class="Postulate">unit-trunc-Prop</a> <a id="3082" class="Symbol">(</a><a id="3083" href="univalent-combinatorics.decidable-dependent-function-types.html#3037" class="Bound">f</a> <a id="3085" href="univalent-combinatorics.decidable-dependent-function-types.html#3057" class="Bound">x</a><a id="3086" class="Symbol">))</a>
</pre>