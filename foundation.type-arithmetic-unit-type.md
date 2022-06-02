# Type arithmetic with the unit type

<pre class="Agda"><a id="47" class="Symbol">{-#</a> <a id="51" class="Keyword">OPTIONS</a> <a id="59" class="Pragma">--without-K</a> <a id="71" class="Pragma">--exact-split</a> <a id="85" class="Symbol">#-}</a>

<a id="90" class="Keyword">module</a> <a id="97" href="foundation.type-arithmetic-unit-type.html" class="Module">foundation.type-arithmetic-unit-type</a> <a id="134" class="Keyword">where</a>

<a id="141" class="Keyword">open</a> <a id="146" class="Keyword">import</a> <a id="153" href="foundation-core.cartesian-product-types.html" class="Module">foundation-core.cartesian-product-types</a> <a id="193" class="Keyword">using</a> <a id="199" class="Symbol">(</a><a id="200" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">_×_</a><a id="203" class="Symbol">)</a>
<a id="205" class="Keyword">open</a> <a id="210" class="Keyword">import</a> <a id="217" href="foundation-core.dependent-pair-types.html" class="Module">foundation-core.dependent-pair-types</a> <a id="254" class="Keyword">using</a> <a id="260" class="Symbol">(</a><a id="261" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="262" class="Symbol">;</a> <a id="264" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="268" class="Symbol">;</a> <a id="270" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="273" class="Symbol">;</a> <a id="275" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="278" class="Symbol">)</a>
<a id="280" class="Keyword">open</a> <a id="285" class="Keyword">import</a> <a id="292" href="foundation-core.equivalences.html" class="Module">foundation-core.equivalences</a> <a id="321" class="Keyword">using</a>
  <a id="329" class="Symbol">(</a> <a id="331" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a><a id="339" class="Symbol">;</a> <a id="341" href="foundation-core.equivalences.html#1607" class="Function Operator">_≃_</a><a id="344" class="Symbol">;</a> <a id="346" href="foundation-core.equivalences.html#2999" class="Function">is-equiv-has-inverse</a><a id="366" class="Symbol">)</a>
<a id="368" class="Keyword">open</a> <a id="373" class="Keyword">import</a> <a id="380" href="foundation-core.functions.html" class="Module">foundation-core.functions</a> <a id="406" class="Keyword">using</a> <a id="412" class="Symbol">(</a><a id="413" href="foundation-core.functions.html#407" class="Function Operator">_∘_</a><a id="416" class="Symbol">;</a> <a id="418" href="foundation-core.functions.html#309" class="Function">id</a><a id="420" class="Symbol">)</a>
<a id="422" class="Keyword">open</a> <a id="427" class="Keyword">import</a> <a id="434" href="foundation-core.homotopies.html" class="Module">foundation-core.homotopies</a> <a id="461" class="Keyword">using</a> <a id="467" class="Symbol">(</a><a id="468" href="foundation-core.homotopies.html#467" class="Function Operator">_~_</a><a id="471" class="Symbol">)</a>
<a id="473" class="Keyword">open</a> <a id="478" class="Keyword">import</a> <a id="485" href="foundation-core.identity-types.html" class="Module">foundation-core.identity-types</a> <a id="516" class="Keyword">using</a> <a id="522" class="Symbol">(</a><a id="523" href="foundation-core.identity-types.html#641" class="Datatype">Id</a><a id="525" class="Symbol">;</a> <a id="527" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a><a id="531" class="Symbol">)</a>
<a id="533" class="Keyword">open</a> <a id="538" class="Keyword">import</a> <a id="545" href="foundation-core.universe-levels.html" class="Module">foundation-core.universe-levels</a> <a id="577" class="Keyword">using</a> <a id="583" class="Symbol">(</a><a id="584" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="589" class="Symbol">;</a> <a id="591" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="593" class="Symbol">)</a>

<a id="596" class="Keyword">open</a> <a id="601" class="Keyword">import</a> <a id="608" href="foundation.unit-type.html" class="Module">foundation.unit-type</a> <a id="629" class="Keyword">using</a> <a id="635" class="Symbol">(</a><a id="636" href="foundation.unit-type.html#1075" class="Datatype">unit</a><a id="640" class="Symbol">;</a> <a id="642" href="foundation.unit-type.html#1099" class="InductiveConstructor">star</a><a id="646" class="Symbol">)</a>
</pre>
## Idea

We prove arithmetical laws involving the unit type

## Laws

### Left unit law for dependent pair types

<pre class="Agda"><a id="775" class="Keyword">module</a> <a id="782" href="foundation.type-arithmetic-unit-type.html#782" class="Module">_</a>
  <a id="786" class="Symbol">{</a><a id="787" href="foundation.type-arithmetic-unit-type.html#787" class="Bound">l</a> <a id="789" class="Symbol">:</a> <a id="791" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="796" class="Symbol">}</a> <a id="798" class="Symbol">(</a><a id="799" href="foundation.type-arithmetic-unit-type.html#799" class="Bound">A</a> <a id="801" class="Symbol">:</a> <a id="803" href="foundation.unit-type.html#1075" class="Datatype">unit</a> <a id="808" class="Symbol">→</a> <a id="810" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="813" href="foundation.type-arithmetic-unit-type.html#787" class="Bound">l</a><a id="814" class="Symbol">)</a>
  <a id="818" class="Keyword">where</a>

  <a id="827" href="foundation.type-arithmetic-unit-type.html#827" class="Function">map-left-unit-law-Σ</a> <a id="847" class="Symbol">:</a> <a id="849" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="851" href="foundation.unit-type.html#1075" class="Datatype">unit</a> <a id="856" href="foundation.type-arithmetic-unit-type.html#799" class="Bound">A</a> <a id="858" class="Symbol">→</a> <a id="860" href="foundation.type-arithmetic-unit-type.html#799" class="Bound">A</a> <a id="862" href="foundation.unit-type.html#1099" class="InductiveConstructor">star</a>
  <a id="869" href="foundation.type-arithmetic-unit-type.html#827" class="Function">map-left-unit-law-Σ</a> <a id="889" class="Symbol">(</a><a id="890" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="895" href="foundation.unit-type.html#1099" class="InductiveConstructor">star</a> <a id="900" href="foundation.type-arithmetic-unit-type.html#900" class="Bound">a</a><a id="901" class="Symbol">)</a> <a id="903" class="Symbol">=</a> <a id="905" href="foundation.type-arithmetic-unit-type.html#900" class="Bound">a</a>

  <a id="910" href="foundation.type-arithmetic-unit-type.html#910" class="Function">map-inv-left-unit-law-Σ</a> <a id="934" class="Symbol">:</a> <a id="936" href="foundation.type-arithmetic-unit-type.html#799" class="Bound">A</a> <a id="938" href="foundation.unit-type.html#1099" class="InductiveConstructor">star</a> <a id="943" class="Symbol">→</a> <a id="945" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="947" href="foundation.unit-type.html#1075" class="Datatype">unit</a> <a id="952" href="foundation.type-arithmetic-unit-type.html#799" class="Bound">A</a>
  <a id="956" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="960" class="Symbol">(</a><a id="961" href="foundation.type-arithmetic-unit-type.html#910" class="Function">map-inv-left-unit-law-Σ</a> <a id="985" href="foundation.type-arithmetic-unit-type.html#985" class="Bound">a</a><a id="986" class="Symbol">)</a> <a id="988" class="Symbol">=</a> <a id="990" href="foundation.unit-type.html#1099" class="InductiveConstructor">star</a>
  <a id="997" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1001" class="Symbol">(</a><a id="1002" href="foundation.type-arithmetic-unit-type.html#910" class="Function">map-inv-left-unit-law-Σ</a> <a id="1026" href="foundation.type-arithmetic-unit-type.html#1026" class="Bound">a</a><a id="1027" class="Symbol">)</a> <a id="1029" class="Symbol">=</a> <a id="1031" href="foundation.type-arithmetic-unit-type.html#1026" class="Bound">a</a>

  <a id="1036" href="foundation.type-arithmetic-unit-type.html#1036" class="Function">issec-map-inv-left-unit-law-Σ</a> <a id="1066" class="Symbol">:</a>
    <a id="1072" class="Symbol">(</a> <a id="1074" href="foundation.type-arithmetic-unit-type.html#827" class="Function">map-left-unit-law-Σ</a> <a id="1094" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="1096" href="foundation.type-arithmetic-unit-type.html#910" class="Function">map-inv-left-unit-law-Σ</a><a id="1119" class="Symbol">)</a> <a id="1121" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="1123" href="foundation-core.functions.html#309" class="Function">id</a>
  <a id="1128" href="foundation.type-arithmetic-unit-type.html#1036" class="Function">issec-map-inv-left-unit-law-Σ</a> <a id="1158" href="foundation.type-arithmetic-unit-type.html#1158" class="Bound">a</a> <a id="1160" class="Symbol">=</a> <a id="1162" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a>

  <a id="1170" href="foundation.type-arithmetic-unit-type.html#1170" class="Function">isretr-map-inv-left-unit-law-Σ</a> <a id="1201" class="Symbol">:</a>
    <a id="1207" class="Symbol">(</a> <a id="1209" href="foundation.type-arithmetic-unit-type.html#910" class="Function">map-inv-left-unit-law-Σ</a> <a id="1233" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="1235" href="foundation.type-arithmetic-unit-type.html#827" class="Function">map-left-unit-law-Σ</a><a id="1254" class="Symbol">)</a> <a id="1256" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="1258" href="foundation-core.functions.html#309" class="Function">id</a>
  <a id="1263" href="foundation.type-arithmetic-unit-type.html#1170" class="Function">isretr-map-inv-left-unit-law-Σ</a> <a id="1294" class="Symbol">(</a><a id="1295" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1300" href="foundation.unit-type.html#1099" class="InductiveConstructor">star</a> <a id="1305" href="foundation.type-arithmetic-unit-type.html#1305" class="Bound">a</a><a id="1306" class="Symbol">)</a> <a id="1308" class="Symbol">=</a> <a id="1310" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a>

  <a id="1318" href="foundation.type-arithmetic-unit-type.html#1318" class="Function">is-equiv-map-left-unit-law-Σ</a> <a id="1347" class="Symbol">:</a> <a id="1349" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a> <a id="1358" href="foundation.type-arithmetic-unit-type.html#827" class="Function">map-left-unit-law-Σ</a>
  <a id="1380" href="foundation.type-arithmetic-unit-type.html#1318" class="Function">is-equiv-map-left-unit-law-Σ</a> <a id="1409" class="Symbol">=</a>
    <a id="1415" href="foundation-core.equivalences.html#2999" class="Function">is-equiv-has-inverse</a>
      <a id="1442" href="foundation.type-arithmetic-unit-type.html#910" class="Function">map-inv-left-unit-law-Σ</a>
      <a id="1472" href="foundation.type-arithmetic-unit-type.html#1036" class="Function">issec-map-inv-left-unit-law-Σ</a>
      <a id="1508" href="foundation.type-arithmetic-unit-type.html#1170" class="Function">isretr-map-inv-left-unit-law-Σ</a>

  <a id="1542" href="foundation.type-arithmetic-unit-type.html#1542" class="Function">left-unit-law-Σ</a> <a id="1558" class="Symbol">:</a> <a id="1560" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="1562" href="foundation.unit-type.html#1075" class="Datatype">unit</a> <a id="1567" href="foundation.type-arithmetic-unit-type.html#799" class="Bound">A</a> <a id="1569" href="foundation-core.equivalences.html#1607" class="Function Operator">≃</a> <a id="1571" href="foundation.type-arithmetic-unit-type.html#799" class="Bound">A</a> <a id="1573" href="foundation.unit-type.html#1099" class="InductiveConstructor">star</a>
  <a id="1580" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1584" href="foundation.type-arithmetic-unit-type.html#1542" class="Function">left-unit-law-Σ</a> <a id="1600" class="Symbol">=</a> <a id="1602" href="foundation.type-arithmetic-unit-type.html#827" class="Function">map-left-unit-law-Σ</a>
  <a id="1624" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1628" href="foundation.type-arithmetic-unit-type.html#1542" class="Function">left-unit-law-Σ</a> <a id="1644" class="Symbol">=</a> <a id="1646" href="foundation.type-arithmetic-unit-type.html#1318" class="Function">is-equiv-map-left-unit-law-Σ</a>
  
  <a id="1680" href="foundation.type-arithmetic-unit-type.html#1680" class="Function">is-equiv-map-inv-left-unit-law-Σ</a> <a id="1713" class="Symbol">:</a> <a id="1715" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a> <a id="1724" href="foundation.type-arithmetic-unit-type.html#910" class="Function">map-inv-left-unit-law-Σ</a>
  <a id="1750" href="foundation.type-arithmetic-unit-type.html#1680" class="Function">is-equiv-map-inv-left-unit-law-Σ</a> <a id="1783" class="Symbol">=</a>
    <a id="1789" href="foundation-core.equivalences.html#2999" class="Function">is-equiv-has-inverse</a>
      <a id="1816" href="foundation.type-arithmetic-unit-type.html#827" class="Function">map-left-unit-law-Σ</a>
      <a id="1842" href="foundation.type-arithmetic-unit-type.html#1170" class="Function">isretr-map-inv-left-unit-law-Σ</a>
      <a id="1879" href="foundation.type-arithmetic-unit-type.html#1036" class="Function">issec-map-inv-left-unit-law-Σ</a>

  <a id="1912" href="foundation.type-arithmetic-unit-type.html#1912" class="Function">inv-left-unit-law-Σ</a> <a id="1932" class="Symbol">:</a> <a id="1934" href="foundation.type-arithmetic-unit-type.html#799" class="Bound">A</a> <a id="1936" href="foundation.unit-type.html#1099" class="InductiveConstructor">star</a> <a id="1941" href="foundation-core.equivalences.html#1607" class="Function Operator">≃</a> <a id="1943" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="1945" href="foundation.unit-type.html#1075" class="Datatype">unit</a> <a id="1950" href="foundation.type-arithmetic-unit-type.html#799" class="Bound">A</a>
  <a id="1954" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1958" href="foundation.type-arithmetic-unit-type.html#1912" class="Function">inv-left-unit-law-Σ</a> <a id="1978" class="Symbol">=</a> <a id="1980" href="foundation.type-arithmetic-unit-type.html#910" class="Function">map-inv-left-unit-law-Σ</a>
  <a id="2006" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="2010" href="foundation.type-arithmetic-unit-type.html#1912" class="Function">inv-left-unit-law-Σ</a> <a id="2030" class="Symbol">=</a> <a id="2032" href="foundation.type-arithmetic-unit-type.html#1680" class="Function">is-equiv-map-inv-left-unit-law-Σ</a>
</pre>
### Left unit law for cartesian products

<pre class="Agda"><a id="2120" class="Keyword">module</a> <a id="2127" href="foundation.type-arithmetic-unit-type.html#2127" class="Module">_</a>
  <a id="2131" class="Symbol">{</a><a id="2132" href="foundation.type-arithmetic-unit-type.html#2132" class="Bound">l</a> <a id="2134" class="Symbol">:</a> <a id="2136" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2141" class="Symbol">}</a> <a id="2143" class="Symbol">{</a><a id="2144" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a> <a id="2146" class="Symbol">:</a> <a id="2148" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2151" href="foundation.type-arithmetic-unit-type.html#2132" class="Bound">l</a><a id="2152" class="Symbol">}</a>
  <a id="2156" class="Keyword">where</a>

  <a id="2165" href="foundation.type-arithmetic-unit-type.html#2165" class="Function">map-left-unit-law-prod</a> <a id="2188" class="Symbol">:</a> <a id="2190" href="foundation.unit-type.html#1075" class="Datatype">unit</a> <a id="2195" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">×</a> <a id="2197" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a> <a id="2199" class="Symbol">→</a> <a id="2201" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a>
  <a id="2205" href="foundation.type-arithmetic-unit-type.html#2165" class="Function">map-left-unit-law-prod</a> <a id="2228" class="Symbol">=</a> <a id="2230" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a>

  <a id="2237" href="foundation.type-arithmetic-unit-type.html#2237" class="Function">map-inv-left-unit-law-prod</a> <a id="2264" class="Symbol">:</a> <a id="2266" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a> <a id="2268" class="Symbol">→</a> <a id="2270" href="foundation.unit-type.html#1075" class="Datatype">unit</a> <a id="2275" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">×</a> <a id="2277" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a>
  <a id="2281" href="foundation.type-arithmetic-unit-type.html#2237" class="Function">map-inv-left-unit-law-prod</a> <a id="2308" class="Symbol">=</a> <a id="2310" href="foundation.type-arithmetic-unit-type.html#910" class="Function">map-inv-left-unit-law-Σ</a> <a id="2334" class="Symbol">(λ</a> <a id="2337" href="foundation.type-arithmetic-unit-type.html#2337" class="Bound">x</a> <a id="2339" class="Symbol">→</a> <a id="2341" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a><a id="2342" class="Symbol">)</a>

  <a id="2347" href="foundation.type-arithmetic-unit-type.html#2347" class="Function">issec-map-inv-left-unit-law-prod</a> <a id="2380" class="Symbol">:</a>
    <a id="2386" class="Symbol">(</a> <a id="2388" href="foundation.type-arithmetic-unit-type.html#2165" class="Function">map-left-unit-law-prod</a> <a id="2411" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="2413" href="foundation.type-arithmetic-unit-type.html#2237" class="Function">map-inv-left-unit-law-prod</a><a id="2439" class="Symbol">)</a> <a id="2441" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="2443" href="foundation-core.functions.html#309" class="Function">id</a>
  <a id="2448" href="foundation.type-arithmetic-unit-type.html#2347" class="Function">issec-map-inv-left-unit-law-prod</a> <a id="2481" class="Symbol">=</a>
    <a id="2487" href="foundation.type-arithmetic-unit-type.html#1036" class="Function">issec-map-inv-left-unit-law-Σ</a> <a id="2517" class="Symbol">(λ</a> <a id="2520" href="foundation.type-arithmetic-unit-type.html#2520" class="Bound">x</a> <a id="2522" class="Symbol">→</a> <a id="2524" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a><a id="2525" class="Symbol">)</a>

  <a id="2530" href="foundation.type-arithmetic-unit-type.html#2530" class="Function">isretr-map-inv-left-unit-law-prod</a> <a id="2564" class="Symbol">:</a>
    <a id="2570" class="Symbol">(</a> <a id="2572" href="foundation.type-arithmetic-unit-type.html#2237" class="Function">map-inv-left-unit-law-prod</a> <a id="2599" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="2601" href="foundation.type-arithmetic-unit-type.html#2165" class="Function">map-left-unit-law-prod</a><a id="2623" class="Symbol">)</a> <a id="2625" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="2627" href="foundation-core.functions.html#309" class="Function">id</a>
  <a id="2632" href="foundation.type-arithmetic-unit-type.html#2530" class="Function">isretr-map-inv-left-unit-law-prod</a> <a id="2666" class="Symbol">(</a><a id="2667" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="2672" href="foundation.unit-type.html#1099" class="InductiveConstructor">star</a> <a id="2677" href="foundation.type-arithmetic-unit-type.html#2677" class="Bound">a</a><a id="2678" class="Symbol">)</a> <a id="2680" class="Symbol">=</a> <a id="2682" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a>

  <a id="2690" href="foundation.type-arithmetic-unit-type.html#2690" class="Function">is-equiv-map-left-unit-law-prod</a> <a id="2722" class="Symbol">:</a> <a id="2724" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a> <a id="2733" href="foundation.type-arithmetic-unit-type.html#2165" class="Function">map-left-unit-law-prod</a>
  <a id="2758" href="foundation.type-arithmetic-unit-type.html#2690" class="Function">is-equiv-map-left-unit-law-prod</a> <a id="2790" class="Symbol">=</a>
    <a id="2796" href="foundation-core.equivalences.html#2999" class="Function">is-equiv-has-inverse</a>
      <a id="2823" href="foundation.type-arithmetic-unit-type.html#2237" class="Function">map-inv-left-unit-law-prod</a>
      <a id="2856" href="foundation.type-arithmetic-unit-type.html#2347" class="Function">issec-map-inv-left-unit-law-prod</a>
      <a id="2895" href="foundation.type-arithmetic-unit-type.html#2530" class="Function">isretr-map-inv-left-unit-law-prod</a>

  <a id="2932" href="foundation.type-arithmetic-unit-type.html#2932" class="Function">left-unit-law-prod</a> <a id="2951" class="Symbol">:</a> <a id="2953" class="Symbol">(</a><a id="2954" href="foundation.unit-type.html#1075" class="Datatype">unit</a> <a id="2959" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">×</a> <a id="2961" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a><a id="2962" class="Symbol">)</a> <a id="2964" href="foundation-core.equivalences.html#1607" class="Function Operator">≃</a> <a id="2966" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a>
  <a id="2970" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="2974" href="foundation.type-arithmetic-unit-type.html#2932" class="Function">left-unit-law-prod</a> <a id="2993" class="Symbol">=</a> <a id="2995" href="foundation.type-arithmetic-unit-type.html#2165" class="Function">map-left-unit-law-prod</a>
  <a id="3020" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="3024" href="foundation.type-arithmetic-unit-type.html#2932" class="Function">left-unit-law-prod</a> <a id="3043" class="Symbol">=</a> <a id="3045" href="foundation.type-arithmetic-unit-type.html#2690" class="Function">is-equiv-map-left-unit-law-prod</a>

  <a id="3080" href="foundation.type-arithmetic-unit-type.html#3080" class="Function">is-equiv-map-inv-left-unit-law-prod</a> <a id="3116" class="Symbol">:</a> <a id="3118" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a> <a id="3127" href="foundation.type-arithmetic-unit-type.html#2237" class="Function">map-inv-left-unit-law-prod</a>
  <a id="3156" href="foundation.type-arithmetic-unit-type.html#3080" class="Function">is-equiv-map-inv-left-unit-law-prod</a> <a id="3192" class="Symbol">=</a>
    <a id="3198" href="foundation-core.equivalences.html#2999" class="Function">is-equiv-has-inverse</a>
      <a id="3225" href="foundation.type-arithmetic-unit-type.html#2165" class="Function">map-left-unit-law-prod</a>
      <a id="3254" href="foundation.type-arithmetic-unit-type.html#2530" class="Function">isretr-map-inv-left-unit-law-prod</a>
      <a id="3294" href="foundation.type-arithmetic-unit-type.html#2347" class="Function">issec-map-inv-left-unit-law-prod</a>

  <a id="3330" href="foundation.type-arithmetic-unit-type.html#3330" class="Function">inv-left-unit-law-prod</a> <a id="3353" class="Symbol">:</a> <a id="3355" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a> <a id="3357" href="foundation-core.equivalences.html#1607" class="Function Operator">≃</a> <a id="3359" class="Symbol">(</a><a id="3360" href="foundation.unit-type.html#1075" class="Datatype">unit</a> <a id="3365" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">×</a> <a id="3367" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a><a id="3368" class="Symbol">)</a>
  <a id="3372" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="3376" href="foundation.type-arithmetic-unit-type.html#3330" class="Function">inv-left-unit-law-prod</a> <a id="3399" class="Symbol">=</a> <a id="3401" href="foundation.type-arithmetic-unit-type.html#2237" class="Function">map-inv-left-unit-law-prod</a>
  <a id="3430" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="3434" href="foundation.type-arithmetic-unit-type.html#3330" class="Function">inv-left-unit-law-prod</a> <a id="3457" class="Symbol">=</a> <a id="3459" href="foundation.type-arithmetic-unit-type.html#3080" class="Function">is-equiv-map-inv-left-unit-law-prod</a>
</pre>
### The right unit law for cartesian products

<pre class="Agda">  <a id="3557" href="foundation.type-arithmetic-unit-type.html#3557" class="Function">map-right-unit-law-prod</a> <a id="3581" class="Symbol">:</a> <a id="3583" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a> <a id="3585" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">×</a> <a id="3587" href="foundation.unit-type.html#1075" class="Datatype">unit</a> <a id="3592" class="Symbol">→</a> <a id="3594" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a>
  <a id="3598" href="foundation.type-arithmetic-unit-type.html#3557" class="Function">map-right-unit-law-prod</a> <a id="3622" class="Symbol">=</a> <a id="3624" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a>

  <a id="3631" href="foundation.type-arithmetic-unit-type.html#3631" class="Function">map-inv-right-unit-law-prod</a> <a id="3659" class="Symbol">:</a> <a id="3661" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a> <a id="3663" class="Symbol">→</a> <a id="3665" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a> <a id="3667" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">×</a> <a id="3669" href="foundation.unit-type.html#1075" class="Datatype">unit</a>
  <a id="3676" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="3680" class="Symbol">(</a><a id="3681" href="foundation.type-arithmetic-unit-type.html#3631" class="Function">map-inv-right-unit-law-prod</a> <a id="3709" href="foundation.type-arithmetic-unit-type.html#3709" class="Bound">a</a><a id="3710" class="Symbol">)</a> <a id="3712" class="Symbol">=</a> <a id="3714" href="foundation.type-arithmetic-unit-type.html#3709" class="Bound">a</a>
  <a id="3718" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="3722" class="Symbol">(</a><a id="3723" href="foundation.type-arithmetic-unit-type.html#3631" class="Function">map-inv-right-unit-law-prod</a> <a id="3751" href="foundation.type-arithmetic-unit-type.html#3751" class="Bound">a</a><a id="3752" class="Symbol">)</a> <a id="3754" class="Symbol">=</a> <a id="3756" href="foundation.unit-type.html#1099" class="InductiveConstructor">star</a>

  <a id="3764" href="foundation.type-arithmetic-unit-type.html#3764" class="Function">issec-map-inv-right-unit-law-prod</a> <a id="3798" class="Symbol">:</a>
    <a id="3804" class="Symbol">(</a><a id="3805" href="foundation.type-arithmetic-unit-type.html#3557" class="Function">map-right-unit-law-prod</a> <a id="3829" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="3831" href="foundation.type-arithmetic-unit-type.html#3631" class="Function">map-inv-right-unit-law-prod</a><a id="3858" class="Symbol">)</a> <a id="3860" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="3862" href="foundation-core.functions.html#309" class="Function">id</a>
  <a id="3867" href="foundation.type-arithmetic-unit-type.html#3764" class="Function">issec-map-inv-right-unit-law-prod</a> <a id="3901" href="foundation.type-arithmetic-unit-type.html#3901" class="Bound">a</a> <a id="3903" class="Symbol">=</a> <a id="3905" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a>

  <a id="3913" href="foundation.type-arithmetic-unit-type.html#3913" class="Function">isretr-map-inv-right-unit-law-prod</a> <a id="3948" class="Symbol">:</a>
    <a id="3954" class="Symbol">(</a><a id="3955" href="foundation.type-arithmetic-unit-type.html#3631" class="Function">map-inv-right-unit-law-prod</a> <a id="3983" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="3985" href="foundation.type-arithmetic-unit-type.html#3557" class="Function">map-right-unit-law-prod</a><a id="4008" class="Symbol">)</a> <a id="4010" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="4012" href="foundation-core.functions.html#309" class="Function">id</a>
  <a id="4017" href="foundation.type-arithmetic-unit-type.html#3913" class="Function">isretr-map-inv-right-unit-law-prod</a> <a id="4052" class="Symbol">(</a><a id="4053" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="4058" href="foundation.type-arithmetic-unit-type.html#4058" class="Bound">a</a> <a id="4060" href="foundation.unit-type.html#1099" class="InductiveConstructor">star</a><a id="4064" class="Symbol">)</a> <a id="4066" class="Symbol">=</a> <a id="4068" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a>

  <a id="4076" href="foundation.type-arithmetic-unit-type.html#4076" class="Function">is-equiv-map-right-unit-law-prod</a> <a id="4109" class="Symbol">:</a> <a id="4111" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a> <a id="4120" href="foundation.type-arithmetic-unit-type.html#3557" class="Function">map-right-unit-law-prod</a>
  <a id="4146" href="foundation.type-arithmetic-unit-type.html#4076" class="Function">is-equiv-map-right-unit-law-prod</a> <a id="4179" class="Symbol">=</a>
    <a id="4185" href="foundation-core.equivalences.html#2999" class="Function">is-equiv-has-inverse</a>
      <a id="4212" href="foundation.type-arithmetic-unit-type.html#3631" class="Function">map-inv-right-unit-law-prod</a>
      <a id="4246" href="foundation.type-arithmetic-unit-type.html#3764" class="Function">issec-map-inv-right-unit-law-prod</a>
      <a id="4286" href="foundation.type-arithmetic-unit-type.html#3913" class="Function">isretr-map-inv-right-unit-law-prod</a>

  <a id="4324" href="foundation.type-arithmetic-unit-type.html#4324" class="Function">right-unit-law-prod</a> <a id="4344" class="Symbol">:</a> <a id="4346" class="Symbol">(</a><a id="4347" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a> <a id="4349" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">×</a> <a id="4351" href="foundation.unit-type.html#1075" class="Datatype">unit</a><a id="4355" class="Symbol">)</a> <a id="4357" href="foundation-core.equivalences.html#1607" class="Function Operator">≃</a> <a id="4359" href="foundation.type-arithmetic-unit-type.html#2144" class="Bound">A</a>
  <a id="4363" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="4367" href="foundation.type-arithmetic-unit-type.html#4324" class="Function">right-unit-law-prod</a> <a id="4387" class="Symbol">=</a> <a id="4389" href="foundation.type-arithmetic-unit-type.html#3557" class="Function">map-right-unit-law-prod</a>
  <a id="4415" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="4419" href="foundation.type-arithmetic-unit-type.html#4324" class="Function">right-unit-law-prod</a> <a id="4439" class="Symbol">=</a> <a id="4441" href="foundation.type-arithmetic-unit-type.html#4076" class="Function">is-equiv-map-right-unit-law-prod</a>
</pre>