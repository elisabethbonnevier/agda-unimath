# Initial object of a precategory

<pre class="Agda"><a id="44" class="Symbol">{-#</a> <a id="48" class="Keyword">OPTIONS</a> <a id="56" class="Pragma">--without-K</a> <a id="68" class="Pragma">--exact-split</a> <a id="82" class="Symbol">#-}</a>

<a id="87" class="Keyword">module</a> <a id="94" href="category-theory.initial-objects-precategories.html" class="Module">category-theory.initial-objects-precategories</a> <a id="140" class="Keyword">where</a>

<a id="147" class="Keyword">open</a> <a id="152" class="Keyword">import</a> <a id="159" href="category-theory.precategories.html" class="Module">category-theory.precategories</a> <a id="189" class="Keyword">using</a>
  <a id="197" class="Symbol">(</a> <a id="199" href="category-theory.precategories.html#2242" class="Function">Precat</a><a id="205" class="Symbol">;</a> <a id="207" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a><a id="217" class="Symbol">;</a> <a id="219" href="category-theory.precategories.html#2674" class="Function">type-hom-Precat</a><a id="234" class="Symbol">)</a>
<a id="236" class="Keyword">open</a> <a id="241" class="Keyword">import</a> <a id="248" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a> <a id="278" class="Keyword">using</a> <a id="284" class="Symbol">(</a><a id="285" href="foundation-core.contractible-types.html#992" class="Function">is-contr</a><a id="293" class="Symbol">)</a>
<a id="295" class="Keyword">open</a> <a id="300" class="Keyword">import</a> <a id="307" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="339" class="Keyword">using</a> <a id="345" class="Symbol">(</a><a id="346" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="347" class="Symbol">;</a> <a id="349" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="352" class="Symbol">;</a> <a id="354" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="357" class="Symbol">)</a>
<a id="359" class="Keyword">open</a> <a id="364" class="Keyword">import</a> <a id="371" href="foundation-core.identity-types.html" class="Module">foundation-core.identity-types</a> <a id="402" class="Keyword">using</a> <a id="408" class="Symbol">(</a><a id="409" href="foundation-core.identity-types.html#641" class="Datatype">Id</a><a id="411" class="Symbol">)</a>
<a id="413" class="Keyword">open</a> <a id="418" class="Keyword">import</a> <a id="425" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="452" class="Keyword">using</a> <a id="458" class="Symbol">(</a><a id="459" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="461" class="Symbol">;</a> <a id="463" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="468" class="Symbol">;</a> <a id="470" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="473" class="Symbol">)</a>
</pre>
## Idea

The initial object of a precategory (if it exists) is an object with the universal property that there is a unique morphism from it to any object.

## Definition

<pre class="Agda"><a id="initial-object"></a><a id="660" href="category-theory.initial-objects-precategories.html#660" class="Function">initial-object</a> <a id="675" class="Symbol">:</a> <a id="677" class="Symbol">{</a><a id="678" href="category-theory.initial-objects-precategories.html#678" class="Bound">l1</a> <a id="681" href="category-theory.initial-objects-precategories.html#681" class="Bound">l2</a> <a id="684" class="Symbol">:</a> <a id="686" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="691" class="Symbol">}</a> <a id="693" class="Symbol">(</a><a id="694" href="category-theory.initial-objects-precategories.html#694" class="Bound">C</a> <a id="696" class="Symbol">:</a> <a id="698" href="category-theory.precategories.html#2242" class="Function">Precat</a> <a id="705" href="category-theory.initial-objects-precategories.html#678" class="Bound">l1</a> <a id="708" href="category-theory.initial-objects-precategories.html#681" class="Bound">l2</a><a id="710" class="Symbol">)</a> <a id="712" class="Symbol">→</a> <a id="714" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="717" class="Symbol">(</a><a id="718" href="category-theory.initial-objects-precategories.html#678" class="Bound">l1</a> <a id="721" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="723" href="category-theory.initial-objects-precategories.html#681" class="Bound">l2</a><a id="725" class="Symbol">)</a>
<a id="727" href="category-theory.initial-objects-precategories.html#660" class="Function">initial-object</a> <a id="742" href="category-theory.initial-objects-precategories.html#742" class="Bound">C</a> <a id="744" class="Symbol">=</a>
  <a id="748" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="750" class="Symbol">(</a><a id="751" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a> <a id="762" href="category-theory.initial-objects-precategories.html#742" class="Bound">C</a><a id="763" class="Symbol">)</a> <a id="765" class="Symbol">λ</a> <a id="767" href="category-theory.initial-objects-precategories.html#767" class="Bound">i</a> <a id="769" class="Symbol">→</a>
    <a id="775" class="Symbol">(</a><a id="776" href="category-theory.initial-objects-precategories.html#776" class="Bound">x</a> <a id="778" class="Symbol">:</a> <a id="780" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a> <a id="791" href="category-theory.initial-objects-precategories.html#742" class="Bound">C</a><a id="792" class="Symbol">)</a> <a id="794" class="Symbol">→</a> <a id="796" href="foundation-core.contractible-types.html#992" class="Function">is-contr</a> <a id="805" class="Symbol">(</a><a id="806" href="category-theory.precategories.html#2674" class="Function">type-hom-Precat</a> <a id="822" href="category-theory.initial-objects-precategories.html#742" class="Bound">C</a> <a id="824" href="category-theory.initial-objects-precategories.html#767" class="Bound">i</a> <a id="826" href="category-theory.initial-objects-precategories.html#776" class="Bound">x</a><a id="827" class="Symbol">)</a>

<a id="830" class="Keyword">module</a> <a id="837" href="category-theory.initial-objects-precategories.html#837" class="Module">_</a> <a id="839" class="Symbol">{</a><a id="840" href="category-theory.initial-objects-precategories.html#840" class="Bound">l1</a> <a id="843" href="category-theory.initial-objects-precategories.html#843" class="Bound">l2</a> <a id="846" class="Symbol">:</a> <a id="848" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="853" class="Symbol">}</a> <a id="855" class="Symbol">(</a><a id="856" href="category-theory.initial-objects-precategories.html#856" class="Bound">C</a> <a id="858" class="Symbol">:</a> <a id="860" href="category-theory.precategories.html#2242" class="Function">Precat</a> <a id="867" href="category-theory.initial-objects-precategories.html#840" class="Bound">l1</a> <a id="870" href="category-theory.initial-objects-precategories.html#843" class="Bound">l2</a><a id="872" class="Symbol">)</a>
  <a id="876" class="Symbol">(</a><a id="877" href="category-theory.initial-objects-precategories.html#877" class="Bound">i</a> <a id="879" class="Symbol">:</a> <a id="881" href="category-theory.initial-objects-precategories.html#660" class="Function">initial-object</a> <a id="896" href="category-theory.initial-objects-precategories.html#856" class="Bound">C</a><a id="897" class="Symbol">)</a> <a id="899" class="Keyword">where</a>

  <a id="908" href="category-theory.initial-objects-precategories.html#908" class="Function">object-initial-object</a> <a id="930" class="Symbol">:</a> <a id="932" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a> <a id="943" href="category-theory.initial-objects-precategories.html#856" class="Bound">C</a>
  <a id="947" href="category-theory.initial-objects-precategories.html#908" class="Function">object-initial-object</a> <a id="969" class="Symbol">=</a> <a id="971" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="975" href="category-theory.initial-objects-precategories.html#877" class="Bound">i</a>

  <a id="980" href="category-theory.initial-objects-precategories.html#980" class="Function">morphism-initial-object</a> <a id="1004" class="Symbol">:</a>
    <a id="1010" class="Symbol">(</a><a id="1011" href="category-theory.initial-objects-precategories.html#1011" class="Bound">x</a> <a id="1013" class="Symbol">:</a> <a id="1015" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a> <a id="1026" href="category-theory.initial-objects-precategories.html#856" class="Bound">C</a><a id="1027" class="Symbol">)</a> <a id="1029" class="Symbol">→</a>
    <a id="1035" href="category-theory.precategories.html#2674" class="Function">type-hom-Precat</a> <a id="1051" href="category-theory.initial-objects-precategories.html#856" class="Bound">C</a> <a id="1053" href="category-theory.initial-objects-precategories.html#908" class="Function">object-initial-object</a> <a id="1075" href="category-theory.initial-objects-precategories.html#1011" class="Bound">x</a>
  <a id="1079" href="category-theory.initial-objects-precategories.html#980" class="Function">morphism-initial-object</a> <a id="1103" href="category-theory.initial-objects-precategories.html#1103" class="Bound">x</a> <a id="1105" class="Symbol">=</a> <a id="1107" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1111" class="Symbol">(</a><a id="1112" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1116" href="category-theory.initial-objects-precategories.html#877" class="Bound">i</a> <a id="1118" href="category-theory.initial-objects-precategories.html#1103" class="Bound">x</a><a id="1119" class="Symbol">)</a>

  <a id="1124" href="category-theory.initial-objects-precategories.html#1124" class="Function">is-unique-morphism-initial-object</a> <a id="1158" class="Symbol">:</a>
    <a id="1164" class="Symbol">(</a><a id="1165" href="category-theory.initial-objects-precategories.html#1165" class="Bound">x</a> <a id="1167" class="Symbol">:</a> <a id="1169" href="category-theory.precategories.html#2555" class="Function">obj-Precat</a> <a id="1180" href="category-theory.initial-objects-precategories.html#856" class="Bound">C</a><a id="1181" class="Symbol">)</a> <a id="1183" class="Symbol">→</a>
    <a id="1189" class="Symbol">(</a><a id="1190" href="category-theory.initial-objects-precategories.html#1190" class="Bound">f</a> <a id="1192" class="Symbol">:</a> <a id="1194" href="category-theory.precategories.html#2674" class="Function">type-hom-Precat</a> <a id="1210" href="category-theory.initial-objects-precategories.html#856" class="Bound">C</a> <a id="1212" href="category-theory.initial-objects-precategories.html#908" class="Function">object-initial-object</a> <a id="1234" href="category-theory.initial-objects-precategories.html#1165" class="Bound">x</a><a id="1235" class="Symbol">)</a> <a id="1237" class="Symbol">→</a>
    <a id="1243" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1246" class="Symbol">(</a><a id="1247" href="category-theory.initial-objects-precategories.html#980" class="Function">morphism-initial-object</a> <a id="1271" href="category-theory.initial-objects-precategories.html#1165" class="Bound">x</a><a id="1272" class="Symbol">)</a> <a id="1274" href="category-theory.initial-objects-precategories.html#1190" class="Bound">f</a>
  <a id="1278" href="category-theory.initial-objects-precategories.html#1124" class="Function">is-unique-morphism-initial-object</a> <a id="1312" href="category-theory.initial-objects-precategories.html#1312" class="Bound">x</a> <a id="1314" class="Symbol">=</a> <a id="1316" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1320" class="Symbol">(</a><a id="1321" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1325" href="category-theory.initial-objects-precategories.html#877" class="Bound">i</a> <a id="1327" href="category-theory.initial-objects-precategories.html#1312" class="Bound">x</a><a id="1328" class="Symbol">)</a>
</pre>