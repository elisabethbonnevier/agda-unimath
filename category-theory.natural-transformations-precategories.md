# Natural transformations between functors on precategories

<pre class="Agda"><a id="70" class="Symbol">{-#</a> <a id="74" class="Keyword">OPTIONS</a> <a id="82" class="Pragma">--without-K</a> <a id="94" class="Pragma">--exact-split</a> <a id="108" class="Symbol">#-}</a>

<a id="113" class="Keyword">module</a> <a id="120" href="category-theory.natural-transformations-precategories.html" class="Module">category-theory.natural-transformations-precategories</a> <a id="174" class="Keyword">where</a>

<a id="181" class="Keyword">open</a> <a id="186" class="Keyword">import</a> <a id="193" href="category-theory.functors-precategories.html" class="Module">category-theory.functors-precategories</a> <a id="232" class="Keyword">using</a>
  <a id="240" class="Symbol">(</a><a id="241" href="category-theory.functors-precategories.html#1046" class="Function">functor-Precat</a><a id="255" class="Symbol">;</a> <a id="257" href="category-theory.functors-precategories.html#1611" class="Function">obj-functor-Precat</a><a id="275" class="Symbol">;</a> <a id="277" href="category-theory.functors-precategories.html#1707" class="Function">hom-functor-Precat</a><a id="295" class="Symbol">)</a>
<a id="297" class="Keyword">open</a> <a id="302" class="Keyword">import</a> <a id="309" href="category-theory.precategories.html" class="Module">category-theory.precategories</a> <a id="339" class="Keyword">using</a>
  <a id="347" class="Symbol">(</a> <a id="349" href="category-theory.precategories.html#2242" class="Function">Precat</a><a id="355" class="Symbol">;</a> <a id="357" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a><a id="367" class="Symbol">;</a> <a id="369" href="category-theory.precategories.html#2674" class="Function">type-hom-Precat</a><a id="384" class="Symbol">;</a> <a id="386" href="category-theory.precategories.html#3056" class="Function">comp-hom-Precat</a><a id="401" class="Symbol">;</a>
    <a id="407" href="category-theory.precategories.html#2772" class="Function">is-set-type-hom-Precat</a><a id="429" class="Symbol">)</a>
<a id="431" class="Keyword">open</a> <a id="436" class="Keyword">import</a> <a id="443" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="475" class="Keyword">using</a> <a id="481" class="Symbol">(</a><a id="482" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="483" class="Symbol">;</a> <a id="485" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="488" class="Symbol">)</a>
<a id="490" class="Keyword">open</a> <a id="495" class="Keyword">import</a> <a id="502" href="foundation.identity-types.html" class="Module">foundation.identity-types</a> <a id="528" class="Keyword">using</a> <a id="534" class="Symbol">(</a><a id="535" href="foundation-core.identity-types.html#641" class="Datatype">Id</a><a id="537" class="Symbol">)</a>
<a id="539" class="Keyword">open</a> <a id="544" class="Keyword">import</a> <a id="551" href="foundation.propositions.html" class="Module">foundation.propositions</a> <a id="575" class="Keyword">using</a>
  <a id="583" class="Symbol">(</a> <a id="585" href="foundation-core.propositions.html#1246" class="Function">is-prop</a><a id="592" class="Symbol">;</a> <a id="594" href="foundation.propositions.html#1492" class="Function">is-prop-Π</a><a id="603" class="Symbol">;</a> <a id="605" href="foundation.propositions.html#2166" class="Function">is-prop-Π&#39;</a><a id="615" class="Symbol">)</a>
<a id="617" class="Keyword">open</a> <a id="622" class="Keyword">import</a> <a id="629" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="656" class="Keyword">using</a> <a id="662" class="Symbol">(</a><a id="663" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="668" class="Symbol">;</a> <a id="670" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="672" class="Symbol">;</a> <a id="674" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="677" class="Symbol">)</a>
</pre>
## Idea

Given precategories `C` and `D`, a natural transformation from a functor `F : C → D` to `G : C → D` consists of :
- a family of morphisms `γ : (x : C) → hom (F x) (G x)`
such that the following identity holds:
- `comp (G f) (γ x) = comp (γ y) (F f)`, for all `f : hom x y`.

## Definition

<pre class="Agda"><a id="991" class="Keyword">module</a> <a id="998" href="category-theory.natural-transformations-precategories.html#998" class="Module">_</a>
  <a id="1002" class="Symbol">{</a><a id="1003" href="category-theory.natural-transformations-precategories.html#1003" class="Bound">l1</a> <a id="1006" href="category-theory.natural-transformations-precategories.html#1006" class="Bound">l2</a> <a id="1009" href="category-theory.natural-transformations-precategories.html#1009" class="Bound">l3</a> <a id="1012" href="category-theory.natural-transformations-precategories.html#1012" class="Bound">l4</a> <a id="1015" class="Symbol">:</a> <a id="1017" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1022" class="Symbol">}</a> <a id="1024" class="Symbol">(</a><a id="1025" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a> <a id="1027" class="Symbol">:</a> <a id="1029" href="category-theory.precategories.html#2242" class="Function">Precat</a> <a id="1036" href="category-theory.natural-transformations-precategories.html#1003" class="Bound">l1</a> <a id="1039" href="category-theory.natural-transformations-precategories.html#1006" class="Bound">l2</a><a id="1041" class="Symbol">)</a> <a id="1043" class="Symbol">(</a><a id="1044" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1046" class="Symbol">:</a> <a id="1048" href="category-theory.precategories.html#2242" class="Function">Precat</a> <a id="1055" href="category-theory.natural-transformations-precategories.html#1009" class="Bound">l3</a> <a id="1058" href="category-theory.natural-transformations-precategories.html#1012" class="Bound">l4</a><a id="1060" class="Symbol">)</a>
  <a id="1064" class="Symbol">(</a><a id="1065" href="category-theory.natural-transformations-precategories.html#1065" class="Bound">F</a> <a id="1067" href="category-theory.natural-transformations-precategories.html#1067" class="Bound">G</a> <a id="1069" class="Symbol">:</a> <a id="1071" href="category-theory.functors-precategories.html#1046" class="Function">functor-Precat</a> <a id="1086" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a> <a id="1088" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a><a id="1089" class="Symbol">)</a>
  <a id="1093" class="Keyword">where</a>

  <a id="1102" href="category-theory.natural-transformations-precategories.html#1102" class="Function">is-nat-trans-Precat</a> <a id="1122" class="Symbol">:</a>
    <a id="1128" class="Symbol">(</a> <a id="1130" class="Symbol">(</a><a id="1131" href="category-theory.natural-transformations-precategories.html#1131" class="Bound">x</a> <a id="1133" class="Symbol">:</a> <a id="1135" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a> <a id="1146" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a><a id="1147" class="Symbol">)</a> <a id="1149" class="Symbol">→</a>
      <a id="1157" href="category-theory.precategories.html#2674" class="Function">type-hom-Precat</a> <a id="1173" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a>
        <a id="1183" class="Symbol">(</a> <a id="1185" href="category-theory.functors-precategories.html#1611" class="Function">obj-functor-Precat</a> <a id="1204" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a> <a id="1206" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1208" href="category-theory.natural-transformations-precategories.html#1065" class="Bound">F</a> <a id="1210" href="category-theory.natural-transformations-precategories.html#1131" class="Bound">x</a><a id="1211" class="Symbol">)</a>
        <a id="1221" class="Symbol">(</a> <a id="1223" href="category-theory.functors-precategories.html#1611" class="Function">obj-functor-Precat</a> <a id="1242" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a> <a id="1244" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1246" href="category-theory.natural-transformations-precategories.html#1067" class="Bound">G</a> <a id="1248" href="category-theory.natural-transformations-precategories.html#1131" class="Bound">x</a><a id="1249" class="Symbol">))</a> <a id="1252" class="Symbol">→</a>
    <a id="1258" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1261" class="Symbol">(</a><a id="1262" href="category-theory.natural-transformations-precategories.html#1003" class="Bound">l1</a> <a id="1265" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1267" href="category-theory.natural-transformations-precategories.html#1006" class="Bound">l2</a> <a id="1270" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1272" href="category-theory.natural-transformations-precategories.html#1012" class="Bound">l4</a><a id="1274" class="Symbol">)</a>
  <a id="1278" href="category-theory.natural-transformations-precategories.html#1102" class="Function">is-nat-trans-Precat</a> <a id="1298" href="category-theory.natural-transformations-precategories.html#1298" class="Bound">γ</a> <a id="1300" class="Symbol">=</a>
    <a id="1306" class="Symbol">{</a><a id="1307" href="category-theory.natural-transformations-precategories.html#1307" class="Bound">x</a> <a id="1309" href="category-theory.natural-transformations-precategories.html#1309" class="Bound">y</a> <a id="1311" class="Symbol">:</a> <a id="1313" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a> <a id="1324" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a><a id="1325" class="Symbol">}</a> <a id="1327" class="Symbol">(</a><a id="1328" href="category-theory.natural-transformations-precategories.html#1328" class="Bound">f</a> <a id="1330" class="Symbol">:</a> <a id="1332" href="category-theory.precategories.html#2674" class="Function">type-hom-Precat</a> <a id="1348" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a> <a id="1350" href="category-theory.natural-transformations-precategories.html#1307" class="Bound">x</a> <a id="1352" href="category-theory.natural-transformations-precategories.html#1309" class="Bound">y</a><a id="1353" class="Symbol">)</a> <a id="1355" class="Symbol">→</a>
    <a id="1361" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1364" class="Symbol">(</a> <a id="1366" href="category-theory.precategories.html#3056" class="Function">comp-hom-Precat</a> <a id="1382" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1384" class="Symbol">(</a><a id="1385" href="category-theory.functors-precategories.html#1707" class="Function">hom-functor-Precat</a> <a id="1404" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a> <a id="1406" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1408" href="category-theory.natural-transformations-precategories.html#1067" class="Bound">G</a> <a id="1410" href="category-theory.natural-transformations-precategories.html#1328" class="Bound">f</a><a id="1411" class="Symbol">)</a> <a id="1413" class="Symbol">(</a><a id="1414" href="category-theory.natural-transformations-precategories.html#1298" class="Bound">γ</a> <a id="1416" href="category-theory.natural-transformations-precategories.html#1307" class="Bound">x</a><a id="1417" class="Symbol">))</a>
       <a id="1427" class="Symbol">(</a> <a id="1429" href="category-theory.precategories.html#3056" class="Function">comp-hom-Precat</a> <a id="1445" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1447" class="Symbol">(</a><a id="1448" href="category-theory.natural-transformations-precategories.html#1298" class="Bound">γ</a> <a id="1450" href="category-theory.natural-transformations-precategories.html#1309" class="Bound">y</a><a id="1451" class="Symbol">)</a> <a id="1453" class="Symbol">(</a><a id="1454" href="category-theory.functors-precategories.html#1707" class="Function">hom-functor-Precat</a> <a id="1473" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a> <a id="1475" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1477" href="category-theory.natural-transformations-precategories.html#1065" class="Bound">F</a> <a id="1479" href="category-theory.natural-transformations-precategories.html#1328" class="Bound">f</a><a id="1480" class="Symbol">))</a>

  <a id="1486" href="category-theory.natural-transformations-precategories.html#1486" class="Function">nat-trans-Precat</a> <a id="1503" class="Symbol">:</a> <a id="1505" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1508" class="Symbol">(</a><a id="1509" href="category-theory.natural-transformations-precategories.html#1003" class="Bound">l1</a> <a id="1512" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1514" href="category-theory.natural-transformations-precategories.html#1006" class="Bound">l2</a> <a id="1517" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1519" href="category-theory.natural-transformations-precategories.html#1012" class="Bound">l4</a><a id="1521" class="Symbol">)</a>
  <a id="1525" href="category-theory.natural-transformations-precategories.html#1486" class="Function">nat-trans-Precat</a> <a id="1542" class="Symbol">=</a>
    <a id="1548" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="1550" class="Symbol">(</a> <a id="1552" class="Symbol">(</a><a id="1553" href="category-theory.natural-transformations-precategories.html#1553" class="Bound">x</a> <a id="1555" class="Symbol">:</a> <a id="1557" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a> <a id="1568" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a><a id="1569" class="Symbol">)</a> <a id="1571" class="Symbol">→</a>
        <a id="1581" href="category-theory.precategories.html#2674" class="Function">type-hom-Precat</a> <a id="1597" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a>
          <a id="1609" class="Symbol">(</a> <a id="1611" href="category-theory.functors-precategories.html#1611" class="Function">obj-functor-Precat</a> <a id="1630" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a> <a id="1632" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1634" href="category-theory.natural-transformations-precategories.html#1065" class="Bound">F</a> <a id="1636" href="category-theory.natural-transformations-precategories.html#1553" class="Bound">x</a><a id="1637" class="Symbol">)</a>
          <a id="1649" class="Symbol">(</a> <a id="1651" href="category-theory.functors-precategories.html#1611" class="Function">obj-functor-Precat</a> <a id="1670" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a> <a id="1672" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1674" href="category-theory.natural-transformations-precategories.html#1067" class="Bound">G</a> <a id="1676" href="category-theory.natural-transformations-precategories.html#1553" class="Bound">x</a><a id="1677" class="Symbol">))</a>
      <a id="1686" class="Symbol">(</a> <a id="1688" href="category-theory.natural-transformations-precategories.html#1102" class="Function">is-nat-trans-Precat</a><a id="1707" class="Symbol">)</a>

  <a id="1712" href="category-theory.natural-transformations-precategories.html#1712" class="Function">components-nat-trans-Precat</a> <a id="1740" class="Symbol">:</a>
    <a id="1746" href="category-theory.natural-transformations-precategories.html#1486" class="Function">nat-trans-Precat</a> <a id="1763" class="Symbol">→</a> <a id="1765" class="Symbol">(</a><a id="1766" href="category-theory.natural-transformations-precategories.html#1766" class="Bound">x</a> <a id="1768" class="Symbol">:</a> <a id="1770" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a> <a id="1781" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a><a id="1782" class="Symbol">)</a> <a id="1784" class="Symbol">→</a>
    <a id="1790" href="category-theory.precategories.html#2674" class="Function">type-hom-Precat</a> <a id="1806" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1808" class="Symbol">(</a><a id="1809" href="category-theory.functors-precategories.html#1611" class="Function">obj-functor-Precat</a> <a id="1828" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a> <a id="1830" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1832" href="category-theory.natural-transformations-precategories.html#1065" class="Bound">F</a> <a id="1834" href="category-theory.natural-transformations-precategories.html#1766" class="Bound">x</a><a id="1835" class="Symbol">)</a> <a id="1837" class="Symbol">(</a><a id="1838" href="category-theory.functors-precategories.html#1611" class="Function">obj-functor-Precat</a> <a id="1857" href="category-theory.natural-transformations-precategories.html#1025" class="Bound">C</a> <a id="1859" href="category-theory.natural-transformations-precategories.html#1044" class="Bound">D</a> <a id="1861" href="category-theory.natural-transformations-precategories.html#1067" class="Bound">G</a> <a id="1863" href="category-theory.natural-transformations-precategories.html#1766" class="Bound">x</a><a id="1864" class="Symbol">)</a>
  <a id="1868" href="category-theory.natural-transformations-precategories.html#1712" class="Function">components-nat-trans-Precat</a> <a id="1896" class="Symbol">=</a> <a id="1898" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a>
</pre>
## Properties

### That a family of morphisms is a natural transformation is a proposition

This follows from the fact that the hom-types are sets.

<pre class="Agda"><a id="is-prop-is-nat-trans-Precat"></a><a id="2064" href="category-theory.natural-transformations-precategories.html#2064" class="Function">is-prop-is-nat-trans-Precat</a> <a id="2092" class="Symbol">:</a>
  <a id="2096" class="Symbol">{</a> <a id="2098" href="category-theory.natural-transformations-precategories.html#2098" class="Bound">l1</a> <a id="2101" href="category-theory.natural-transformations-precategories.html#2101" class="Bound">l2</a> <a id="2104" href="category-theory.natural-transformations-precategories.html#2104" class="Bound">l3</a> <a id="2107" href="category-theory.natural-transformations-precategories.html#2107" class="Bound">l4</a> <a id="2110" class="Symbol">:</a> <a id="2112" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2117" class="Symbol">}</a> <a id="2119" class="Symbol">(</a><a id="2120" href="category-theory.natural-transformations-precategories.html#2120" class="Bound">C</a> <a id="2122" class="Symbol">:</a> <a id="2124" href="category-theory.precategories.html#2242" class="Function">Precat</a> <a id="2131" href="category-theory.natural-transformations-precategories.html#2098" class="Bound">l1</a> <a id="2134" href="category-theory.natural-transformations-precategories.html#2101" class="Bound">l2</a><a id="2136" class="Symbol">)</a> <a id="2138" class="Symbol">(</a><a id="2139" href="category-theory.natural-transformations-precategories.html#2139" class="Bound">D</a> <a id="2141" class="Symbol">:</a> <a id="2143" href="category-theory.precategories.html#2242" class="Function">Precat</a> <a id="2150" href="category-theory.natural-transformations-precategories.html#2104" class="Bound">l3</a> <a id="2153" href="category-theory.natural-transformations-precategories.html#2107" class="Bound">l4</a><a id="2155" class="Symbol">)</a>
  <a id="2159" class="Symbol">(</a> <a id="2161" href="category-theory.natural-transformations-precategories.html#2161" class="Bound">F</a> <a id="2163" href="category-theory.natural-transformations-precategories.html#2163" class="Bound">G</a> <a id="2165" class="Symbol">:</a> <a id="2167" href="category-theory.functors-precategories.html#1046" class="Function">functor-Precat</a> <a id="2182" href="category-theory.natural-transformations-precategories.html#2120" class="Bound">C</a> <a id="2184" href="category-theory.natural-transformations-precategories.html#2139" class="Bound">D</a><a id="2185" class="Symbol">)</a> <a id="2187" class="Symbol">→</a>
  <a id="2191" class="Symbol">(</a> <a id="2193" href="category-theory.natural-transformations-precategories.html#2193" class="Bound">γ</a> <a id="2195" class="Symbol">:</a>
    <a id="2201" class="Symbol">(</a><a id="2202" href="category-theory.natural-transformations-precategories.html#2202" class="Bound">x</a> <a id="2204" class="Symbol">:</a> <a id="2206" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a> <a id="2217" href="category-theory.natural-transformations-precategories.html#2120" class="Bound">C</a><a id="2218" class="Symbol">)</a> <a id="2220" class="Symbol">→</a>
    <a id="2226" href="category-theory.precategories.html#2674" class="Function">type-hom-Precat</a> <a id="2242" href="category-theory.natural-transformations-precategories.html#2139" class="Bound">D</a>
      <a id="2250" class="Symbol">(</a> <a id="2252" href="category-theory.functors-precategories.html#1611" class="Function">obj-functor-Precat</a> <a id="2271" href="category-theory.natural-transformations-precategories.html#2120" class="Bound">C</a> <a id="2273" href="category-theory.natural-transformations-precategories.html#2139" class="Bound">D</a> <a id="2275" href="category-theory.natural-transformations-precategories.html#2161" class="Bound">F</a> <a id="2277" href="category-theory.natural-transformations-precategories.html#2202" class="Bound">x</a><a id="2278" class="Symbol">)</a>
      <a id="2286" class="Symbol">(</a> <a id="2288" href="category-theory.functors-precategories.html#1611" class="Function">obj-functor-Precat</a> <a id="2307" href="category-theory.natural-transformations-precategories.html#2120" class="Bound">C</a> <a id="2309" href="category-theory.natural-transformations-precategories.html#2139" class="Bound">D</a> <a id="2311" href="category-theory.natural-transformations-precategories.html#2163" class="Bound">G</a> <a id="2313" href="category-theory.natural-transformations-precategories.html#2202" class="Bound">x</a><a id="2314" class="Symbol">))</a> <a id="2317" class="Symbol">→</a>
  <a id="2321" href="foundation-core.propositions.html#1246" class="Function">is-prop</a> <a id="2329" class="Symbol">(</a><a id="2330" href="category-theory.natural-transformations-precategories.html#1102" class="Function">is-nat-trans-Precat</a> <a id="2350" href="category-theory.natural-transformations-precategories.html#2120" class="Bound">C</a> <a id="2352" href="category-theory.natural-transformations-precategories.html#2139" class="Bound">D</a> <a id="2354" href="category-theory.natural-transformations-precategories.html#2161" class="Bound">F</a> <a id="2356" href="category-theory.natural-transformations-precategories.html#2163" class="Bound">G</a> <a id="2358" href="category-theory.natural-transformations-precategories.html#2193" class="Bound">γ</a><a id="2359" class="Symbol">)</a>
<a id="2361" href="category-theory.natural-transformations-precategories.html#2064" class="Function">is-prop-is-nat-trans-Precat</a> <a id="2389" href="category-theory.natural-transformations-precategories.html#2389" class="Bound">C</a> <a id="2391" href="category-theory.natural-transformations-precategories.html#2391" class="Bound">D</a> <a id="2393" href="category-theory.natural-transformations-precategories.html#2393" class="Bound">F</a> <a id="2395" href="category-theory.natural-transformations-precategories.html#2395" class="Bound">G</a> <a id="2397" href="category-theory.natural-transformations-precategories.html#2397" class="Bound">γ</a> <a id="2399" class="Symbol">=</a>
  <a id="2403" href="foundation.propositions.html#2166" class="Function">is-prop-Π&#39;</a>
    <a id="2418" class="Symbol">(</a> <a id="2420" class="Symbol">λ</a> <a id="2422" href="category-theory.natural-transformations-precategories.html#2422" class="Bound">x</a> <a id="2424" class="Symbol">→</a>
      <a id="2432" href="foundation.propositions.html#2166" class="Function">is-prop-Π&#39;</a>
        <a id="2451" class="Symbol">(</a> <a id="2453" class="Symbol">λ</a> <a id="2455" href="category-theory.natural-transformations-precategories.html#2455" class="Bound">y</a> <a id="2457" class="Symbol">→</a>
          <a id="2469" href="foundation.propositions.html#1492" class="Function">is-prop-Π</a>
            <a id="2491" class="Symbol">(</a> <a id="2493" class="Symbol">λ</a> <a id="2495" href="category-theory.natural-transformations-precategories.html#2495" class="Bound">f</a> <a id="2497" class="Symbol">→</a>
              <a id="2513" href="category-theory.precategories.html#2772" class="Function">is-set-type-hom-Precat</a> <a id="2536" href="category-theory.natural-transformations-precategories.html#2391" class="Bound">D</a>
                <a id="2554" class="Symbol">(</a> <a id="2556" href="category-theory.functors-precategories.html#1611" class="Function">obj-functor-Precat</a> <a id="2575" href="category-theory.natural-transformations-precategories.html#2389" class="Bound">C</a> <a id="2577" href="category-theory.natural-transformations-precategories.html#2391" class="Bound">D</a> <a id="2579" href="category-theory.natural-transformations-precategories.html#2393" class="Bound">F</a> <a id="2581" href="category-theory.natural-transformations-precategories.html#2422" class="Bound">x</a><a id="2582" class="Symbol">)</a>
                <a id="2600" class="Symbol">(</a> <a id="2602" href="category-theory.functors-precategories.html#1611" class="Function">obj-functor-Precat</a> <a id="2621" href="category-theory.natural-transformations-precategories.html#2389" class="Bound">C</a> <a id="2623" href="category-theory.natural-transformations-precategories.html#2391" class="Bound">D</a> <a id="2625" href="category-theory.natural-transformations-precategories.html#2395" class="Bound">G</a> <a id="2627" href="category-theory.natural-transformations-precategories.html#2455" class="Bound">y</a><a id="2628" class="Symbol">)</a>
                <a id="2646" class="Symbol">(</a> <a id="2648" href="category-theory.precategories.html#3056" class="Function">comp-hom-Precat</a> <a id="2664" href="category-theory.natural-transformations-precategories.html#2391" class="Bound">D</a> <a id="2666" class="Symbol">(</a><a id="2667" href="category-theory.functors-precategories.html#1707" class="Function">hom-functor-Precat</a> <a id="2686" href="category-theory.natural-transformations-precategories.html#2389" class="Bound">C</a> <a id="2688" href="category-theory.natural-transformations-precategories.html#2391" class="Bound">D</a> <a id="2690" href="category-theory.natural-transformations-precategories.html#2395" class="Bound">G</a> <a id="2692" href="category-theory.natural-transformations-precategories.html#2495" class="Bound">f</a><a id="2693" class="Symbol">)</a> <a id="2695" class="Symbol">(</a><a id="2696" href="category-theory.natural-transformations-precategories.html#2397" class="Bound">γ</a> <a id="2698" href="category-theory.natural-transformations-precategories.html#2422" class="Bound">x</a><a id="2699" class="Symbol">))</a>
                <a id="2718" class="Symbol">(</a> <a id="2720" href="category-theory.precategories.html#3056" class="Function">comp-hom-Precat</a> <a id="2736" href="category-theory.natural-transformations-precategories.html#2391" class="Bound">D</a> <a id="2738" class="Symbol">(</a><a id="2739" href="category-theory.natural-transformations-precategories.html#2397" class="Bound">γ</a> <a id="2741" href="category-theory.natural-transformations-precategories.html#2455" class="Bound">y</a><a id="2742" class="Symbol">)</a> <a id="2744" class="Symbol">(</a><a id="2745" href="category-theory.functors-precategories.html#1707" class="Function">hom-functor-Precat</a> <a id="2764" href="category-theory.natural-transformations-precategories.html#2389" class="Bound">C</a> <a id="2766" href="category-theory.natural-transformations-precategories.html#2391" class="Bound">D</a> <a id="2768" href="category-theory.natural-transformations-precategories.html#2393" class="Bound">F</a> <a id="2770" href="category-theory.natural-transformations-precategories.html#2495" class="Bound">f</a><a id="2771" class="Symbol">)))))</a>
</pre>