# The universal property of truncations

<pre class="Agda"><a id="50" class="Symbol">{-#</a> <a id="54" class="Keyword">OPTIONS</a> <a id="62" class="Pragma">--without-K</a> <a id="74" class="Pragma">--exact-split</a> <a id="88" class="Symbol">#-}</a>

<a id="93" class="Keyword">module</a> <a id="100" href="foundation.universal-property-truncation.html" class="Module">foundation.universal-property-truncation</a> <a id="141" class="Keyword">where</a>

<a id="148" class="Keyword">open</a> <a id="153" class="Keyword">import</a> <a id="160" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a> <a id="190" class="Keyword">using</a>
  <a id="198" class="Symbol">(</a> <a id="200" href="foundation-core.contractible-types.html#992" class="Function">is-contr</a><a id="208" class="Symbol">;</a> <a id="210" href="foundation-core.contractible-types.html#3297" class="Function">is-contr-equiv</a><a id="224" class="Symbol">;</a> <a id="226" href="foundation-core.contractible-types.html#3806" class="Function">is-contr-equiv&#39;</a><a id="241" class="Symbol">;</a> <a id="243" href="foundation-core.contractible-types.html#1085" class="Function">center</a><a id="249" class="Symbol">)</a>
<a id="251" class="Keyword">open</a> <a id="256" class="Keyword">import</a> <a id="263" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="295" class="Keyword">using</a> <a id="301" class="Symbol">(</a><a id="302" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="303" class="Symbol">;</a> <a id="305" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="309" class="Symbol">;</a> <a id="311" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="314" class="Symbol">;</a> <a id="316" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="319" class="Symbol">;</a> <a id="321" href="foundation-core.dependent-pair-types.html#687" class="Function">ind-Σ</a><a id="326" class="Symbol">)</a>
<a id="328" class="Keyword">open</a> <a id="333" class="Keyword">import</a>
  <a id="342" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html" class="Module">foundation.distributivity-of-dependent-functions-over-dependent-pairs</a> <a id="412" class="Keyword">using</a>
  <a id="420" class="Symbol">(</a> <a id="422" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html#5106" class="Function">inv-distributive-Π-Σ</a><a id="442" class="Symbol">;</a> <a id="444" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html#2808" class="Function">map-distributive-Π-Σ</a><a id="464" class="Symbol">)</a>
<a id="466" class="Keyword">open</a> <a id="471" class="Keyword">import</a> <a id="478" href="foundation.equivalences.html" class="Module">foundation.equivalences</a> <a id="502" class="Keyword">using</a>
  <a id="510" class="Symbol">(</a> <a id="512" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a><a id="520" class="Symbol">;</a> <a id="522" href="foundation-core.equivalences.html#12785" class="Function">is-equiv-equiv</a><a id="536" class="Symbol">;</a> <a id="538" href="foundation-core.equivalences.html#4173" class="Function">map-inv-is-equiv</a><a id="554" class="Symbol">;</a> <a id="556" href="foundation.equivalences.html#7869" class="Function">is-equiv-precomp-is-equiv</a><a id="581" class="Symbol">;</a>
    <a id="587" href="foundation-core.equivalences.html#2309" class="Function">is-equiv-id</a><a id="598" class="Symbol">;</a> <a id="600" href="foundation-core.equivalences.html#1607" class="Function Operator">_≃_</a><a id="603" class="Symbol">;</a> <a id="605" href="foundation-core.equivalences.html#1807" class="Function">map-equiv</a><a id="614" class="Symbol">;</a> <a id="616" href="foundation-core.equivalences.html#1862" class="Function">is-equiv-map-equiv</a><a id="634" class="Symbol">)</a>
<a id="636" class="Keyword">open</a> <a id="641" class="Keyword">import</a> <a id="648" href="foundation.function-extensionality.html" class="Module">foundation.function-extensionality</a> <a id="683" class="Keyword">using</a> <a id="689" class="Symbol">(</a><a id="690" href="foundation-core.function-extensionality.html#1301" class="Function">equiv-funext</a><a id="702" class="Symbol">)</a>
<a id="704" class="Keyword">open</a> <a id="709" class="Keyword">import</a> <a id="716" href="foundation.functions.html" class="Module">foundation.functions</a> <a id="737" class="Keyword">using</a> <a id="743" class="Symbol">(</a><a id="744" href="foundation-core.functions.html#925" class="Function">precomp</a><a id="751" class="Symbol">;</a> <a id="753" href="foundation-core.functions.html#407" class="Function Operator">_∘_</a><a id="756" class="Symbol">;</a> <a id="758" href="foundation-core.functions.html#309" class="Function">id</a><a id="760" class="Symbol">)</a>
<a id="762" class="Keyword">open</a> <a id="767" class="Keyword">import</a> <a id="774" href="foundation.homotopies.html" class="Module">foundation.homotopies</a> <a id="796" class="Keyword">using</a> <a id="802" class="Symbol">(</a><a id="803" href="foundation-core.homotopies.html#467" class="Function Operator">_~_</a><a id="806" class="Symbol">)</a>
<a id="808" class="Keyword">open</a> <a id="813" class="Keyword">import</a> <a id="820" href="foundation.identity-types.html" class="Module">foundation.identity-types</a> <a id="846" class="Keyword">using</a> <a id="852" class="Symbol">(</a><a id="853" href="foundation-core.identity-types.html#641" class="Datatype">Id</a><a id="855" class="Symbol">;</a> <a id="857" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a><a id="861" class="Symbol">;</a> <a id="863" href="foundation-core.identity-types.html#1552" class="Function">inv</a><a id="866" class="Symbol">)</a>
<a id="868" class="Keyword">open</a> <a id="873" class="Keyword">import</a> <a id="880" href="foundation.sections.html" class="Module">foundation.sections</a> <a id="900" class="Keyword">using</a> <a id="906" class="Symbol">(</a><a id="907" href="foundation-core.sections.html#521" class="Function">sec</a><a id="910" class="Symbol">)</a>
<a id="912" class="Keyword">open</a> <a id="917" class="Keyword">import</a> <a id="924" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a> <a id="951" class="Keyword">using</a>
  <a id="959" class="Symbol">(</a> <a id="961" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a><a id="975" class="Symbol">;</a> <a id="977" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a><a id="996" class="Symbol">;</a> <a id="998" href="foundation-core.truncated-types.html#10684" class="Function">type-hom-Truncated-Type</a><a id="1021" class="Symbol">;</a>
    <a id="1027" href="foundation-core.truncated-types.html#6283" class="Function">Σ-Truncated-Type</a><a id="1043" class="Symbol">;</a> <a id="1045" href="foundation-core.truncated-types.html#6657" class="Function">fib-Truncated-Type</a><a id="1063" class="Symbol">;</a> <a id="1065" href="foundation-core.truncated-types.html#1727" class="Function">is-trunc</a><a id="1073" class="Symbol">)</a>
<a id="1075" class="Keyword">open</a> <a id="1080" class="Keyword">import</a> <a id="1087" href="foundation-core.truncation-levels.html" class="Module">foundation-core.truncation-levels</a> <a id="1121" class="Keyword">using</a> <a id="1127" class="Symbol">(</a><a id="1128" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="1129" class="Symbol">)</a>
<a id="1131" class="Keyword">open</a> <a id="1136" class="Keyword">import</a> <a id="1143" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="1170" class="Keyword">using</a> <a id="1176" class="Symbol">(</a><a id="1177" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="1179" class="Symbol">;</a> <a id="1181" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1186" class="Symbol">;</a> <a id="1188" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="1191" class="Symbol">;</a> <a id="1193" href="Agda.Primitive.html#780" class="Primitive">lsuc</a><a id="1197" class="Symbol">)</a>

<a id="1200" class="Keyword">open</a> <a id="1205" class="Keyword">import</a> <a id="1212" href="foundation-core.contractible-maps.html" class="Module">foundation-core.contractible-maps</a> <a id="1246" class="Keyword">using</a>
  <a id="1254" class="Symbol">(</a> <a id="1256" href="foundation-core.contractible-maps.html#2368" class="Function">is-equiv-is-contr-map</a><a id="1277" class="Symbol">;</a> <a id="1279" href="foundation-core.contractible-maps.html#3850" class="Function">is-contr-map-is-equiv</a><a id="1300" class="Symbol">)</a>
<a id="1302" class="Keyword">open</a> <a id="1307" class="Keyword">import</a> <a id="1314" href="foundation-core.functoriality-dependent-pair-types.html" class="Module">foundation-core.functoriality-dependent-pair-types</a> <a id="1365" class="Keyword">using</a>
  <a id="1373" class="Symbol">(</a> <a id="1375" href="foundation-core.functoriality-dependent-pair-types.html#6804" class="Function">equiv-tot</a><a id="1384" class="Symbol">;</a> <a id="1386" href="foundation-core.functoriality-dependent-pair-types.html#10750" class="Function">is-fiberwise-equiv-is-equiv-map-Σ</a><a id="1419" class="Symbol">)</a>
</pre>
## Idea

We say that a map `f : A → B` into a `k`-truncated type `B` is a `k`-truncation of `A` -- or that it satisfies the universal property of the `k`-truncation of `A` -- if any map `g : A → C` into a `k`-truncated type `C` extends uniquely along `f` to a map `B → C`.

## Definition

### The condition on a map to be a truncation

<pre class="Agda"><a id="precomp-Trunc"></a><a id="1770" href="foundation.universal-property-truncation.html#1770" class="Function">precomp-Trunc</a> <a id="1784" class="Symbol">:</a>
  <a id="1788" class="Symbol">{</a><a id="1789" href="foundation.universal-property-truncation.html#1789" class="Bound">l1</a> <a id="1792" href="foundation.universal-property-truncation.html#1792" class="Bound">l2</a> <a id="1795" href="foundation.universal-property-truncation.html#1795" class="Bound">l3</a> <a id="1798" class="Symbol">:</a> <a id="1800" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1805" class="Symbol">}</a> <a id="1807" class="Symbol">{</a><a id="1808" href="foundation.universal-property-truncation.html#1808" class="Bound">k</a> <a id="1810" class="Symbol">:</a> <a id="1812" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="1813" class="Symbol">}</a> <a id="1815" class="Symbol">{</a><a id="1816" href="foundation.universal-property-truncation.html#1816" class="Bound">A</a> <a id="1818" class="Symbol">:</a> <a id="1820" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1823" href="foundation.universal-property-truncation.html#1789" class="Bound">l1</a><a id="1825" class="Symbol">}</a> <a id="1827" class="Symbol">{</a><a id="1828" href="foundation.universal-property-truncation.html#1828" class="Bound">B</a> <a id="1830" class="Symbol">:</a> <a id="1832" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1835" href="foundation.universal-property-truncation.html#1792" class="Bound">l2</a><a id="1837" class="Symbol">}</a> <a id="1839" class="Symbol">(</a><a id="1840" href="foundation.universal-property-truncation.html#1840" class="Bound">f</a> <a id="1842" class="Symbol">:</a> <a id="1844" href="foundation.universal-property-truncation.html#1816" class="Bound">A</a> <a id="1846" class="Symbol">→</a> <a id="1848" href="foundation.universal-property-truncation.html#1828" class="Bound">B</a><a id="1849" class="Symbol">)</a>
  <a id="1853" class="Symbol">(</a><a id="1854" href="foundation.universal-property-truncation.html#1854" class="Bound">C</a> <a id="1856" class="Symbol">:</a> <a id="1858" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="1873" href="foundation.universal-property-truncation.html#1795" class="Bound">l3</a> <a id="1876" href="foundation.universal-property-truncation.html#1808" class="Bound">k</a><a id="1877" class="Symbol">)</a> <a id="1879" class="Symbol">→</a>
  <a id="1883" class="Symbol">(</a><a id="1884" href="foundation.universal-property-truncation.html#1828" class="Bound">B</a> <a id="1886" class="Symbol">→</a> <a id="1888" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="1908" href="foundation.universal-property-truncation.html#1854" class="Bound">C</a><a id="1909" class="Symbol">)</a> <a id="1911" class="Symbol">→</a> <a id="1913" class="Symbol">(</a><a id="1914" href="foundation.universal-property-truncation.html#1816" class="Bound">A</a> <a id="1916" class="Symbol">→</a> <a id="1918" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="1938" href="foundation.universal-property-truncation.html#1854" class="Bound">C</a><a id="1939" class="Symbol">)</a>
<a id="1941" href="foundation.universal-property-truncation.html#1770" class="Function">precomp-Trunc</a> <a id="1955" href="foundation.universal-property-truncation.html#1955" class="Bound">f</a> <a id="1957" href="foundation.universal-property-truncation.html#1957" class="Bound">C</a> <a id="1959" class="Symbol">=</a> <a id="1961" href="foundation-core.functions.html#925" class="Function">precomp</a> <a id="1969" href="foundation.universal-property-truncation.html#1955" class="Bound">f</a> <a id="1971" class="Symbol">(</a><a id="1972" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="1992" href="foundation.universal-property-truncation.html#1957" class="Bound">C</a><a id="1993" class="Symbol">)</a>

<a id="is-truncation"></a><a id="1996" href="foundation.universal-property-truncation.html#1996" class="Function">is-truncation</a> <a id="2010" class="Symbol">:</a>
  <a id="2014" class="Symbol">{</a><a id="2015" href="foundation.universal-property-truncation.html#2015" class="Bound">l1</a> <a id="2018" href="foundation.universal-property-truncation.html#2018" class="Bound">l2</a> <a id="2021" class="Symbol">:</a> <a id="2023" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2028" class="Symbol">}</a> <a id="2030" class="Symbol">(</a><a id="2031" href="foundation.universal-property-truncation.html#2031" class="Bound">l</a> <a id="2033" class="Symbol">:</a> <a id="2035" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2040" class="Symbol">)</a> <a id="2042" class="Symbol">{</a><a id="2043" href="foundation.universal-property-truncation.html#2043" class="Bound">k</a> <a id="2045" class="Symbol">:</a> <a id="2047" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="2048" class="Symbol">}</a> <a id="2050" class="Symbol">{</a><a id="2051" href="foundation.universal-property-truncation.html#2051" class="Bound">A</a> <a id="2053" class="Symbol">:</a> <a id="2055" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2058" href="foundation.universal-property-truncation.html#2015" class="Bound">l1</a><a id="2060" class="Symbol">}</a>
  <a id="2064" class="Symbol">(</a><a id="2065" href="foundation.universal-property-truncation.html#2065" class="Bound">B</a> <a id="2067" class="Symbol">:</a> <a id="2069" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="2084" href="foundation.universal-property-truncation.html#2018" class="Bound">l2</a> <a id="2087" href="foundation.universal-property-truncation.html#2043" class="Bound">k</a><a id="2088" class="Symbol">)</a> <a id="2090" class="Symbol">→</a> <a id="2092" class="Symbol">(</a><a id="2093" href="foundation.universal-property-truncation.html#2051" class="Bound">A</a> <a id="2095" class="Symbol">→</a> <a id="2097" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="2117" href="foundation.universal-property-truncation.html#2065" class="Bound">B</a><a id="2118" class="Symbol">)</a> <a id="2120" class="Symbol">→</a>
  <a id="2124" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2127" class="Symbol">(</a><a id="2128" href="foundation.universal-property-truncation.html#2015" class="Bound">l1</a> <a id="2131" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="2133" href="foundation.universal-property-truncation.html#2018" class="Bound">l2</a> <a id="2136" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="2138" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="2143" href="foundation.universal-property-truncation.html#2031" class="Bound">l</a><a id="2144" class="Symbol">)</a>
<a id="2146" href="foundation.universal-property-truncation.html#1996" class="Function">is-truncation</a> <a id="2160" href="foundation.universal-property-truncation.html#2160" class="Bound">l</a> <a id="2162" class="Symbol">{</a><a id="2163" href="foundation.universal-property-truncation.html#2163" class="Bound">k</a><a id="2164" class="Symbol">}</a> <a id="2166" href="foundation.universal-property-truncation.html#2166" class="Bound">B</a> <a id="2168" href="foundation.universal-property-truncation.html#2168" class="Bound">f</a> <a id="2170" class="Symbol">=</a>
  <a id="2174" class="Symbol">(</a><a id="2175" href="foundation.universal-property-truncation.html#2175" class="Bound">C</a> <a id="2177" class="Symbol">:</a> <a id="2179" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="2194" href="foundation.universal-property-truncation.html#2160" class="Bound">l</a> <a id="2196" href="foundation.universal-property-truncation.html#2163" class="Bound">k</a><a id="2197" class="Symbol">)</a> <a id="2199" class="Symbol">→</a> <a id="2201" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a> <a id="2210" class="Symbol">(</a><a id="2211" href="foundation.universal-property-truncation.html#1770" class="Function">precomp-Trunc</a> <a id="2225" href="foundation.universal-property-truncation.html#2168" class="Bound">f</a> <a id="2227" href="foundation.universal-property-truncation.html#2175" class="Bound">C</a><a id="2228" class="Symbol">)</a>
</pre>
### The universal property of truncations

<pre class="Agda"><a id="universal-property-truncation"></a><a id="2286" href="foundation.universal-property-truncation.html#2286" class="Function">universal-property-truncation</a> <a id="2316" class="Symbol">:</a>
  <a id="2320" class="Symbol">(</a><a id="2321" href="foundation.universal-property-truncation.html#2321" class="Bound">l</a> <a id="2323" class="Symbol">:</a> <a id="2325" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2330" class="Symbol">)</a> <a id="2332" class="Symbol">{</a><a id="2333" href="foundation.universal-property-truncation.html#2333" class="Bound">l1</a> <a id="2336" href="foundation.universal-property-truncation.html#2336" class="Bound">l2</a> <a id="2339" class="Symbol">:</a> <a id="2341" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2346" class="Symbol">}</a> <a id="2348" class="Symbol">{</a><a id="2349" href="foundation.universal-property-truncation.html#2349" class="Bound">k</a> <a id="2351" class="Symbol">:</a> <a id="2353" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="2354" class="Symbol">}</a> <a id="2356" class="Symbol">{</a><a id="2357" href="foundation.universal-property-truncation.html#2357" class="Bound">A</a> <a id="2359" class="Symbol">:</a> <a id="2361" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2364" href="foundation.universal-property-truncation.html#2333" class="Bound">l1</a><a id="2366" class="Symbol">}</a>
  <a id="2370" class="Symbol">(</a><a id="2371" href="foundation.universal-property-truncation.html#2371" class="Bound">B</a> <a id="2373" class="Symbol">:</a> <a id="2375" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="2390" href="foundation.universal-property-truncation.html#2336" class="Bound">l2</a> <a id="2393" href="foundation.universal-property-truncation.html#2349" class="Bound">k</a><a id="2394" class="Symbol">)</a> <a id="2396" class="Symbol">(</a><a id="2397" href="foundation.universal-property-truncation.html#2397" class="Bound">f</a> <a id="2399" class="Symbol">:</a> <a id="2401" href="foundation.universal-property-truncation.html#2357" class="Bound">A</a> <a id="2403" class="Symbol">→</a> <a id="2405" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="2425" href="foundation.universal-property-truncation.html#2371" class="Bound">B</a><a id="2426" class="Symbol">)</a> <a id="2428" class="Symbol">→</a>
  <a id="2432" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2435" class="Symbol">(</a><a id="2436" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="2441" href="foundation.universal-property-truncation.html#2321" class="Bound">l</a> <a id="2443" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="2445" href="foundation.universal-property-truncation.html#2333" class="Bound">l1</a> <a id="2448" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="2450" href="foundation.universal-property-truncation.html#2336" class="Bound">l2</a><a id="2452" class="Symbol">)</a>
<a id="2454" href="foundation.universal-property-truncation.html#2286" class="Function">universal-property-truncation</a> <a id="2484" href="foundation.universal-property-truncation.html#2484" class="Bound">l</a> <a id="2486" class="Symbol">{</a><a id="2487" class="Argument">k</a> <a id="2489" class="Symbol">=</a> <a id="2491" href="foundation.universal-property-truncation.html#2491" class="Bound">k</a><a id="2492" class="Symbol">}</a> <a id="2494" class="Symbol">{</a><a id="2495" href="foundation.universal-property-truncation.html#2495" class="Bound">A</a><a id="2496" class="Symbol">}</a> <a id="2498" href="foundation.universal-property-truncation.html#2498" class="Bound">B</a> <a id="2500" href="foundation.universal-property-truncation.html#2500" class="Bound">f</a> <a id="2502" class="Symbol">=</a>
  <a id="2506" class="Symbol">(</a><a id="2507" href="foundation.universal-property-truncation.html#2507" class="Bound">C</a> <a id="2509" class="Symbol">:</a> <a id="2511" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="2526" href="foundation.universal-property-truncation.html#2484" class="Bound">l</a> <a id="2528" href="foundation.universal-property-truncation.html#2491" class="Bound">k</a><a id="2529" class="Symbol">)</a> <a id="2531" class="Symbol">(</a><a id="2532" href="foundation.universal-property-truncation.html#2532" class="Bound">g</a> <a id="2534" class="Symbol">:</a> <a id="2536" href="foundation.universal-property-truncation.html#2495" class="Bound">A</a> <a id="2538" class="Symbol">→</a> <a id="2540" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="2560" href="foundation.universal-property-truncation.html#2507" class="Bound">C</a><a id="2561" class="Symbol">)</a> <a id="2563" class="Symbol">→</a>
  <a id="2567" href="foundation-core.contractible-types.html#992" class="Function">is-contr</a> <a id="2576" class="Symbol">(</a><a id="2577" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="2579" class="Symbol">(</a><a id="2580" href="foundation-core.truncated-types.html#10684" class="Function">type-hom-Truncated-Type</a> <a id="2604" href="foundation.universal-property-truncation.html#2491" class="Bound">k</a> <a id="2606" href="foundation.universal-property-truncation.html#2498" class="Bound">B</a> <a id="2608" href="foundation.universal-property-truncation.html#2507" class="Bound">C</a><a id="2609" class="Symbol">)</a> <a id="2611" class="Symbol">(λ</a> <a id="2614" href="foundation.universal-property-truncation.html#2614" class="Bound">h</a> <a id="2616" class="Symbol">→</a> <a id="2618" class="Symbol">(</a><a id="2619" href="foundation.universal-property-truncation.html#2614" class="Bound">h</a> <a id="2621" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="2623" href="foundation.universal-property-truncation.html#2500" class="Bound">f</a><a id="2624" class="Symbol">)</a> <a id="2626" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="2628" href="foundation.universal-property-truncation.html#2532" class="Bound">g</a><a id="2629" class="Symbol">))</a>
</pre>
### The dependent universal property of truncations

<pre class="Agda"><a id="precomp-Π-Truncated-Type"></a><a id="2694" href="foundation.universal-property-truncation.html#2694" class="Function">precomp-Π-Truncated-Type</a> <a id="2719" class="Symbol">:</a>
  <a id="2723" class="Symbol">{</a><a id="2724" href="foundation.universal-property-truncation.html#2724" class="Bound">l1</a> <a id="2727" href="foundation.universal-property-truncation.html#2727" class="Bound">l2</a> <a id="2730" href="foundation.universal-property-truncation.html#2730" class="Bound">l3</a> <a id="2733" class="Symbol">:</a> <a id="2735" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2740" class="Symbol">}</a> <a id="2742" class="Symbol">{</a><a id="2743" href="foundation.universal-property-truncation.html#2743" class="Bound">k</a> <a id="2745" class="Symbol">:</a> <a id="2747" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="2748" class="Symbol">}</a> <a id="2750" class="Symbol">{</a><a id="2751" href="foundation.universal-property-truncation.html#2751" class="Bound">A</a> <a id="2753" class="Symbol">:</a> <a id="2755" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2758" href="foundation.universal-property-truncation.html#2724" class="Bound">l1</a><a id="2760" class="Symbol">}</a> <a id="2762" class="Symbol">{</a><a id="2763" href="foundation.universal-property-truncation.html#2763" class="Bound">B</a> <a id="2765" class="Symbol">:</a> <a id="2767" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2770" href="foundation.universal-property-truncation.html#2727" class="Bound">l2</a><a id="2772" class="Symbol">}</a> <a id="2774" class="Symbol">(</a><a id="2775" href="foundation.universal-property-truncation.html#2775" class="Bound">f</a> <a id="2777" class="Symbol">:</a> <a id="2779" href="foundation.universal-property-truncation.html#2751" class="Bound">A</a> <a id="2781" class="Symbol">→</a> <a id="2783" href="foundation.universal-property-truncation.html#2763" class="Bound">B</a><a id="2784" class="Symbol">)</a>
  <a id="2788" class="Symbol">(</a><a id="2789" href="foundation.universal-property-truncation.html#2789" class="Bound">C</a> <a id="2791" class="Symbol">:</a> <a id="2793" href="foundation.universal-property-truncation.html#2763" class="Bound">B</a> <a id="2795" class="Symbol">→</a> <a id="2797" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="2812" href="foundation.universal-property-truncation.html#2730" class="Bound">l3</a> <a id="2815" href="foundation.universal-property-truncation.html#2743" class="Bound">k</a><a id="2816" class="Symbol">)</a> <a id="2818" class="Symbol">→</a>
  <a id="2822" class="Symbol">((</a><a id="2824" href="foundation.universal-property-truncation.html#2824" class="Bound">b</a> <a id="2826" class="Symbol">:</a> <a id="2828" href="foundation.universal-property-truncation.html#2763" class="Bound">B</a><a id="2829" class="Symbol">)</a> <a id="2831" class="Symbol">→</a> <a id="2833" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="2853" class="Symbol">(</a><a id="2854" href="foundation.universal-property-truncation.html#2789" class="Bound">C</a> <a id="2856" href="foundation.universal-property-truncation.html#2824" class="Bound">b</a><a id="2857" class="Symbol">))</a> <a id="2860" class="Symbol">→</a>
  <a id="2864" class="Symbol">((</a><a id="2866" href="foundation.universal-property-truncation.html#2866" class="Bound">a</a> <a id="2868" class="Symbol">:</a> <a id="2870" href="foundation.universal-property-truncation.html#2751" class="Bound">A</a><a id="2871" class="Symbol">)</a> <a id="2873" class="Symbol">→</a> <a id="2875" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="2895" class="Symbol">(</a><a id="2896" href="foundation.universal-property-truncation.html#2789" class="Bound">C</a> <a id="2898" class="Symbol">(</a><a id="2899" href="foundation.universal-property-truncation.html#2775" class="Bound">f</a> <a id="2901" href="foundation.universal-property-truncation.html#2866" class="Bound">a</a><a id="2902" class="Symbol">)))</a>
<a id="2906" href="foundation.universal-property-truncation.html#2694" class="Function">precomp-Π-Truncated-Type</a> <a id="2931" href="foundation.universal-property-truncation.html#2931" class="Bound">f</a> <a id="2933" href="foundation.universal-property-truncation.html#2933" class="Bound">C</a> <a id="2935" href="foundation.universal-property-truncation.html#2935" class="Bound">h</a> <a id="2937" href="foundation.universal-property-truncation.html#2937" class="Bound">a</a> <a id="2939" class="Symbol">=</a> <a id="2941" href="foundation.universal-property-truncation.html#2935" class="Bound">h</a> <a id="2943" class="Symbol">(</a><a id="2944" href="foundation.universal-property-truncation.html#2931" class="Bound">f</a> <a id="2946" href="foundation.universal-property-truncation.html#2937" class="Bound">a</a><a id="2947" class="Symbol">)</a>

<a id="dependent-universal-property-truncation"></a><a id="2950" href="foundation.universal-property-truncation.html#2950" class="Function">dependent-universal-property-truncation</a> <a id="2990" class="Symbol">:</a>
  <a id="2994" class="Symbol">{</a><a id="2995" href="foundation.universal-property-truncation.html#2995" class="Bound">l1</a> <a id="2998" href="foundation.universal-property-truncation.html#2998" class="Bound">l2</a> <a id="3001" class="Symbol">:</a> <a id="3003" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3008" class="Symbol">}</a> <a id="3010" class="Symbol">(</a><a id="3011" href="foundation.universal-property-truncation.html#3011" class="Bound">l</a> <a id="3013" class="Symbol">:</a> <a id="3015" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3020" class="Symbol">)</a> <a id="3022" class="Symbol">{</a><a id="3023" href="foundation.universal-property-truncation.html#3023" class="Bound">k</a> <a id="3025" class="Symbol">:</a> <a id="3027" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="3028" class="Symbol">}</a> <a id="3030" class="Symbol">{</a><a id="3031" href="foundation.universal-property-truncation.html#3031" class="Bound">A</a> <a id="3033" class="Symbol">:</a> <a id="3035" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="3038" href="foundation.universal-property-truncation.html#2995" class="Bound">l1</a><a id="3040" class="Symbol">}</a> <a id="3042" class="Symbol">(</a><a id="3043" href="foundation.universal-property-truncation.html#3043" class="Bound">B</a> <a id="3045" class="Symbol">:</a> <a id="3047" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="3062" href="foundation.universal-property-truncation.html#2998" class="Bound">l2</a> <a id="3065" href="foundation.universal-property-truncation.html#3023" class="Bound">k</a><a id="3066" class="Symbol">)</a>
  <a id="3070" class="Symbol">(</a><a id="3071" href="foundation.universal-property-truncation.html#3071" class="Bound">f</a> <a id="3073" class="Symbol">:</a> <a id="3075" href="foundation.universal-property-truncation.html#3031" class="Bound">A</a> <a id="3077" class="Symbol">→</a> <a id="3079" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="3099" href="foundation.universal-property-truncation.html#3043" class="Bound">B</a><a id="3100" class="Symbol">)</a> <a id="3102" class="Symbol">→</a> <a id="3104" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="3107" class="Symbol">(</a><a id="3108" href="foundation.universal-property-truncation.html#2995" class="Bound">l1</a> <a id="3111" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="3113" href="foundation.universal-property-truncation.html#2998" class="Bound">l2</a> <a id="3116" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="3118" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="3123" href="foundation.universal-property-truncation.html#3011" class="Bound">l</a><a id="3124" class="Symbol">)</a>
<a id="3126" href="foundation.universal-property-truncation.html#2950" class="Function">dependent-universal-property-truncation</a> <a id="3166" href="foundation.universal-property-truncation.html#3166" class="Bound">l</a> <a id="3168" class="Symbol">{</a><a id="3169" href="foundation.universal-property-truncation.html#3169" class="Bound">k</a><a id="3170" class="Symbol">}</a> <a id="3172" href="foundation.universal-property-truncation.html#3172" class="Bound">B</a> <a id="3174" href="foundation.universal-property-truncation.html#3174" class="Bound">f</a> <a id="3176" class="Symbol">=</a>
  <a id="3180" class="Symbol">(</a><a id="3181" href="foundation.universal-property-truncation.html#3181" class="Bound">X</a> <a id="3183" class="Symbol">:</a> <a id="3185" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="3205" href="foundation.universal-property-truncation.html#3172" class="Bound">B</a> <a id="3207" class="Symbol">→</a> <a id="3209" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="3224" href="foundation.universal-property-truncation.html#3166" class="Bound">l</a> <a id="3226" href="foundation.universal-property-truncation.html#3169" class="Bound">k</a><a id="3227" class="Symbol">)</a> <a id="3229" class="Symbol">→</a>
  <a id="3233" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a> <a id="3242" class="Symbol">(</a><a id="3243" href="foundation.universal-property-truncation.html#2694" class="Function">precomp-Π-Truncated-Type</a> <a id="3268" href="foundation.universal-property-truncation.html#3174" class="Bound">f</a> <a id="3270" href="foundation.universal-property-truncation.html#3181" class="Bound">X</a><a id="3271" class="Symbol">)</a>
</pre>
## Properties

### Equivalences into `k`-truncated types are truncations

<pre class="Agda"><a id="3360" class="Keyword">abstract</a>
  <a id="is-truncation-id"></a><a id="3371" href="foundation.universal-property-truncation.html#3371" class="Function">is-truncation-id</a> <a id="3388" class="Symbol">:</a>
    <a id="3394" class="Symbol">{</a><a id="3395" href="foundation.universal-property-truncation.html#3395" class="Bound">l1</a> <a id="3398" class="Symbol">:</a> <a id="3400" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3405" class="Symbol">}</a> <a id="3407" class="Symbol">{</a><a id="3408" href="foundation.universal-property-truncation.html#3408" class="Bound">k</a> <a id="3410" class="Symbol">:</a> <a id="3412" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="3413" class="Symbol">}</a> <a id="3415" class="Symbol">{</a><a id="3416" href="foundation.universal-property-truncation.html#3416" class="Bound">A</a> <a id="3418" class="Symbol">:</a> <a id="3420" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="3423" href="foundation.universal-property-truncation.html#3395" class="Bound">l1</a><a id="3425" class="Symbol">}</a> <a id="3427" class="Symbol">(</a><a id="3428" href="foundation.universal-property-truncation.html#3428" class="Bound">H</a> <a id="3430" class="Symbol">:</a> <a id="3432" href="foundation-core.truncated-types.html#1727" class="Function">is-trunc</a> <a id="3441" href="foundation.universal-property-truncation.html#3408" class="Bound">k</a> <a id="3443" href="foundation.universal-property-truncation.html#3416" class="Bound">A</a><a id="3444" class="Symbol">)</a> <a id="3446" class="Symbol">→</a>
    <a id="3452" class="Symbol">{</a><a id="3453" href="foundation.universal-property-truncation.html#3453" class="Bound">l</a> <a id="3455" class="Symbol">:</a> <a id="3457" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3462" class="Symbol">}</a> <a id="3464" class="Symbol">→</a> <a id="3466" href="foundation.universal-property-truncation.html#1996" class="Function">is-truncation</a> <a id="3480" href="foundation.universal-property-truncation.html#3453" class="Bound">l</a> <a id="3482" class="Symbol">(</a><a id="3483" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="3488" href="foundation.universal-property-truncation.html#3416" class="Bound">A</a> <a id="3490" href="foundation.universal-property-truncation.html#3428" class="Bound">H</a><a id="3491" class="Symbol">)</a> <a id="3493" href="foundation-core.functions.html#309" class="Function">id</a>
  <a id="3498" href="foundation.universal-property-truncation.html#3371" class="Function">is-truncation-id</a> <a id="3515" href="foundation.universal-property-truncation.html#3515" class="Bound">H</a> <a id="3517" href="foundation.universal-property-truncation.html#3517" class="Bound">B</a> <a id="3519" class="Symbol">=</a>
    <a id="3525" href="foundation.equivalences.html#7869" class="Function">is-equiv-precomp-is-equiv</a> <a id="3551" href="foundation-core.functions.html#309" class="Function">id</a> <a id="3554" href="foundation-core.equivalences.html#2309" class="Function">is-equiv-id</a> <a id="3566" class="Symbol">(</a><a id="3567" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="3587" href="foundation.universal-property-truncation.html#3517" class="Bound">B</a><a id="3588" class="Symbol">)</a>

<a id="3591" class="Keyword">abstract</a>
  <a id="is-truncation-equiv"></a><a id="3602" href="foundation.universal-property-truncation.html#3602" class="Function">is-truncation-equiv</a> <a id="3622" class="Symbol">:</a>
    <a id="3628" class="Symbol">{</a><a id="3629" href="foundation.universal-property-truncation.html#3629" class="Bound">l1</a> <a id="3632" href="foundation.universal-property-truncation.html#3632" class="Bound">l2</a> <a id="3635" class="Symbol">:</a> <a id="3637" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3642" class="Symbol">}</a> <a id="3644" class="Symbol">{</a><a id="3645" href="foundation.universal-property-truncation.html#3645" class="Bound">k</a> <a id="3647" class="Symbol">:</a> <a id="3649" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="3650" class="Symbol">}</a> <a id="3652" class="Symbol">{</a><a id="3653" href="foundation.universal-property-truncation.html#3653" class="Bound">A</a> <a id="3655" class="Symbol">:</a> <a id="3657" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="3660" href="foundation.universal-property-truncation.html#3629" class="Bound">l1</a><a id="3662" class="Symbol">}</a> <a id="3664" class="Symbol">(</a><a id="3665" href="foundation.universal-property-truncation.html#3665" class="Bound">B</a> <a id="3667" class="Symbol">:</a> <a id="3669" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="3684" href="foundation.universal-property-truncation.html#3632" class="Bound">l2</a> <a id="3687" href="foundation.universal-property-truncation.html#3645" class="Bound">k</a><a id="3688" class="Symbol">)</a>
    <a id="3694" class="Symbol">(</a><a id="3695" href="foundation.universal-property-truncation.html#3695" class="Bound">e</a> <a id="3697" class="Symbol">:</a> <a id="3699" href="foundation.universal-property-truncation.html#3653" class="Bound">A</a> <a id="3701" href="foundation-core.equivalences.html#1607" class="Function Operator">≃</a> <a id="3703" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="3723" href="foundation.universal-property-truncation.html#3665" class="Bound">B</a><a id="3724" class="Symbol">)</a> <a id="3726" class="Symbol">→</a>
    <a id="3732" class="Symbol">{</a><a id="3733" href="foundation.universal-property-truncation.html#3733" class="Bound">l</a> <a id="3735" class="Symbol">:</a> <a id="3737" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3742" class="Symbol">}</a> <a id="3744" class="Symbol">→</a> <a id="3746" href="foundation.universal-property-truncation.html#1996" class="Function">is-truncation</a> <a id="3760" href="foundation.universal-property-truncation.html#3733" class="Bound">l</a> <a id="3762" href="foundation.universal-property-truncation.html#3665" class="Bound">B</a> <a id="3764" class="Symbol">(</a><a id="3765" href="foundation-core.equivalences.html#1807" class="Function">map-equiv</a> <a id="3775" href="foundation.universal-property-truncation.html#3695" class="Bound">e</a><a id="3776" class="Symbol">)</a>
  <a id="3780" href="foundation.universal-property-truncation.html#3602" class="Function">is-truncation-equiv</a> <a id="3800" href="foundation.universal-property-truncation.html#3800" class="Bound">B</a> <a id="3802" href="foundation.universal-property-truncation.html#3802" class="Bound">e</a> <a id="3804" href="foundation.universal-property-truncation.html#3804" class="Bound">C</a> <a id="3806" class="Symbol">=</a>
    <a id="3812" href="foundation.equivalences.html#7869" class="Function">is-equiv-precomp-is-equiv</a>
      <a id="3844" class="Symbol">(</a> <a id="3846" href="foundation-core.equivalences.html#1807" class="Function">map-equiv</a> <a id="3856" href="foundation.universal-property-truncation.html#3802" class="Bound">e</a><a id="3857" class="Symbol">)</a>
      <a id="3865" class="Symbol">(</a> <a id="3867" href="foundation-core.equivalences.html#1862" class="Function">is-equiv-map-equiv</a> <a id="3886" href="foundation.universal-property-truncation.html#3802" class="Bound">e</a><a id="3887" class="Symbol">)</a>
      <a id="3895" class="Symbol">(</a> <a id="3897" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="3917" href="foundation.universal-property-truncation.html#3804" class="Bound">C</a><a id="3918" class="Symbol">)</a>
</pre>
### A map into a truncated type is a truncation if and only if it satisfies the universal property of the truncation

<pre class="Agda"><a id="4051" class="Keyword">module</a> <a id="4058" href="foundation.universal-property-truncation.html#4058" class="Module">_</a>
  <a id="4062" class="Symbol">{</a><a id="4063" href="foundation.universal-property-truncation.html#4063" class="Bound">l1</a> <a id="4066" href="foundation.universal-property-truncation.html#4066" class="Bound">l2</a> <a id="4069" class="Symbol">:</a> <a id="4071" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="4076" class="Symbol">}</a> <a id="4078" class="Symbol">{</a><a id="4079" href="foundation.universal-property-truncation.html#4079" class="Bound">k</a> <a id="4081" class="Symbol">:</a> <a id="4083" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="4084" class="Symbol">}</a> <a id="4086" class="Symbol">{</a><a id="4087" href="foundation.universal-property-truncation.html#4087" class="Bound">A</a> <a id="4089" class="Symbol">:</a> <a id="4091" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="4094" href="foundation.universal-property-truncation.html#4063" class="Bound">l1</a><a id="4096" class="Symbol">}</a> <a id="4098" class="Symbol">(</a><a id="4099" href="foundation.universal-property-truncation.html#4099" class="Bound">B</a> <a id="4101" class="Symbol">:</a> <a id="4103" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="4118" href="foundation.universal-property-truncation.html#4066" class="Bound">l2</a> <a id="4121" href="foundation.universal-property-truncation.html#4079" class="Bound">k</a><a id="4122" class="Symbol">)</a>
  <a id="4126" class="Symbol">(</a><a id="4127" href="foundation.universal-property-truncation.html#4127" class="Bound">f</a> <a id="4129" class="Symbol">:</a> <a id="4131" href="foundation.universal-property-truncation.html#4087" class="Bound">A</a> <a id="4133" class="Symbol">→</a> <a id="4135" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="4155" href="foundation.universal-property-truncation.html#4099" class="Bound">B</a><a id="4156" class="Symbol">)</a>
  <a id="4160" class="Keyword">where</a>

  <a id="4169" class="Keyword">abstract</a>
    <a id="4182" href="foundation.universal-property-truncation.html#4182" class="Function">is-truncation-universal-property-truncation</a> <a id="4226" class="Symbol">:</a>
      <a id="4234" class="Symbol">({</a><a id="4236" href="foundation.universal-property-truncation.html#4236" class="Bound">l</a> <a id="4238" class="Symbol">:</a> <a id="4240" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="4245" class="Symbol">}</a> <a id="4247" class="Symbol">→</a> <a id="4249" href="foundation.universal-property-truncation.html#2286" class="Function">universal-property-truncation</a> <a id="4279" href="foundation.universal-property-truncation.html#4236" class="Bound">l</a> <a id="4281" href="foundation.universal-property-truncation.html#4099" class="Bound">B</a> <a id="4283" href="foundation.universal-property-truncation.html#4127" class="Bound">f</a><a id="4284" class="Symbol">)</a> <a id="4286" class="Symbol">→</a>
      <a id="4294" class="Symbol">({</a><a id="4296" href="foundation.universal-property-truncation.html#4296" class="Bound">l</a> <a id="4298" class="Symbol">:</a> <a id="4300" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="4305" class="Symbol">}</a> <a id="4307" class="Symbol">→</a> <a id="4309" href="foundation.universal-property-truncation.html#1996" class="Function">is-truncation</a> <a id="4323" href="foundation.universal-property-truncation.html#4296" class="Bound">l</a> <a id="4325" href="foundation.universal-property-truncation.html#4099" class="Bound">B</a> <a id="4327" href="foundation.universal-property-truncation.html#4127" class="Bound">f</a><a id="4328" class="Symbol">)</a>
    <a id="4334" href="foundation.universal-property-truncation.html#4182" class="Function">is-truncation-universal-property-truncation</a> <a id="4378" href="foundation.universal-property-truncation.html#4378" class="Bound">H</a> <a id="4380" href="foundation.universal-property-truncation.html#4380" class="Bound">C</a> <a id="4382" class="Symbol">=</a>
      <a id="4390" href="foundation-core.contractible-maps.html#2368" class="Function">is-equiv-is-contr-map</a>
        <a id="4420" class="Symbol">(</a> <a id="4422" class="Symbol">λ</a> <a id="4424" href="foundation.universal-property-truncation.html#4424" class="Bound">g</a> <a id="4426" class="Symbol">→</a>
          <a id="4438" href="foundation-core.contractible-types.html#3297" class="Function">is-contr-equiv</a>
            <a id="4465" class="Symbol">(</a> <a id="4467" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="4469" class="Symbol">(</a><a id="4470" href="foundation-core.truncated-types.html#10684" class="Function">type-hom-Truncated-Type</a> <a id="4494" href="foundation.universal-property-truncation.html#4079" class="Bound">k</a> <a id="4496" href="foundation.universal-property-truncation.html#4099" class="Bound">B</a> <a id="4498" href="foundation.universal-property-truncation.html#4380" class="Bound">C</a><a id="4499" class="Symbol">)</a> <a id="4501" class="Symbol">(λ</a> <a id="4504" href="foundation.universal-property-truncation.html#4504" class="Bound">h</a> <a id="4506" class="Symbol">→</a> <a id="4508" class="Symbol">(</a><a id="4509" href="foundation.universal-property-truncation.html#4504" class="Bound">h</a> <a id="4511" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="4513" href="foundation.universal-property-truncation.html#4127" class="Bound">f</a><a id="4514" class="Symbol">)</a> <a id="4516" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="4518" href="foundation.universal-property-truncation.html#4424" class="Bound">g</a><a id="4519" class="Symbol">))</a>
            <a id="4534" class="Symbol">(</a> <a id="4536" href="foundation-core.functoriality-dependent-pair-types.html#6804" class="Function">equiv-tot</a> <a id="4546" class="Symbol">(λ</a> <a id="4549" href="foundation.universal-property-truncation.html#4549" class="Bound">h</a> <a id="4551" class="Symbol">→</a> <a id="4553" href="foundation-core.function-extensionality.html#1301" class="Function">equiv-funext</a><a id="4565" class="Symbol">))</a>
            <a id="4580" class="Symbol">(</a> <a id="4582" href="foundation.universal-property-truncation.html#4378" class="Bound">H</a> <a id="4584" href="foundation.universal-property-truncation.html#4380" class="Bound">C</a> <a id="4586" href="foundation.universal-property-truncation.html#4424" class="Bound">g</a><a id="4587" class="Symbol">))</a>

  <a id="4593" class="Keyword">abstract</a>
    <a id="4606" href="foundation.universal-property-truncation.html#4606" class="Function">universal-property-truncation-is-truncation</a> <a id="4650" class="Symbol">:</a>
      <a id="4658" class="Symbol">({</a><a id="4660" href="foundation.universal-property-truncation.html#4660" class="Bound">l</a> <a id="4662" class="Symbol">:</a> <a id="4664" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="4669" class="Symbol">}</a> <a id="4671" class="Symbol">→</a> <a id="4673" href="foundation.universal-property-truncation.html#1996" class="Function">is-truncation</a> <a id="4687" href="foundation.universal-property-truncation.html#4660" class="Bound">l</a> <a id="4689" href="foundation.universal-property-truncation.html#4099" class="Bound">B</a> <a id="4691" href="foundation.universal-property-truncation.html#4127" class="Bound">f</a><a id="4692" class="Symbol">)</a> <a id="4694" class="Symbol">→</a>
      <a id="4702" class="Symbol">({</a><a id="4704" href="foundation.universal-property-truncation.html#4704" class="Bound">l</a> <a id="4706" class="Symbol">:</a> <a id="4708" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="4713" class="Symbol">}</a> <a id="4715" class="Symbol">→</a> <a id="4717" href="foundation.universal-property-truncation.html#2286" class="Function">universal-property-truncation</a> <a id="4747" href="foundation.universal-property-truncation.html#4704" class="Bound">l</a> <a id="4749" href="foundation.universal-property-truncation.html#4099" class="Bound">B</a> <a id="4751" href="foundation.universal-property-truncation.html#4127" class="Bound">f</a><a id="4752" class="Symbol">)</a>
    <a id="4758" href="foundation.universal-property-truncation.html#4606" class="Function">universal-property-truncation-is-truncation</a> <a id="4802" href="foundation.universal-property-truncation.html#4802" class="Bound">H</a> <a id="4804" href="foundation.universal-property-truncation.html#4804" class="Bound">C</a> <a id="4806" href="foundation.universal-property-truncation.html#4806" class="Bound">g</a> <a id="4808" class="Symbol">=</a>
      <a id="4816" href="foundation-core.contractible-types.html#3806" class="Function">is-contr-equiv&#39;</a>
        <a id="4840" class="Symbol">(</a> <a id="4842" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="4844" class="Symbol">(</a><a id="4845" href="foundation-core.truncated-types.html#10684" class="Function">type-hom-Truncated-Type</a> <a id="4869" href="foundation.universal-property-truncation.html#4079" class="Bound">k</a> <a id="4871" href="foundation.universal-property-truncation.html#4099" class="Bound">B</a> <a id="4873" href="foundation.universal-property-truncation.html#4804" class="Bound">C</a><a id="4874" class="Symbol">)</a> <a id="4876" class="Symbol">(λ</a> <a id="4879" href="foundation.universal-property-truncation.html#4879" class="Bound">h</a> <a id="4881" class="Symbol">→</a> <a id="4883" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="4886" class="Symbol">(</a><a id="4887" href="foundation.universal-property-truncation.html#4879" class="Bound">h</a> <a id="4889" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="4891" href="foundation.universal-property-truncation.html#4127" class="Bound">f</a><a id="4892" class="Symbol">)</a> <a id="4894" href="foundation.universal-property-truncation.html#4806" class="Bound">g</a><a id="4895" class="Symbol">))</a>
        <a id="4906" class="Symbol">(</a> <a id="4908" href="foundation-core.functoriality-dependent-pair-types.html#6804" class="Function">equiv-tot</a> <a id="4918" class="Symbol">(λ</a> <a id="4921" href="foundation.universal-property-truncation.html#4921" class="Bound">h</a> <a id="4923" class="Symbol">→</a> <a id="4925" href="foundation-core.function-extensionality.html#1301" class="Function">equiv-funext</a><a id="4937" class="Symbol">))</a>
        <a id="4948" class="Symbol">(</a> <a id="4950" href="foundation-core.contractible-maps.html#3850" class="Function">is-contr-map-is-equiv</a> <a id="4972" class="Symbol">(</a><a id="4973" href="foundation.universal-property-truncation.html#4802" class="Bound">H</a> <a id="4975" href="foundation.universal-property-truncation.html#4804" class="Bound">C</a><a id="4976" class="Symbol">)</a> <a id="4978" href="foundation.universal-property-truncation.html#4806" class="Bound">g</a><a id="4979" class="Symbol">)</a>

  <a id="4984" href="foundation.universal-property-truncation.html#4984" class="Function">map-is-truncation</a> <a id="5002" class="Symbol">:</a>
    <a id="5008" class="Symbol">({</a><a id="5010" href="foundation.universal-property-truncation.html#5010" class="Bound">l</a> <a id="5012" class="Symbol">:</a> <a id="5014" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5019" class="Symbol">}</a> <a id="5021" class="Symbol">→</a> <a id="5023" href="foundation.universal-property-truncation.html#1996" class="Function">is-truncation</a> <a id="5037" href="foundation.universal-property-truncation.html#5010" class="Bound">l</a> <a id="5039" href="foundation.universal-property-truncation.html#4099" class="Bound">B</a> <a id="5041" href="foundation.universal-property-truncation.html#4127" class="Bound">f</a><a id="5042" class="Symbol">)</a> <a id="5044" class="Symbol">→</a>
    <a id="5050" class="Symbol">({</a><a id="5052" href="foundation.universal-property-truncation.html#5052" class="Bound">l</a> <a id="5054" class="Symbol">:</a> <a id="5056" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5061" class="Symbol">}</a> <a id="5063" class="Symbol">(</a><a id="5064" href="foundation.universal-property-truncation.html#5064" class="Bound">C</a> <a id="5066" class="Symbol">:</a> <a id="5068" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="5083" href="foundation.universal-property-truncation.html#5052" class="Bound">l</a> <a id="5085" href="foundation.universal-property-truncation.html#4079" class="Bound">k</a><a id="5086" class="Symbol">)</a> <a id="5088" class="Symbol">(</a><a id="5089" href="foundation.universal-property-truncation.html#5089" class="Bound">g</a> <a id="5091" class="Symbol">:</a> <a id="5093" href="foundation.universal-property-truncation.html#4087" class="Bound">A</a> <a id="5095" class="Symbol">→</a> <a id="5097" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="5117" href="foundation.universal-property-truncation.html#5064" class="Bound">C</a><a id="5118" class="Symbol">)</a> <a id="5120" class="Symbol">→</a>
    <a id="5126" href="foundation-core.truncated-types.html#10684" class="Function">type-hom-Truncated-Type</a> <a id="5150" href="foundation.universal-property-truncation.html#4079" class="Bound">k</a> <a id="5152" href="foundation.universal-property-truncation.html#4099" class="Bound">B</a> <a id="5154" href="foundation.universal-property-truncation.html#5064" class="Bound">C</a><a id="5155" class="Symbol">)</a>
  <a id="5159" href="foundation.universal-property-truncation.html#4984" class="Function">map-is-truncation</a> <a id="5177" href="foundation.universal-property-truncation.html#5177" class="Bound">H</a> <a id="5179" href="foundation.universal-property-truncation.html#5179" class="Bound">C</a> <a id="5181" href="foundation.universal-property-truncation.html#5181" class="Bound">g</a> <a id="5183" class="Symbol">=</a>
    <a id="5189" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="5193" class="Symbol">(</a><a id="5194" href="foundation-core.contractible-types.html#1085" class="Function">center</a> <a id="5201" class="Symbol">(</a><a id="5202" href="foundation.universal-property-truncation.html#4606" class="Function">universal-property-truncation-is-truncation</a> <a id="5246" href="foundation.universal-property-truncation.html#5177" class="Bound">H</a> <a id="5248" href="foundation.universal-property-truncation.html#5179" class="Bound">C</a> <a id="5250" href="foundation.universal-property-truncation.html#5181" class="Bound">g</a><a id="5251" class="Symbol">))</a>

  <a id="5257" href="foundation.universal-property-truncation.html#5257" class="Function">triangle-is-truncation</a> <a id="5280" class="Symbol">:</a>
    <a id="5286" class="Symbol">(</a><a id="5287" href="foundation.universal-property-truncation.html#5287" class="Bound">H</a> <a id="5289" class="Symbol">:</a> <a id="5291" class="Symbol">{</a><a id="5292" href="foundation.universal-property-truncation.html#5292" class="Bound">l</a> <a id="5294" class="Symbol">:</a> <a id="5296" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5301" class="Symbol">}</a> <a id="5303" class="Symbol">→</a> <a id="5305" href="foundation.universal-property-truncation.html#1996" class="Function">is-truncation</a> <a id="5319" href="foundation.universal-property-truncation.html#5292" class="Bound">l</a> <a id="5321" href="foundation.universal-property-truncation.html#4099" class="Bound">B</a> <a id="5323" href="foundation.universal-property-truncation.html#4127" class="Bound">f</a><a id="5324" class="Symbol">)</a> <a id="5326" class="Symbol">→</a>
    <a id="5332" class="Symbol">{</a><a id="5333" href="foundation.universal-property-truncation.html#5333" class="Bound">l</a> <a id="5335" class="Symbol">:</a> <a id="5337" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5342" class="Symbol">}</a> <a id="5344" class="Symbol">(</a><a id="5345" href="foundation.universal-property-truncation.html#5345" class="Bound">C</a> <a id="5347" class="Symbol">:</a> <a id="5349" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="5364" href="foundation.universal-property-truncation.html#5333" class="Bound">l</a> <a id="5366" href="foundation.universal-property-truncation.html#4079" class="Bound">k</a><a id="5367" class="Symbol">)</a> <a id="5369" class="Symbol">(</a><a id="5370" href="foundation.universal-property-truncation.html#5370" class="Bound">g</a> <a id="5372" class="Symbol">:</a> <a id="5374" href="foundation.universal-property-truncation.html#4087" class="Bound">A</a> <a id="5376" class="Symbol">→</a> <a id="5378" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="5398" href="foundation.universal-property-truncation.html#5345" class="Bound">C</a><a id="5399" class="Symbol">)</a> <a id="5401" class="Symbol">→</a>
    <a id="5407" class="Symbol">(</a><a id="5408" href="foundation.universal-property-truncation.html#4984" class="Function">map-is-truncation</a> <a id="5426" href="foundation.universal-property-truncation.html#5287" class="Bound">H</a> <a id="5428" href="foundation.universal-property-truncation.html#5345" class="Bound">C</a> <a id="5430" href="foundation.universal-property-truncation.html#5370" class="Bound">g</a> <a id="5432" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="5434" href="foundation.universal-property-truncation.html#4127" class="Bound">f</a><a id="5435" class="Symbol">)</a> <a id="5437" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="5439" href="foundation.universal-property-truncation.html#5370" class="Bound">g</a>
  <a id="5443" href="foundation.universal-property-truncation.html#5257" class="Function">triangle-is-truncation</a> <a id="5466" href="foundation.universal-property-truncation.html#5466" class="Bound">H</a> <a id="5468" href="foundation.universal-property-truncation.html#5468" class="Bound">C</a> <a id="5470" href="foundation.universal-property-truncation.html#5470" class="Bound">g</a> <a id="5472" class="Symbol">=</a>
    <a id="5478" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="5482" class="Symbol">(</a><a id="5483" href="foundation-core.contractible-types.html#1085" class="Function">center</a> <a id="5490" class="Symbol">(</a><a id="5491" href="foundation.universal-property-truncation.html#4606" class="Function">universal-property-truncation-is-truncation</a> <a id="5535" href="foundation.universal-property-truncation.html#5466" class="Bound">H</a> <a id="5537" href="foundation.universal-property-truncation.html#5468" class="Bound">C</a> <a id="5539" href="foundation.universal-property-truncation.html#5470" class="Bound">g</a><a id="5540" class="Symbol">))</a>
</pre>
### A map into a truncated type is a truncation if and only if it satisfies the dependent universal property of the truncation

<pre class="Agda"><a id="5684" class="Keyword">module</a> <a id="5691" href="foundation.universal-property-truncation.html#5691" class="Module">_</a>
  <a id="5695" class="Symbol">{</a><a id="5696" href="foundation.universal-property-truncation.html#5696" class="Bound">l1</a> <a id="5699" href="foundation.universal-property-truncation.html#5699" class="Bound">l2</a> <a id="5702" class="Symbol">:</a> <a id="5704" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5709" class="Symbol">}</a> <a id="5711" class="Symbol">{</a><a id="5712" href="foundation.universal-property-truncation.html#5712" class="Bound">k</a> <a id="5714" class="Symbol">:</a> <a id="5716" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="5717" class="Symbol">}</a> <a id="5719" class="Symbol">{</a><a id="5720" href="foundation.universal-property-truncation.html#5720" class="Bound">A</a> <a id="5722" class="Symbol">:</a> <a id="5724" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="5727" href="foundation.universal-property-truncation.html#5696" class="Bound">l1</a><a id="5729" class="Symbol">}</a> <a id="5731" class="Symbol">(</a><a id="5732" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a> <a id="5734" class="Symbol">:</a> <a id="5736" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="5751" href="foundation.universal-property-truncation.html#5699" class="Bound">l2</a> <a id="5754" href="foundation.universal-property-truncation.html#5712" class="Bound">k</a><a id="5755" class="Symbol">)</a>
  <a id="5759" class="Symbol">(</a><a id="5760" href="foundation.universal-property-truncation.html#5760" class="Bound">f</a> <a id="5762" class="Symbol">:</a> <a id="5764" href="foundation.universal-property-truncation.html#5720" class="Bound">A</a> <a id="5766" class="Symbol">→</a> <a id="5768" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="5788" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a><a id="5789" class="Symbol">)</a>
  <a id="5793" class="Keyword">where</a>

  <a id="5802" class="Keyword">abstract</a>
    <a id="5815" href="foundation.universal-property-truncation.html#5815" class="Function">dependent-universal-property-truncation-is-truncation</a> <a id="5869" class="Symbol">:</a>
      <a id="5877" class="Symbol">({</a><a id="5879" href="foundation.universal-property-truncation.html#5879" class="Bound">l</a> <a id="5881" class="Symbol">:</a> <a id="5883" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5888" class="Symbol">}</a> <a id="5890" class="Symbol">→</a> <a id="5892" href="foundation.universal-property-truncation.html#1996" class="Function">is-truncation</a> <a id="5906" href="foundation.universal-property-truncation.html#5879" class="Bound">l</a> <a id="5908" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a> <a id="5910" href="foundation.universal-property-truncation.html#5760" class="Bound">f</a><a id="5911" class="Symbol">)</a> <a id="5913" class="Symbol">→</a>
      <a id="5921" class="Symbol">{</a><a id="5922" href="foundation.universal-property-truncation.html#5922" class="Bound">l</a> <a id="5924" class="Symbol">:</a> <a id="5926" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5931" class="Symbol">}</a> <a id="5933" class="Symbol">→</a> <a id="5935" href="foundation.universal-property-truncation.html#2950" class="Function">dependent-universal-property-truncation</a> <a id="5975" href="foundation.universal-property-truncation.html#5922" class="Bound">l</a> <a id="5977" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a> <a id="5979" href="foundation.universal-property-truncation.html#5760" class="Bound">f</a>
    <a id="5985" href="foundation.universal-property-truncation.html#5815" class="Function">dependent-universal-property-truncation-is-truncation</a> <a id="6039" href="foundation.universal-property-truncation.html#6039" class="Bound">H</a> <a id="6041" href="foundation.universal-property-truncation.html#6041" class="Bound">X</a> <a id="6043" class="Symbol">=</a>
      <a id="6051" href="foundation-core.functoriality-dependent-pair-types.html#10750" class="Function">is-fiberwise-equiv-is-equiv-map-Σ</a>
        <a id="6093" class="Symbol">(</a> <a id="6095" class="Symbol">λ</a> <a id="6097" class="Symbol">(</a><a id="6098" href="foundation.universal-property-truncation.html#6098" class="Bound">h</a> <a id="6100" class="Symbol">:</a> <a id="6102" href="foundation.universal-property-truncation.html#5720" class="Bound">A</a> <a id="6104" class="Symbol">→</a> <a id="6106" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="6126" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a><a id="6127" class="Symbol">)</a> <a id="6129" class="Symbol">→</a>
          <a id="6141" class="Symbol">(</a><a id="6142" href="foundation.universal-property-truncation.html#6142" class="Bound">a</a> <a id="6144" class="Symbol">:</a> <a id="6146" href="foundation.universal-property-truncation.html#5720" class="Bound">A</a><a id="6147" class="Symbol">)</a> <a id="6149" class="Symbol">→</a> <a id="6151" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="6171" class="Symbol">(</a><a id="6172" href="foundation.universal-property-truncation.html#6041" class="Bound">X</a> <a id="6174" class="Symbol">(</a><a id="6175" href="foundation.universal-property-truncation.html#6098" class="Bound">h</a> <a id="6177" href="foundation.universal-property-truncation.html#6142" class="Bound">a</a><a id="6178" class="Symbol">)))</a>
        <a id="6190" class="Symbol">(</a> <a id="6192" class="Symbol">λ</a> <a id="6194" class="Symbol">(</a><a id="6195" href="foundation.universal-property-truncation.html#6195" class="Bound">g</a> <a id="6197" class="Symbol">:</a> <a id="6199" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="6219" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a> <a id="6221" class="Symbol">→</a> <a id="6223" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="6243" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a><a id="6244" class="Symbol">)</a> <a id="6246" class="Symbol">→</a> <a id="6248" href="foundation.universal-property-truncation.html#6195" class="Bound">g</a> <a id="6250" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="6252" href="foundation.universal-property-truncation.html#5760" class="Bound">f</a><a id="6253" class="Symbol">)</a>
        <a id="6263" class="Symbol">(</a> <a id="6265" class="Symbol">λ</a> <a id="6267" href="foundation.universal-property-truncation.html#6267" class="Bound">g</a> <a id="6269" class="Symbol">(</a><a id="6270" href="foundation.universal-property-truncation.html#6270" class="Bound">s</a> <a id="6272" class="Symbol">:</a> <a id="6274" class="Symbol">(</a><a id="6275" href="foundation.universal-property-truncation.html#6275" class="Bound">b</a> <a id="6277" class="Symbol">:</a> <a id="6279" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="6299" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a><a id="6300" class="Symbol">)</a> <a id="6302" class="Symbol">→</a>
          <a id="6314" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="6334" class="Symbol">(</a><a id="6335" href="foundation.universal-property-truncation.html#6041" class="Bound">X</a> <a id="6337" class="Symbol">(</a><a id="6338" href="foundation.universal-property-truncation.html#6267" class="Bound">g</a> <a id="6340" href="foundation.universal-property-truncation.html#6275" class="Bound">b</a><a id="6341" class="Symbol">)))</a> <a id="6345" class="Symbol">(</a><a id="6346" href="foundation.universal-property-truncation.html#6346" class="Bound">a</a> <a id="6348" class="Symbol">:</a> <a id="6350" href="foundation.universal-property-truncation.html#5720" class="Bound">A</a><a id="6351" class="Symbol">)</a> <a id="6353" class="Symbol">→</a> <a id="6355" href="foundation.universal-property-truncation.html#6270" class="Bound">s</a> <a id="6357" class="Symbol">(</a><a id="6358" href="foundation.universal-property-truncation.html#5760" class="Bound">f</a> <a id="6360" href="foundation.universal-property-truncation.html#6346" class="Bound">a</a><a id="6361" class="Symbol">))</a>
        <a id="6372" class="Symbol">(</a> <a id="6374" href="foundation.universal-property-truncation.html#6039" class="Bound">H</a> <a id="6376" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a><a id="6377" class="Symbol">)</a>
        <a id="6387" class="Symbol">(</a> <a id="6389" href="foundation-core.equivalences.html#12785" class="Function">is-equiv-equiv</a>
          <a id="6414" class="Symbol">(</a> <a id="6416" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html#5106" class="Function">inv-distributive-Π-Σ</a><a id="6436" class="Symbol">)</a>
          <a id="6448" class="Symbol">(</a> <a id="6450" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html#5106" class="Function">inv-distributive-Π-Σ</a><a id="6470" class="Symbol">)</a>
          <a id="6482" class="Symbol">(</a> <a id="6484" href="foundation-core.dependent-pair-types.html#687" class="Function">ind-Σ</a> <a id="6490" class="Symbol">(λ</a> <a id="6493" href="foundation.universal-property-truncation.html#6493" class="Bound">g</a> <a id="6495" href="foundation.universal-property-truncation.html#6495" class="Bound">s</a> <a id="6497" class="Symbol">→</a> <a id="6499" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a><a id="6503" class="Symbol">))</a>
          <a id="6516" class="Symbol">(</a> <a id="6518" href="foundation.universal-property-truncation.html#6039" class="Bound">H</a> <a id="6520" class="Symbol">(</a><a id="6521" href="foundation-core.truncated-types.html#6283" class="Function">Σ-Truncated-Type</a> <a id="6538" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a> <a id="6540" href="foundation.universal-property-truncation.html#6041" class="Bound">X</a><a id="6541" class="Symbol">)))</a>
        <a id="6553" class="Symbol">(</a> <a id="6555" href="foundation-core.functions.html#309" class="Function">id</a><a id="6557" class="Symbol">)</a>

  <a id="6562" class="Keyword">abstract</a>
    <a id="6575" href="foundation.universal-property-truncation.html#6575" class="Function">is-truncation-dependent-universal-property-truncation</a> <a id="6629" class="Symbol">:</a>
      <a id="6637" class="Symbol">({</a><a id="6639" href="foundation.universal-property-truncation.html#6639" class="Bound">l</a> <a id="6641" class="Symbol">:</a> <a id="6643" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="6648" class="Symbol">}</a> <a id="6650" class="Symbol">→</a> <a id="6652" href="foundation.universal-property-truncation.html#2950" class="Function">dependent-universal-property-truncation</a> <a id="6692" href="foundation.universal-property-truncation.html#6639" class="Bound">l</a> <a id="6694" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a> <a id="6696" href="foundation.universal-property-truncation.html#5760" class="Bound">f</a><a id="6697" class="Symbol">)</a> <a id="6699" class="Symbol">→</a>
      <a id="6707" class="Symbol">{</a><a id="6708" href="foundation.universal-property-truncation.html#6708" class="Bound">l</a> <a id="6710" class="Symbol">:</a> <a id="6712" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="6717" class="Symbol">}</a> <a id="6719" class="Symbol">→</a> <a id="6721" href="foundation.universal-property-truncation.html#1996" class="Function">is-truncation</a> <a id="6735" href="foundation.universal-property-truncation.html#6708" class="Bound">l</a> <a id="6737" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a> <a id="6739" href="foundation.universal-property-truncation.html#5760" class="Bound">f</a>
    <a id="6745" href="foundation.universal-property-truncation.html#6575" class="Function">is-truncation-dependent-universal-property-truncation</a> <a id="6799" href="foundation.universal-property-truncation.html#6799" class="Bound">H</a> <a id="6801" href="foundation.universal-property-truncation.html#6801" class="Bound">X</a> <a id="6803" class="Symbol">=</a>
      <a id="6811" href="foundation.universal-property-truncation.html#6799" class="Bound">H</a> <a id="6813" class="Symbol">(λ</a> <a id="6816" href="foundation.universal-property-truncation.html#6816" class="Bound">b</a> <a id="6818" class="Symbol">→</a> <a id="6820" href="foundation.universal-property-truncation.html#6801" class="Bound">X</a><a id="6821" class="Symbol">)</a>

  <a id="6826" href="foundation.universal-property-truncation.html#6826" class="Function">sec-is-truncation</a> <a id="6844" class="Symbol">:</a>
    <a id="6850" class="Symbol">({</a><a id="6852" href="foundation.universal-property-truncation.html#6852" class="Bound">l</a> <a id="6854" class="Symbol">:</a> <a id="6856" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="6861" class="Symbol">}</a> <a id="6863" class="Symbol">→</a> <a id="6865" href="foundation.universal-property-truncation.html#1996" class="Function">is-truncation</a> <a id="6879" href="foundation.universal-property-truncation.html#6852" class="Bound">l</a> <a id="6881" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a> <a id="6883" href="foundation.universal-property-truncation.html#5760" class="Bound">f</a><a id="6884" class="Symbol">)</a> <a id="6886" class="Symbol">→</a>
    <a id="6892" class="Symbol">{</a><a id="6893" href="foundation.universal-property-truncation.html#6893" class="Bound">l3</a> <a id="6896" class="Symbol">:</a> <a id="6898" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="6903" class="Symbol">}</a> <a id="6905" class="Symbol">(</a><a id="6906" href="foundation.universal-property-truncation.html#6906" class="Bound">C</a> <a id="6908" class="Symbol">:</a> <a id="6910" href="foundation-core.truncated-types.html#1912" class="Function">Truncated-Type</a> <a id="6925" href="foundation.universal-property-truncation.html#6893" class="Bound">l3</a> <a id="6928" href="foundation.universal-property-truncation.html#5712" class="Bound">k</a><a id="6929" class="Symbol">)</a>
    <a id="6935" class="Symbol">(</a><a id="6936" href="foundation.universal-property-truncation.html#6936" class="Bound">h</a> <a id="6938" class="Symbol">:</a> <a id="6940" href="foundation.universal-property-truncation.html#5720" class="Bound">A</a> <a id="6942" class="Symbol">→</a> <a id="6944" href="foundation-core.truncated-types.html#2047" class="Function">type-Truncated-Type</a> <a id="6964" href="foundation.universal-property-truncation.html#6906" class="Bound">C</a><a id="6965" class="Symbol">)</a> <a id="6967" class="Symbol">(</a><a id="6968" href="foundation.universal-property-truncation.html#6968" class="Bound">g</a> <a id="6970" class="Symbol">:</a> <a id="6972" href="foundation-core.truncated-types.html#10684" class="Function">type-hom-Truncated-Type</a> <a id="6996" href="foundation.universal-property-truncation.html#5712" class="Bound">k</a> <a id="6998" href="foundation.universal-property-truncation.html#6906" class="Bound">C</a> <a id="7000" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a><a id="7001" class="Symbol">)</a> <a id="7003" class="Symbol">→</a>
    <a id="7009" href="foundation.universal-property-truncation.html#5760" class="Bound">f</a> <a id="7011" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="7013" class="Symbol">(</a><a id="7014" href="foundation.universal-property-truncation.html#6968" class="Bound">g</a> <a id="7016" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="7018" href="foundation.universal-property-truncation.html#6936" class="Bound">h</a><a id="7019" class="Symbol">)</a> <a id="7021" class="Symbol">→</a> <a id="7023" href="foundation-core.sections.html#521" class="Function">sec</a> <a id="7027" href="foundation.universal-property-truncation.html#6968" class="Bound">g</a>
  <a id="7031" href="foundation.universal-property-truncation.html#6826" class="Function">sec-is-truncation</a> <a id="7049" href="foundation.universal-property-truncation.html#7049" class="Bound">H</a> <a id="7051" href="foundation.universal-property-truncation.html#7051" class="Bound">C</a> <a id="7053" href="foundation.universal-property-truncation.html#7053" class="Bound">h</a> <a id="7055" href="foundation.universal-property-truncation.html#7055" class="Bound">g</a> <a id="7057" href="foundation.universal-property-truncation.html#7057" class="Bound">K</a> <a id="7059" class="Symbol">=</a>
    <a id="7065" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html#2808" class="Function">map-distributive-Π-Σ</a>
      <a id="7092" class="Symbol">(</a> <a id="7094" href="foundation-core.equivalences.html#4173" class="Function">map-inv-is-equiv</a>
        <a id="7119" class="Symbol">(</a> <a id="7121" href="foundation.universal-property-truncation.html#5815" class="Function">dependent-universal-property-truncation-is-truncation</a> <a id="7175" href="foundation.universal-property-truncation.html#7049" class="Bound">H</a>
          <a id="7187" class="Symbol">(</a> <a id="7189" href="foundation-core.truncated-types.html#6657" class="Function">fib-Truncated-Type</a> <a id="7208" href="foundation.universal-property-truncation.html#7051" class="Bound">C</a> <a id="7210" href="foundation.universal-property-truncation.html#5732" class="Bound">B</a> <a id="7212" href="foundation.universal-property-truncation.html#7055" class="Bound">g</a><a id="7213" class="Symbol">))</a>
        <a id="7224" class="Symbol">(</a> <a id="7226" class="Symbol">λ</a> <a id="7228" href="foundation.universal-property-truncation.html#7228" class="Bound">a</a> <a id="7230" class="Symbol">→</a> <a id="7232" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="7237" class="Symbol">(</a><a id="7238" href="foundation.universal-property-truncation.html#7053" class="Bound">h</a> <a id="7240" href="foundation.universal-property-truncation.html#7228" class="Bound">a</a><a id="7241" class="Symbol">)</a> <a id="7243" class="Symbol">(</a><a id="7244" href="foundation-core.identity-types.html#1552" class="Function">inv</a> <a id="7248" class="Symbol">(</a><a id="7249" href="foundation.universal-property-truncation.html#7057" class="Bound">K</a> <a id="7251" href="foundation.universal-property-truncation.html#7228" class="Bound">a</a><a id="7252" class="Symbol">))))</a>
</pre>
## To do

<pre class="Agda">
<a id="7281" class="Comment">{-

-- Theorem 18.5.2 (iii) implies (i)

reflects-mere-eq :
  {l1 l2 : Level} {A : UU l1} (X : UU-Set l2) (f : A → type-Set X) →
  reflects-Eq-Rel (mere-eq-Eq-Rel A) f
reflects-mere-eq X f {x} {y} r =
  apply-universal-property-trunc-Prop r
    ( Id-Prop X (f x) (f y))
    ( ap f)

reflecting-map-mere-eq :
  {l1 l2 : Level} {A : UU l1} (X : UU-Set l2) (f : A → type-Set X) →
  reflecting-map-Eq-Rel (mere-eq-Eq-Rel A) (type-Set X)
reflecting-map-mere-eq X f = pair f (reflects-mere-eq X f)

abstract
  is-set-truncation-is-set-quotient :
    {l1 l2 l3 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B) →
    ( {l : Level} →
      is-set-quotient l (mere-eq-Eq-Rel A) B (reflecting-map-mere-eq B f)) →
    is-set-truncation l3 B f
  is-set-truncation-is-set-quotient {A = A} B f H X =
    is-equiv-comp
      ( precomp-Set f X)
      ( pr1)
      ( precomp-Set-Quotient
        ( mere-eq-Eq-Rel A)
        ( B)
        ( reflecting-map-mere-eq B f)
        ( X))
      ( refl-htpy)
      ( H X)
      ( is-equiv-pr1-is-contr
        ( λ h →
          is-proof-irrelevant-is-prop
            ( is-prop-reflects-Eq-Rel (mere-eq-Eq-Rel A) X h)
            ( reflects-mere-eq X h)))

abstract
  is-set-quotient-is-set-truncation :
    {l1 l2 l3 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B) →
    ( {l : Level} → is-set-truncation l B f) →
    is-set-quotient l3 (mere-eq-Eq-Rel A) B (reflecting-map-mere-eq B f)
  is-set-quotient-is-set-truncation {A = A} B f H X =
    is-equiv-right-factor
      ( precomp-Set f X)
      ( pr1)
      ( precomp-Set-Quotient
        ( mere-eq-Eq-Rel A)
        ( B)
        ( reflecting-map-mere-eq B f)
        ( X))
      ( refl-htpy)
      ( is-equiv-pr1-is-contr
        ( λ h →
          is-proof-irrelevant-is-prop
            ( is-prop-reflects-Eq-Rel (mere-eq-Eq-Rel A) X h)
            ( reflects-mere-eq X h)))
      ( H X)

-- Definition 18.5.3

-- Corollary 18.5.4

reflecting-map-mere-eq-unit-trunc-Set :
  {l : Level} (A : UU l) →
  reflecting-map-Eq-Rel (mere-eq-Eq-Rel A) (type-trunc-Set A)
reflecting-map-mere-eq-unit-trunc-Set A =
  pair unit-trunc-Set (reflects-mere-eq (trunc-Set A) unit-trunc-Set)

abstract
  is-set-quotient-trunc-Set :
    {l1 l2 : Level} (A : UU l1) →
    is-set-quotient l2
      ( mere-eq-Eq-Rel A)
      ( trunc-Set A)
      ( reflecting-map-mere-eq-unit-trunc-Set A)
  is-set-quotient-trunc-Set A =
    is-set-quotient-is-set-truncation
      ( trunc-Set A)
      ( unit-trunc-Set)
      ( λ {l} → is-set-truncation-trunc-Set A)

abstract
  is-surjective-and-effective-unit-trunc-Set :
    {l1 : Level} (A : UU l1) →
    is-surjective-and-effective (mere-eq-Eq-Rel A) unit-trunc-Set
  is-surjective-and-effective-unit-trunc-Set A =
    is-surjective-and-effective-is-set-quotient
      ( mere-eq-Eq-Rel A)
      ( trunc-Set A)
      ( unit-trunc-Set)
      ( reflects-mere-eq (trunc-Set A) unit-trunc-Set)
      ( λ {l} → is-set-quotient-trunc-Set A)

abstract
  is-surjective-unit-trunc-Set :
    {l1 : Level} (A : UU l1) → is-surjective (unit-trunc-Set {A = A})
  is-surjective-unit-trunc-Set A =
    pr1 (is-surjective-and-effective-unit-trunc-Set A)

abstract
  is-effective-unit-trunc-Set :
    {l1 : Level} (A : UU l1) →
    is-effective (mere-eq-Eq-Rel A) (unit-trunc-Set {A = A})
  is-effective-unit-trunc-Set A =
    pr2 (is-surjective-and-effective-unit-trunc-Set A)

abstract
  apply-effectiveness-unit-trunc-Set :
    {l1 : Level} {A : UU l1} {x y : A} →
    Id (unit-trunc-Set x) (unit-trunc-Set y) → mere-eq x y
  apply-effectiveness-unit-trunc-Set {A = A} {x} {y} =
    map-equiv (is-effective-unit-trunc-Set A x y)

abstract
  apply-effectiveness-unit-trunc-Set&#39; :
    {l1 : Level} {A : UU l1} {x y : A} →
    mere-eq x y → Id (unit-trunc-Set x) (unit-trunc-Set y)
  apply-effectiveness-unit-trunc-Set&#39; {A = A} {x} {y} =
    map-inv-equiv (is-effective-unit-trunc-Set A x y)

emb-trunc-Set :
  {l1 : Level} (A : UU l1) → type-trunc-Set A ↪ (A → UU-Prop l1)
emb-trunc-Set A =
  emb-is-surjective-and-effective
    ( mere-eq-Eq-Rel A)
    ( trunc-Set A)
    ( unit-trunc-Set)
    ( is-surjective-and-effective-unit-trunc-Set A)

hom-slice-trunc-Set :
  {l1 : Level} (A : UU l1) →
  hom-slice (mere-eq-Prop {A = A}) (map-emb (emb-trunc-Set A))
hom-slice-trunc-Set A =
  pair
    ( unit-trunc-Set)
    ( triangle-emb-is-surjective-and-effective
      ( mere-eq-Eq-Rel A)
      ( trunc-Set A)
      ( unit-trunc-Set)
      ( is-surjective-and-effective-unit-trunc-Set A))

abstract
  is-image-trunc-Set :
    {l1 l2 : Level} (A : UU l1) →
    is-image l2
      ( mere-eq-Prop {A = A})
      ( emb-trunc-Set A)
      ( hom-slice-trunc-Set A)
  is-image-trunc-Set A =
    is-image-is-surjective-and-effective
      ( mere-eq-Eq-Rel A)
      ( trunc-Set A)
      ( unit-trunc-Set)
      ( is-surjective-and-effective-unit-trunc-Set A)

-- Uniqueness of trunc-Set

module _
  {l1 l2 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B)
  {h : type-hom-Set B (trunc-Set A)} (H : (h ∘ f) ~ unit-trunc-Set)
  where

  abstract
    is-equiv-is-set-truncation&#39; :
      ({l : Level} → is-set-truncation l B f) → is-equiv h
    is-equiv-is-set-truncation&#39; Sf =
      is-equiv-is-set-truncation-is-set-truncation
        ( B)
        ( f)
        ( trunc-Set A)
        ( unit-trunc-Set)
        ( H)
        ( Sf)
        ( λ {h} → is-set-truncation-trunc-Set A)

  abstract
    is-set-truncation-is-equiv&#39; :
      is-equiv h → ({l : Level} → is-set-truncation l B f)
    is-set-truncation-is-equiv&#39; Eh =
      is-set-truncation-is-equiv-is-set-truncation
        ( B)
        ( f)
        ( trunc-Set A)
        ( unit-trunc-Set)
        ( H)
        ( λ {l} → is-set-truncation-trunc-Set A)
        ( Eh)

module _
  {l1 l2 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B)
  {h : type-hom-Set (trunc-Set A) B} (H : (h ∘ unit-trunc-Set) ~ f)
  where

  abstract
    is-equiv-is-set-truncation :
      ({l : Level} → is-set-truncation l B f) → is-equiv h
    is-equiv-is-set-truncation Sf =
      is-equiv-is-set-truncation-is-set-truncation
        ( trunc-Set A)
        ( unit-trunc-Set)
        ( B)
        ( f)
        ( H)
        ( λ {l} → is-set-truncation-trunc-Set A)
        ( Sf)

  abstract
    is-set-truncation-is-equiv :
      is-equiv h → ({l : Level} → is-set-truncation l B f)
    is-set-truncation-is-equiv Eh =
      is-set-truncation-is-set-truncation-is-equiv
        ( trunc-Set A)
        ( unit-trunc-Set)
        ( B)
        ( f)
        ( H)
        ( Eh)
        ( λ {l} → is-set-truncation-trunc-Set A)

abstract
  is-equiv-unit-trunc-Set :
    {l : Level} (A : UU-Set l) → is-equiv (unit-trunc-Set {A = type-Set A})
  is-equiv-unit-trunc-Set A =
    is-equiv-is-set-truncation&#39; A id refl-htpy
      ( is-set-truncation-id (is-set-type-Set A))

equiv-unit-trunc-Set :
  {l : Level} (A : UU-Set l) → type-Set A ≃ type-trunc-Set (type-Set A)
equiv-unit-trunc-Set A =
  pair unit-trunc-Set (is-equiv-unit-trunc-Set A)

equiv-unit-trunc-empty-Set : empty ≃ type-trunc-Set empty
equiv-unit-trunc-empty-Set = equiv-unit-trunc-Set empty-Set

abstract
  is-empty-trunc-Set :
    {l : Level} {A : UU l} → is-empty A → is-empty (type-trunc-Set A)
  is-empty-trunc-Set f x = apply-universal-property-trunc-Set x empty-Set f

abstract
  is-empty-is-empty-trunc-Set :
    {l : Level} {A : UU l} → is-empty (type-trunc-Set A) → is-empty A
  is-empty-is-empty-trunc-Set f = f ∘ unit-trunc-Set

equiv-unit-trunc-unit-Set : unit ≃ type-trunc-Set unit
equiv-unit-trunc-unit-Set = equiv-unit-trunc-Set unit-Set

equiv-unit-trunc-ℕ-Set : ℕ ≃ type-trunc-Set ℕ
equiv-unit-trunc-ℕ-Set = equiv-unit-trunc-Set ℕ-Set

equiv-unit-trunc-ℤ-Set : ℤ ≃ type-trunc-Set ℤ
equiv-unit-trunc-ℤ-Set = equiv-unit-trunc-Set ℤ-Set

equiv-unit-trunc-Fin-Set : (k : ℕ) → Fin k ≃ type-trunc-Set (Fin k)
equiv-unit-trunc-Fin-Set k = equiv-unit-trunc-Set (Fin-Set k)

abstract
  is-contr-trunc-Set :
    {l : Level} {A : UU l} → is-contr A → is-contr (type-trunc-Set A)
  is-contr-trunc-Set {l} {A} H =
    is-contr-equiv&#39;
      ( A)
      ( equiv-unit-trunc-Set (pair A (is-set-is-contr H)))
      ( H)

module _
  {l1 l2 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B)
  (Sf : {l : Level} → is-set-truncation l B f)
  where

  abstract
    uniqueness-trunc-Set :
      is-contr
        ( Σ (type-trunc-Set A ≃ type-Set B)
        ( λ e → (map-equiv e ∘ unit-trunc-Set) ~ f))
    uniqueness-trunc-Set =
      uniqueness-set-truncation (trunc-Set A) unit-trunc-Set B f
        ( λ {l} → is-set-truncation-trunc-Set A)
        ( Sf)

  equiv-uniqueness-trunc-Set : type-trunc-Set A ≃ type-Set B
  equiv-uniqueness-trunc-Set =
    pr1 (center uniqueness-trunc-Set)

  map-equiv-uniqueness-trunc-Set : type-trunc-Set A → type-Set B
  map-equiv-uniqueness-trunc-Set =
    map-equiv equiv-uniqueness-trunc-Set

  triangle-uniqueness-trunc-Set :
    (map-equiv-uniqueness-trunc-Set ∘ unit-trunc-Set) ~ f
  triangle-uniqueness-trunc-Set =
    pr2 (center uniqueness-trunc-Set)

module _
  {l1 l2 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B)
  (Sf : {l : Level} → is-set-truncation l B f)
  where

  abstract
    uniqueness-trunc-Set&#39; :
      is-contr
        ( Σ ( type-Set B ≃ type-trunc-Set A)
            ( λ e → (map-equiv e ∘ f) ~ unit-trunc-Set))
    uniqueness-trunc-Set&#39; =
      uniqueness-set-truncation B f (trunc-Set A) unit-trunc-Set Sf
        ( λ {l} → is-set-truncation-trunc-Set A)

  equiv-uniqueness-trunc-Set&#39; : type-Set B ≃ type-trunc-Set A
  equiv-uniqueness-trunc-Set&#39; =
    pr1 (center uniqueness-trunc-Set&#39;)

  map-equiv-uniqueness-trunc-Set&#39; : type-Set B → type-trunc-Set A
  map-equiv-uniqueness-trunc-Set&#39; =
    map-equiv equiv-uniqueness-trunc-Set&#39;
  
  triangle-uniqueness-trunc-Set&#39; :
    (map-equiv-uniqueness-trunc-Set&#39; ∘ f) ~ unit-trunc-Set
  triangle-uniqueness-trunc-Set&#39; =
    pr2 (center uniqueness-trunc-Set&#39;)

-- Proposition 18.5.5

module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (f : A → B)
  where

  abstract
    unique-map-trunc-Set :
      is-contr
        ( Σ ( type-trunc-Set A → type-trunc-Set B)
            ( λ h → (h ∘ unit-trunc-Set) ~ (unit-trunc-Set ∘ f)))
    unique-map-trunc-Set =
      universal-property-trunc-Set A (trunc-Set B) (unit-trunc-Set ∘ f)

  map-trunc-Set :
    type-trunc-Set A → type-trunc-Set B
  map-trunc-Set =
    pr1 (center unique-map-trunc-Set)

  naturality-trunc-Set :
    (map-trunc-Set ∘ unit-trunc-Set) ~ (unit-trunc-Set ∘ f)
  naturality-trunc-Set =
    pr2 (center unique-map-trunc-Set)

  htpy-map-trunc-Set :
    (h : type-trunc-Set A → type-trunc-Set B) →
    (H : (h ∘ unit-trunc-Set) ~ (unit-trunc-Set ∘ f)) →
    map-trunc-Set ~ h
  htpy-map-trunc-Set h H =
    htpy-eq
      ( ap pr1
        ( eq-is-contr unique-map-trunc-Set
          { pair map-trunc-Set naturality-trunc-Set}
          { pair h H}))

map-id-trunc-Set :
  {l1 : Level} {A : UU l1} → map-trunc-Set (id {A = A}) ~ id
map-id-trunc-Set {l1} {A} =
  htpy-eq
    ( ap pr1
      ( eq-is-contr
        ( universal-property-trunc-Set A (trunc-Set A) unit-trunc-Set)
        { pair (map-trunc-Set id) (naturality-trunc-Set id)}
        { pair id refl-htpy}))

map-comp-trunc-Set :
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} {C : UU l3}
  (g : B → C) (f : A → B) →
  map-trunc-Set (g ∘ f) ~ (map-trunc-Set g ∘ map-trunc-Set f)
map-comp-trunc-Set {A = A} {C = C} g f =
  htpy-eq
    ( ap pr1
      ( eq-is-contr
        ( universal-property-trunc-Set
          A
          (trunc-Set C)
          (unit-trunc-Set ∘ (g ∘ f)))
        { pair (map-trunc-Set (g ∘ f)) (naturality-trunc-Set (g ∘ f))}
        { pair ( map-trunc-Set g ∘ map-trunc-Set f)
               ( ( map-trunc-Set g ·l naturality-trunc-Set f) ∙h
                 ( naturality-trunc-Set g ·r f))}))

htpy-trunc-Set :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} {f g : A → B} →
  (f ~ g) → (map-trunc-Set f ~ map-trunc-Set g)
htpy-trunc-Set {B = B} {f = f} {g} H =
  map-inv-is-equiv
    ( dependent-universal-property-trunc-Set
      ( λ x →
        set-Prop
          ( Id-Prop (trunc-Set B) (map-trunc-Set f x) (map-trunc-Set g x))))
    ( λ a →
      ( naturality-trunc-Set f a) ∙
      ( ( ap unit-trunc-Set (H a)) ∙
        ( inv (naturality-trunc-Set g a))))

abstract
  is-equiv-map-trunc-Set :
    {l1 l2 : Level} {A : UU l1} {B : UU l2} {f : A → B} →
    is-equiv f → is-equiv (map-trunc-Set f)
  is-equiv-map-trunc-Set {f = f} H =
    pair
      ( pair
        ( map-trunc-Set (pr1 (pr1 H)))
        ( ( inv-htpy (map-comp-trunc-Set f (pr1 (pr1 H)))) ∙h
          ( ( htpy-trunc-Set (pr2 (pr1 H))) ∙h
            ( map-id-trunc-Set))))
      ( pair
        ( map-trunc-Set (pr1 (pr2 H)))
        ( ( inv-htpy (map-comp-trunc-Set (pr1 (pr2 H)) f)) ∙h
          ( ( htpy-trunc-Set (pr2 (pr2 H))) ∙h
            ( map-id-trunc-Set))))

equiv-trunc-Set :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} →
  (A ≃ B) → (type-trunc-Set A ≃ type-trunc-Set B)
equiv-trunc-Set e =
  pair
    ( map-trunc-Set (map-equiv e))
    ( is-equiv-map-trunc-Set (is-equiv-map-equiv e))

map-equiv-trunc-Set :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} →
  (A ≃ B) → type-trunc-Set A → type-trunc-Set B
map-equiv-trunc-Set e = map-equiv (equiv-trunc-Set e)

--------------------------------------------------------------------------------

module _
  {l1 l2 : Level} (A : UU l1) (B : UU l2)
  where

  abstract
    distributive-trunc-coprod-Set :
      is-contr
        ( Σ ( type-equiv-Set
              ( trunc-Set (coprod A B))
              ( coprod-Set (trunc-Set A) (trunc-Set B)))
            ( λ e →
              ( map-equiv e ∘ unit-trunc-Set) ~
              ( map-coprod unit-trunc-Set unit-trunc-Set)))
    distributive-trunc-coprod-Set =
      uniqueness-trunc-Set
        ( coprod-Set (trunc-Set A) (trunc-Set B))
        ( map-coprod unit-trunc-Set unit-trunc-Set)
        ( λ {l} C →
          is-equiv-right-factor&#39;
            ( ev-inl-inr (λ x → type-Set C))
            ( precomp-Set (map-coprod unit-trunc-Set unit-trunc-Set) C)
            ( universal-property-coprod (type-Set C))
            ( is-equiv-comp&#39;
              ( map-prod
                ( precomp-Set unit-trunc-Set C)
                ( precomp-Set unit-trunc-Set C))
              ( ev-inl-inr (λ x → type-Set C))
              ( universal-property-coprod (type-Set C))
              ( is-equiv-map-prod
                ( precomp-Set unit-trunc-Set C)
                ( precomp-Set unit-trunc-Set C)
                ( is-set-truncation-trunc-Set A C)
                ( is-set-truncation-trunc-Set B C))))

  equiv-distributive-trunc-coprod-Set :
    type-equiv-Set
      ( trunc-Set (coprod A B))
      ( coprod-Set (trunc-Set A) (trunc-Set B))
  equiv-distributive-trunc-coprod-Set =
    pr1 (center distributive-trunc-coprod-Set)

  map-equiv-distributive-trunc-coprod-Set :
    type-hom-Set
      ( trunc-Set (coprod A B))
      ( coprod-Set (trunc-Set A) (trunc-Set B))
  map-equiv-distributive-trunc-coprod-Set =
    map-equiv equiv-distributive-trunc-coprod-Set

  triangle-distributive-trunc-coprod-Set :
    ( map-equiv-distributive-trunc-coprod-Set ∘ unit-trunc-Set) ~
    ( map-coprod unit-trunc-Set unit-trunc-Set)
  triangle-distributive-trunc-coprod-Set =
    pr2 (center distributive-trunc-coprod-Set)

-- Set truncations of Σ-types

module _
  {l1 l2 : Level} (A : UU l1) (B : A → UU l2)
  where

  abstract
    trunc-Σ-Set :
      is-contr
        ( Σ ( type-trunc-Set (Σ A B) ≃
              type-trunc-Set (Σ A (λ x → type-trunc-Set (B x))))
            ( λ e →
              ( map-equiv e ∘ unit-trunc-Set) ~
              ( unit-trunc-Set ∘ tot (λ x → unit-trunc-Set))))
    trunc-Σ-Set =
      uniqueness-trunc-Set
        ( trunc-Set (Σ A (λ x → type-trunc-Set (B x))))
        ( unit-trunc-Set ∘ tot (λ x → unit-trunc-Set))
        ( λ {l} C →
          is-equiv-right-factor&#39;
            ( ev-pair)
            ( precomp-Set (unit-trunc-Set ∘ tot (λ x → unit-trunc-Set)) C)
            ( is-equiv-ev-pair)
            ( is-equiv-htpy-equiv
              ( ( equiv-map-Π
                  ( λ x → equiv-universal-property-trunc-Set (B x) C)) ∘e
                ( ( equiv-ev-pair) ∘e
                  ( equiv-universal-property-trunc-Set
                    ( Σ A (type-trunc-Set ∘ B)) C)))
              ( refl-htpy)))

  equiv-trunc-Σ-Set :
    type-trunc-Set (Σ A B) ≃ type-trunc-Set (Σ A (λ x → type-trunc-Set (B x)))
  equiv-trunc-Σ-Set =
    pr1 (center trunc-Σ-Set)

  map-equiv-trunc-Σ-Set :
    type-trunc-Set (Σ A B) → type-trunc-Set (Σ A (λ x → type-trunc-Set (B x)))
  map-equiv-trunc-Σ-Set =
    map-equiv equiv-trunc-Σ-Set

  square-trunc-Σ-Set :
    ( map-equiv-trunc-Σ-Set ∘ unit-trunc-Set) ~
    ( unit-trunc-Set ∘ tot (λ x → unit-trunc-Set))
  square-trunc-Σ-Set =
    pr2 (center trunc-Σ-Set)

  htpy-map-equiv-trunc-Σ-Set :
    map-trunc-Set (tot (λ x → unit-trunc-Set)) ~ map-equiv-trunc-Σ-Set
  htpy-map-equiv-trunc-Σ-Set =
    htpy-map-trunc-Set
      ( tot (λ x → unit-trunc-Set))
      ( map-equiv-trunc-Σ-Set)
      ( square-trunc-Σ-Set)

  abstract
    is-equiv-map-trunc-tot-unit-trunc-Set :
      is-equiv (map-trunc-Set (tot (λ (x : A) → unit-trunc-Set {A = B x})))
    is-equiv-map-trunc-tot-unit-trunc-Set =
      is-equiv-htpy-equiv
        ( equiv-trunc-Σ-Set)
        ( htpy-map-equiv-trunc-Σ-Set)

-- trunc-Set distributes over products

module _
  {l1 l2 : Level} (A : UU l1) (B : UU l2)
  where

  abstract
    distributive-trunc-prod-Set :
      is-contr
        ( Σ ( type-trunc-Set (A × B) ≃ ( type-trunc-Set A × type-trunc-Set B))
            ( λ e →
              ( map-equiv e ∘ unit-trunc-Set) ~
              ( map-prod unit-trunc-Set unit-trunc-Set)))
    distributive-trunc-prod-Set =
      uniqueness-trunc-Set
        ( prod-Set (trunc-Set A) (trunc-Set B))
        ( map-prod unit-trunc-Set unit-trunc-Set)
        ( λ {l} C →
          is-equiv-right-factor&#39;
            ( ev-pair)
            ( precomp-Set (map-prod unit-trunc-Set unit-trunc-Set) C)
            ( is-equiv-ev-pair)
            ( is-equiv-htpy-equiv
              ( ( equiv-universal-property-trunc-Set A (Π-Set&#39; B (λ y → C))) ∘e
                ( ( equiv-postcomp
                    ( type-trunc-Set A)
                    (equiv-universal-property-trunc-Set B C)) ∘e
                  ( equiv-ev-pair)))
              ( refl-htpy)))

  equiv-distributive-trunc-prod-Set :
    type-trunc-Set (A × B) ≃ ( type-trunc-Set A × type-trunc-Set B)
  equiv-distributive-trunc-prod-Set =
    pr1 (center distributive-trunc-prod-Set)

  map-equiv-distributive-trunc-prod-Set :
    type-trunc-Set (A × B) → type-trunc-Set A × type-trunc-Set B
  map-equiv-distributive-trunc-prod-Set =
    map-equiv equiv-distributive-trunc-prod-Set

  triangle-distributive-trunc-prod-Set :
    ( map-equiv-distributive-trunc-prod-Set ∘ unit-trunc-Set) ~
    ( map-prod unit-trunc-Set unit-trunc-Set)
  triangle-distributive-trunc-prod-Set =
    pr2 (center distributive-trunc-prod-Set)

-- trunc-Set distributes over Π indexed by Fin

abstract
  distributive-trunc-Π-Fin-Set :
    {l : Level} (k : ℕ) (A : Fin k → UU l) →
    is-contr
      ( Σ ( ( type-trunc-Set ((x : Fin k) → A x)) ≃
            ( (x : Fin k) → type-trunc-Set (A x)))
          ( λ e →
            ( map-equiv e ∘ unit-trunc-Set) ~
            ( map-Π (λ x → unit-trunc-Set))))
  distributive-trunc-Π-Fin-Set zero-ℕ A =
    uniqueness-trunc-Set
      ( Π-Set empty-Set (λ x → trunc-Set (A x)))
      ( map-Π (λ x → unit-trunc-Set))
      ( λ {l} B →
        is-equiv-precomp-is-equiv
          ( map-Π (λ x → unit-trunc-Set))
          ( is-equiv-is-contr
            ( map-Π (λ x → unit-trunc-Set))
            ( dependent-universal-property-empty&#39; A)
            ( dependent-universal-property-empty&#39; (type-trunc-Set ∘ A)))
          ( type-Set B))
  distributive-trunc-Π-Fin-Set (succ-ℕ k) A =
    uniqueness-trunc-Set
      ( Π-Set (Fin-Set (succ-ℕ k)) (λ x → trunc-Set (A x)))
      ( map-Π (λ x → unit-trunc-Set))
      ( λ {l} B →
        is-equiv-left-factor&#39;
          ( precomp (map-Π (λ x → unit-trunc-Set)) (type-Set B))
          ( precomp (ev-Maybe {B = type-trunc-Set ∘ A}) (type-Set B))
          ( is-equiv-comp&#39;
            ( precomp ev-Maybe (type-Set B))
            ( precomp
              ( map-prod (map-Π (λ x → unit-trunc-Set)) unit-trunc-Set)
              ( type-Set B))
            ( is-equiv-right-factor&#39;
              ( ev-pair)
              ( precomp
                ( map-prod (map-Π (λ x → unit-trunc-Set)) unit-trunc-Set)
                ( type-Set B))
              ( is-equiv-ev-pair)
              ( is-equiv-htpy-equiv
                ( ( ( pair
                      ( precomp
                        ( (map-Π (λ x → unit-trunc-Set)))
                        ( A (inr star) → type-Set B))
                      ( is-set-truncation-is-equiv
                        ( Π-Set (Fin-Set k) (λ x → trunc-Set (A (inl x))))
                        ( map-Π (λ x → unit-trunc-Set))
                        { map-equiv
                          ( pr1
                            ( center
                              ( distributive-trunc-Π-Fin-Set k (A ∘ inl))))}
                        ( pr2
                          ( center (distributive-trunc-Π-Fin-Set k (A ∘ inl))))
                        ( is-equiv-map-equiv
                          ( pr1
                            ( center
                              ( distributive-trunc-Π-Fin-Set k (A ∘ inl)))))
                        ( Π-Set&#39; (A (inr star)) (λ a → B)))) ∘e
                    ( equiv-postcomp
                      ( (x : Fin k) → type-trunc-Set (A (inl x)))
                      ( equiv-universal-property-trunc-Set
                        ( A (inr star))
                        ( B)))) ∘e
                  ( equiv-ev-pair))
                ( refl-htpy)))
            ( is-equiv-precomp-is-equiv
              ( ev-Maybe)
              ( dependent-universal-property-Maybe)
              ( type-Set B)))
          ( is-equiv-precomp-is-equiv
            ( ev-Maybe)
            ( dependent-universal-property-Maybe)
            ( type-Set B)))

module _
  {l : Level} (k : ℕ) (A : Fin k → UU l)
  where

  equiv-distributive-trunc-Π-Fin-Set :
    type-trunc-Set ((x : Fin k) → A x) ≃ ((x : Fin k) → type-trunc-Set (A x))
  equiv-distributive-trunc-Π-Fin-Set =
    pr1 (center (distributive-trunc-Π-Fin-Set k A))

  map-equiv-distributive-trunc-Π-Fin-Set :
    type-trunc-Set ((x : Fin k) → A x) → ((x : Fin k) → type-trunc-Set (A x))
  map-equiv-distributive-trunc-Π-Fin-Set =
    map-equiv equiv-distributive-trunc-Π-Fin-Set

  triangle-distributive-trunc-Π-Fin-Set :
    ( map-equiv-distributive-trunc-Π-Fin-Set ∘ unit-trunc-Set) ~
    ( map-Π (λ x → unit-trunc-Set))
  triangle-distributive-trunc-Π-Fin-Set =
    pr2 (center (distributive-trunc-Π-Fin-Set k A))

module _
  {l1 l2 : Level} {A : UU l1} (B : A → UU l2)
  where

  abstract
    distributive-trunc-Π-count-Set :
      count A → 
      is-contr
        ( Σ ( ( type-trunc-Set ((x : A) → B x)) ≃
              ( (x : A) → type-trunc-Set (B x)))
            ( λ e →
              ( map-equiv e ∘ unit-trunc-Set) ~
              ( map-Π (λ x → unit-trunc-Set))))
    distributive-trunc-Π-count-Set (pair k e) =
      is-contr-equiv
        ( Σ ( ( type-trunc-Set ((x : A) → B x)) ≃
              ( (x : Fin k) → type-trunc-Set (B (map-equiv e x))))
            ( λ f →
              ( map-equiv f ∘ unit-trunc-Set) ~
              ( map-Π (λ x → unit-trunc-Set) ∘ precomp-Π (map-equiv e) B)))
        ( equiv-Σ
          ( λ f →
            ( map-equiv f ∘ unit-trunc-Set) ~
            ( map-Π (λ x → unit-trunc-Set) ∘ precomp-Π (map-equiv e) B))
          ( equiv-postcomp-equiv
            ( equiv-precomp-Π e (type-trunc-Set ∘ B))
            ( type-trunc-Set ((x : A) → B x)))
          ( λ f →
            equiv-map-Π
              ( λ h →
                ( ( inv-equiv equiv-funext) ∘e
                  ( equiv-precomp-Π e
                    ( λ x → Id ((map-equiv f ∘ unit-trunc-Set) h x)
                    ( map-Π (λ y → unit-trunc-Set) h x)))) ∘e
                ( equiv-funext))))
        ( is-contr-equiv&#39;
          ( Σ ( ( type-trunc-Set ((x : Fin k) → B (map-equiv e x))) ≃
                ( (x : Fin k) → type-trunc-Set (B (map-equiv e x))))
              ( λ f →
                ( map-equiv f ∘ unit-trunc-Set) ~
                ( map-Π (λ x → unit-trunc-Set))))
          ( equiv-Σ
            ( λ f →
              ( map-equiv f ∘ unit-trunc-Set) ~
              ( map-Π (λ x → unit-trunc-Set) ∘ precomp-Π (map-equiv e) B))
            ( equiv-precomp-equiv
              ( equiv-trunc-Set (equiv-precomp-Π e B))
              ( (x : Fin k) → type-trunc-Set (B (map-equiv e x))))
            ( λ f →
              equiv-Π
                ( λ h →
                  Id ( map-equiv f
                       ( map-equiv
                         ( equiv-trunc-Set (equiv-precomp-Π e B))
                         ( unit-trunc-Set h)))
                     ( map-Π (λ x → unit-trunc-Set) (λ x → h (map-equiv e x))))
                ( equiv-Π B e (λ x → id-equiv))
                ( λ h →
                  ( ( inv-equiv equiv-funext) ∘e
                    ( equiv-Π
                      ( λ x →
                        Id ( map-equiv f
                             ( map-equiv-trunc-Set
                               ( equiv-precomp-Π e B)
                               ( unit-trunc-Set
                                 ( map-equiv-Π B e (λ x → id-equiv) h)))
                             ( x))
                           ( unit-trunc-Set
                             ( map-equiv-Π B e
                               ( λ z → id-equiv)
                               ( h)
                               ( map-equiv e x))))
                      ( id-equiv)
                      ( λ x →
                        ( equiv-concat
                          ( ap
                            ( λ t → map-equiv f t x)
                            ( ( naturality-trunc-Set (precomp-Π (map-equiv e) B)
                                ( map-equiv-Π B e (λ _ → id-equiv) h)) ∙
                              ( ap
                                ( unit-trunc-Set)
                                ( eq-htpy
                                  ( compute-map-equiv-Π B e
                                    ( λ _ → id-equiv)
                                    ( h))))))
                          ( unit-trunc-Set
                            ( map-equiv-Π B e
                              ( λ _ → id-equiv)
                              ( h)
                              ( map-equiv e x)))) ∘e
                        ( equiv-concat&#39;
                          ( map-equiv f (unit-trunc-Set h) x)
                          ( ap unit-trunc-Set
                            ( inv
                              ( compute-map-equiv-Π B e
                                ( λ _ → id-equiv)
                                ( h)
                                ( x)))))))) ∘e
                  ( equiv-funext))))
          ( distributive-trunc-Π-Fin-Set k (B ∘ map-equiv e)))

module _
  {l1 l2 : Level} {A : UU l1} (B : A → UU l2) (c : count A)
  where

  equiv-distributive-trunc-Π-count-Set :
    ( type-trunc-Set ((x : A) → B x)) ≃ ((x : A) → type-trunc-Set (B x))
  equiv-distributive-trunc-Π-count-Set =
    pr1 (center (distributive-trunc-Π-count-Set B c))

  map-equiv-distributive-trunc-Π-count-Set :
    ( type-trunc-Set ((x : A) → B x)) → ((x : A) → type-trunc-Set (B x))
  map-equiv-distributive-trunc-Π-count-Set =
    map-equiv equiv-distributive-trunc-Π-count-Set

  triangle-distributive-trunc-Π-count-Set :
    ( map-equiv-distributive-trunc-Π-count-Set ∘ unit-trunc-Set) ~
    ( map-Π (λ x → unit-trunc-Set))
  triangle-distributive-trunc-Π-count-Set =
    pr2 (center (distributive-trunc-Π-count-Set B c))

module _
  {l1 l2 : Level} {A : UU l1} (B : A → UU l2) (H : is-finite A)
  where

  abstract
    distributive-trunc-Π-is-finite-Set :
      is-contr
        ( Σ ( ( type-trunc-Set ((x : A) → B x)) ≃
              ( (x : A) → type-trunc-Set (B x)))
            ( λ e →
              ( map-equiv e ∘ unit-trunc-Set) ~
              ( map-Π (λ x → unit-trunc-Set))))
    distributive-trunc-Π-is-finite-Set =
      apply-universal-property-trunc-Prop H
        ( is-contr-Prop _)
        ( distributive-trunc-Π-count-Set B)

  equiv-distributive-trunc-Π-is-finite-Set :
    ( type-trunc-Set ((x : A) → B x)) ≃ ((x : A) → type-trunc-Set (B x))
  equiv-distributive-trunc-Π-is-finite-Set =
    pr1 (center distributive-trunc-Π-is-finite-Set)

  map-equiv-distributive-trunc-Π-is-finite-Set :
    ( type-trunc-Set ((x : A) → B x)) → ((x : A) → type-trunc-Set (B x))
  map-equiv-distributive-trunc-Π-is-finite-Set =
    map-equiv equiv-distributive-trunc-Π-is-finite-Set

  triangle-distributive-trunc-Π-is-finite-Set :
    ( map-equiv-distributive-trunc-Π-is-finite-Set ∘ unit-trunc-Set) ~
    ( map-Π (λ x → unit-trunc-Set))
  triangle-distributive-trunc-Π-is-finite-Set =
    pr2 (center distributive-trunc-Π-is-finite-Set)
    -}</a>
</pre>