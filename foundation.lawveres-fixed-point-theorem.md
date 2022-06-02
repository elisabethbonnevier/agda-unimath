# Lawvere's fixed point theorem

<pre class="Agda"><a id="42" class="Symbol">{-#</a> <a id="46" class="Keyword">OPTIONS</a> <a id="54" class="Pragma">--without-K</a> <a id="66" class="Pragma">--exact-split</a> <a id="80" class="Symbol">#-}</a>

<a id="85" class="Keyword">module</a> <a id="92" href="foundation.lawveres-fixed-point-theorem.html" class="Module">foundation.lawveres-fixed-point-theorem</a> <a id="132" class="Keyword">where</a>

<a id="139" class="Keyword">open</a> <a id="144" class="Keyword">import</a> <a id="151" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="183" class="Keyword">using</a> <a id="189" class="Symbol">(</a><a id="190" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="191" class="Symbol">;</a> <a id="193" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="197" class="Symbol">;</a> <a id="199" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="202" class="Symbol">;</a> <a id="204" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="207" class="Symbol">)</a>
<a id="209" class="Keyword">open</a> <a id="214" class="Keyword">import</a> <a id="221" href="foundation.existential-quantification.html" class="Module">foundation.existential-quantification</a> <a id="259" class="Keyword">using</a> <a id="265" class="Symbol">(</a><a id="266" href="foundation.existential-quantification.html#1759" class="Function">∃</a><a id="267" class="Symbol">;</a> <a id="269" href="foundation.existential-quantification.html#1645" class="Function">∃-Prop</a><a id="275" class="Symbol">;</a> <a id="277" href="foundation.existential-quantification.html#2219" class="Function">intro-∃</a><a id="284" class="Symbol">)</a>
<a id="286" class="Keyword">open</a> <a id="291" class="Keyword">import</a> <a id="298" href="foundation.function-extensionality.html" class="Module">foundation.function-extensionality</a> <a id="333" class="Keyword">using</a> <a id="339" class="Symbol">(</a><a id="340" href="foundation-core.function-extensionality.html#964" class="Function">htpy-eq</a><a id="347" class="Symbol">)</a>
<a id="349" class="Keyword">open</a> <a id="354" class="Keyword">import</a> <a id="361" href="foundation.identity-types.html" class="Module">foundation.identity-types</a> <a id="387" class="Keyword">using</a> <a id="393" class="Symbol">(</a><a id="394" href="foundation-core.identity-types.html#641" class="Datatype">Id</a><a id="396" class="Symbol">;</a> <a id="398" href="foundation-core.identity-types.html#1552" class="Function">inv</a><a id="401" class="Symbol">)</a>
<a id="403" class="Keyword">open</a> <a id="408" class="Keyword">import</a> <a id="415" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a> <a id="452" class="Keyword">using</a>
  <a id="460" class="Symbol">(</a> <a id="462" href="foundation.propositional-truncations.html#5581" class="Function">apply-universal-property-trunc-Prop</a><a id="497" class="Symbol">)</a>
<a id="499" class="Keyword">open</a> <a id="504" class="Keyword">import</a> <a id="511" href="foundation.surjective-maps.html" class="Module">foundation.surjective-maps</a> <a id="538" class="Keyword">using</a> <a id="544" class="Symbol">(</a><a id="545" href="foundation.surjective-maps.html#1905" class="Function">is-surjective</a><a id="558" class="Symbol">)</a>
<a id="560" class="Keyword">open</a> <a id="565" class="Keyword">import</a> <a id="572" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="599" class="Keyword">using</a> <a id="605" class="Symbol">(</a><a id="606" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="611" class="Symbol">;</a> <a id="613" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="615" class="Symbol">)</a>
</pre>
## Idea

Lawvere's fixed point theorem asserts that if there is a surjective map `A → (A → B)`, then any map `B → B` must have a fixed point.

## Theorem

<pre class="Agda"><a id="785" class="Keyword">abstract</a>
  <a id="fixed-point-theorem-Lawvere"></a><a id="796" href="foundation.lawveres-fixed-point-theorem.html#796" class="Function">fixed-point-theorem-Lawvere</a> <a id="824" class="Symbol">:</a>
    <a id="830" class="Symbol">{</a><a id="831" href="foundation.lawveres-fixed-point-theorem.html#831" class="Bound">l1</a> <a id="834" href="foundation.lawveres-fixed-point-theorem.html#834" class="Bound">l2</a> <a id="837" class="Symbol">:</a> <a id="839" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="844" class="Symbol">}</a> <a id="846" class="Symbol">{</a><a id="847" href="foundation.lawveres-fixed-point-theorem.html#847" class="Bound">A</a> <a id="849" class="Symbol">:</a> <a id="851" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="854" href="foundation.lawveres-fixed-point-theorem.html#831" class="Bound">l1</a><a id="856" class="Symbol">}</a> <a id="858" class="Symbol">{</a><a id="859" href="foundation.lawveres-fixed-point-theorem.html#859" class="Bound">B</a> <a id="861" class="Symbol">:</a> <a id="863" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="866" href="foundation.lawveres-fixed-point-theorem.html#834" class="Bound">l2</a><a id="868" class="Symbol">}</a> <a id="870" class="Symbol">{</a><a id="871" href="foundation.lawveres-fixed-point-theorem.html#871" class="Bound">f</a> <a id="873" class="Symbol">:</a> <a id="875" href="foundation.lawveres-fixed-point-theorem.html#847" class="Bound">A</a> <a id="877" class="Symbol">→</a> <a id="879" href="foundation.lawveres-fixed-point-theorem.html#847" class="Bound">A</a> <a id="881" class="Symbol">→</a> <a id="883" href="foundation.lawveres-fixed-point-theorem.html#859" class="Bound">B</a><a id="884" class="Symbol">}</a> <a id="886" class="Symbol">→</a>
    <a id="892" href="foundation.surjective-maps.html#1905" class="Function">is-surjective</a> <a id="906" href="foundation.lawveres-fixed-point-theorem.html#871" class="Bound">f</a> <a id="908" class="Symbol">→</a> <a id="910" class="Symbol">(</a><a id="911" href="foundation.lawveres-fixed-point-theorem.html#911" class="Bound">h</a> <a id="913" class="Symbol">:</a> <a id="915" href="foundation.lawveres-fixed-point-theorem.html#859" class="Bound">B</a> <a id="917" class="Symbol">→</a> <a id="919" href="foundation.lawveres-fixed-point-theorem.html#859" class="Bound">B</a><a id="920" class="Symbol">)</a> <a id="922" class="Symbol">→</a> <a id="924" href="foundation.existential-quantification.html#1759" class="Function">∃</a> <a id="926" class="Symbol">(λ</a> <a id="929" href="foundation.lawveres-fixed-point-theorem.html#929" class="Bound">b</a> <a id="931" class="Symbol">→</a> <a id="933" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="936" class="Symbol">(</a><a id="937" href="foundation.lawveres-fixed-point-theorem.html#911" class="Bound">h</a> <a id="939" href="foundation.lawveres-fixed-point-theorem.html#929" class="Bound">b</a><a id="940" class="Symbol">)</a> <a id="942" href="foundation.lawveres-fixed-point-theorem.html#929" class="Bound">b</a><a id="943" class="Symbol">)</a>
  <a id="947" href="foundation.lawveres-fixed-point-theorem.html#796" class="Function">fixed-point-theorem-Lawvere</a> <a id="975" class="Symbol">{</a><a id="976" class="Argument">A</a> <a id="978" class="Symbol">=</a> <a id="980" href="foundation.lawveres-fixed-point-theorem.html#980" class="Bound">A</a><a id="981" class="Symbol">}</a> <a id="983" class="Symbol">{</a><a id="984" href="foundation.lawveres-fixed-point-theorem.html#984" class="Bound">B</a><a id="985" class="Symbol">}</a> <a id="987" class="Symbol">{</a><a id="988" href="foundation.lawveres-fixed-point-theorem.html#988" class="Bound">f</a><a id="989" class="Symbol">}</a> <a id="991" href="foundation.lawveres-fixed-point-theorem.html#991" class="Bound">H</a> <a id="993" href="foundation.lawveres-fixed-point-theorem.html#993" class="Bound">h</a> <a id="995" class="Symbol">=</a>
    <a id="1001" href="foundation.propositional-truncations.html#5581" class="Function">apply-universal-property-trunc-Prop</a>
      <a id="1043" class="Symbol">(</a> <a id="1045" href="foundation.lawveres-fixed-point-theorem.html#991" class="Bound">H</a> <a id="1047" href="foundation.lawveres-fixed-point-theorem.html#1174" class="Function">g</a><a id="1048" class="Symbol">)</a>
      <a id="1056" class="Symbol">(</a> <a id="1058" href="foundation.existential-quantification.html#1645" class="Function">∃-Prop</a> <a id="1065" class="Symbol">(λ</a> <a id="1068" href="foundation.lawveres-fixed-point-theorem.html#1068" class="Bound">b</a> <a id="1070" class="Symbol">→</a> <a id="1072" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1075" class="Symbol">(</a><a id="1076" href="foundation.lawveres-fixed-point-theorem.html#993" class="Bound">h</a> <a id="1078" href="foundation.lawveres-fixed-point-theorem.html#1068" class="Bound">b</a><a id="1079" class="Symbol">)</a> <a id="1081" href="foundation.lawveres-fixed-point-theorem.html#1068" class="Bound">b</a><a id="1082" class="Symbol">))</a>
      <a id="1091" class="Symbol">(</a> <a id="1093" class="Symbol">λ</a> <a id="1095" href="foundation.lawveres-fixed-point-theorem.html#1095" class="Bound">p</a> <a id="1097" class="Symbol">→</a> <a id="1099" href="foundation.existential-quantification.html#2219" class="Function">intro-∃</a> <a id="1107" class="Symbol">(</a><a id="1108" href="foundation.lawveres-fixed-point-theorem.html#988" class="Bound">f</a> <a id="1110" class="Symbol">(</a><a id="1111" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1115" href="foundation.lawveres-fixed-point-theorem.html#1095" class="Bound">p</a><a id="1116" class="Symbol">)</a> <a id="1118" class="Symbol">(</a><a id="1119" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1123" href="foundation.lawveres-fixed-point-theorem.html#1095" class="Bound">p</a><a id="1124" class="Symbol">))</a> <a id="1127" class="Symbol">(</a><a id="1128" href="foundation-core.identity-types.html#1552" class="Function">inv</a> <a id="1132" class="Symbol">(</a><a id="1133" href="foundation-core.function-extensionality.html#964" class="Function">htpy-eq</a> <a id="1141" class="Symbol">(</a><a id="1142" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1146" href="foundation.lawveres-fixed-point-theorem.html#1095" class="Bound">p</a><a id="1147" class="Symbol">)</a> <a id="1149" class="Symbol">(</a><a id="1150" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1154" href="foundation.lawveres-fixed-point-theorem.html#1095" class="Bound">p</a><a id="1155" class="Symbol">))))</a>
    <a id="1164" class="Keyword">where</a>
    <a id="1174" href="foundation.lawveres-fixed-point-theorem.html#1174" class="Function">g</a> <a id="1176" class="Symbol">:</a> <a id="1178" href="foundation.lawveres-fixed-point-theorem.html#980" class="Bound">A</a> <a id="1180" class="Symbol">→</a> <a id="1182" href="foundation.lawveres-fixed-point-theorem.html#984" class="Bound">B</a>
    <a id="1188" href="foundation.lawveres-fixed-point-theorem.html#1174" class="Function">g</a> <a id="1190" href="foundation.lawveres-fixed-point-theorem.html#1190" class="Bound">a</a> <a id="1192" class="Symbol">=</a> <a id="1194" href="foundation.lawveres-fixed-point-theorem.html#993" class="Bound">h</a> <a id="1196" class="Symbol">(</a><a id="1197" href="foundation.lawveres-fixed-point-theorem.html#988" class="Bound">f</a> <a id="1199" href="foundation.lawveres-fixed-point-theorem.html#1190" class="Bound">a</a> <a id="1201" href="foundation.lawveres-fixed-point-theorem.html#1190" class="Bound">a</a><a id="1202" class="Symbol">)</a>
</pre>