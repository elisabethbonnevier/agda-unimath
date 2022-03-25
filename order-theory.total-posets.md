# Totally ordered posets

<pre class="Agda"><a id="35" class="Symbol">{-#</a> <a id="39" class="Keyword">OPTIONS</a> <a id="47" class="Pragma">--without-K</a> <a id="59" class="Pragma">--exact-split</a> <a id="73" class="Symbol">#-}</a>

<a id="78" class="Keyword">module</a> <a id="85" href="order-theory.total-posets.html" class="Module">order-theory.total-posets</a> <a id="111" class="Keyword">where</a>

<a id="118" class="Keyword">open</a> <a id="123" class="Keyword">import</a> <a id="130" href="foundation.propositions.html" class="Module">foundation.propositions</a> <a id="154" class="Keyword">using</a> <a id="160" class="Symbol">(</a><a id="161" href="foundation-core.propositions.html#1322" class="Function">UU-Prop</a><a id="168" class="Symbol">;</a> <a id="170" href="foundation-core.propositions.html#1246" class="Function">is-prop</a><a id="177" class="Symbol">)</a>
<a id="179" class="Keyword">open</a> <a id="184" class="Keyword">import</a> <a id="191" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="218" class="Keyword">using</a> <a id="224" class="Symbol">(</a><a id="225" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="230" class="Symbol">;</a> <a id="232" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="234" class="Symbol">;</a> <a id="236" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="239" class="Symbol">)</a>

<a id="242" class="Keyword">open</a> <a id="247" class="Keyword">import</a> <a id="254" href="order-theory.posets.html" class="Module">order-theory.posets</a> <a id="274" class="Keyword">using</a>  <a id="281" class="Symbol">(</a><a id="282" href="order-theory.posets.html#731" class="Function">Poset</a><a id="287" class="Symbol">;</a> <a id="289" href="order-theory.posets.html#1145" class="Function">element-Poset</a><a id="302" class="Symbol">;</a> <a id="304" href="order-theory.posets.html#1761" class="Function">preorder-Poset</a><a id="318" class="Symbol">)</a>
<a id="320" class="Keyword">open</a> <a id="325" class="Keyword">import</a> <a id="332" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a> <a id="361" class="Keyword">using</a>
  <a id="369" class="Symbol">(</a> <a id="371" href="order-theory.total-preorders.html#511" class="Function">incident-preorder-Prop</a><a id="393" class="Symbol">;</a> <a id="395" href="order-theory.total-preorders.html#676" class="Function">incident-Preorder</a><a id="412" class="Symbol">;</a> <a id="414" href="order-theory.total-preorders.html#799" class="Function">is-prop-incident-Preorder</a><a id="439" class="Symbol">;</a>
    <a id="445" href="order-theory.total-preorders.html#976" class="Function">is-total-preorder-Prop</a><a id="467" class="Symbol">;</a> <a id="469" href="order-theory.total-preorders.html#1167" class="Function">is-total-Preorder</a><a id="486" class="Symbol">;</a> <a id="488" href="order-theory.total-preorders.html#1258" class="Function">is-prop-is-total-Preorder</a><a id="513" class="Symbol">)</a>
</pre>
## Definition

<pre class="Agda"><a id="543" class="Keyword">module</a> <a id="550" href="order-theory.total-posets.html#550" class="Module">_</a>
  <a id="554" class="Symbol">{</a><a id="555" href="order-theory.total-posets.html#555" class="Bound">l1</a> <a id="558" href="order-theory.total-posets.html#558" class="Bound">l2</a> <a id="561" class="Symbol">:</a> <a id="563" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="568" class="Symbol">}</a> <a id="570" class="Symbol">(</a><a id="571" href="order-theory.total-posets.html#571" class="Bound">X</a> <a id="573" class="Symbol">:</a> <a id="575" href="order-theory.posets.html#731" class="Function">Poset</a> <a id="581" href="order-theory.total-posets.html#555" class="Bound">l1</a> <a id="584" href="order-theory.total-posets.html#558" class="Bound">l2</a><a id="586" class="Symbol">)</a>
  <a id="590" class="Keyword">where</a>

  <a id="599" href="order-theory.total-posets.html#599" class="Function">incident-poset-Prop</a> <a id="619" class="Symbol">:</a> <a id="621" class="Symbol">(</a><a id="622" href="order-theory.total-posets.html#622" class="Bound">x</a> <a id="624" href="order-theory.total-posets.html#624" class="Bound">y</a> <a id="626" class="Symbol">:</a> <a id="628" href="order-theory.posets.html#1145" class="Function">element-Poset</a> <a id="642" href="order-theory.total-posets.html#571" class="Bound">X</a><a id="643" class="Symbol">)</a> <a id="645" class="Symbol">→</a> <a id="647" href="foundation-core.propositions.html#1322" class="Function">UU-Prop</a> <a id="655" href="order-theory.total-posets.html#558" class="Bound">l2</a>
  <a id="660" href="order-theory.total-posets.html#599" class="Function">incident-poset-Prop</a> <a id="680" class="Symbol">=</a> <a id="682" href="order-theory.total-preorders.html#511" class="Function">incident-preorder-Prop</a> <a id="705" class="Symbol">(</a><a id="706" href="order-theory.posets.html#1761" class="Function">preorder-Poset</a> <a id="721" href="order-theory.total-posets.html#571" class="Bound">X</a><a id="722" class="Symbol">)</a>

  <a id="727" href="order-theory.total-posets.html#727" class="Function">incident-Poset</a> <a id="742" class="Symbol">:</a> <a id="744" class="Symbol">(</a><a id="745" href="order-theory.total-posets.html#745" class="Bound">x</a> <a id="747" href="order-theory.total-posets.html#747" class="Bound">y</a> <a id="749" class="Symbol">:</a> <a id="751" href="order-theory.posets.html#1145" class="Function">element-Poset</a> <a id="765" href="order-theory.total-posets.html#571" class="Bound">X</a><a id="766" class="Symbol">)</a> <a id="768" class="Symbol">→</a> <a id="770" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="773" href="order-theory.total-posets.html#558" class="Bound">l2</a>
  <a id="778" href="order-theory.total-posets.html#727" class="Function">incident-Poset</a> <a id="793" class="Symbol">=</a> <a id="795" href="order-theory.total-preorders.html#676" class="Function">incident-Preorder</a> <a id="813" class="Symbol">(</a><a id="814" href="order-theory.posets.html#1761" class="Function">preorder-Poset</a> <a id="829" href="order-theory.total-posets.html#571" class="Bound">X</a><a id="830" class="Symbol">)</a>

  <a id="835" href="order-theory.total-posets.html#835" class="Function">is-prop-incident-Poset</a> <a id="858" class="Symbol">:</a>
    <a id="864" class="Symbol">(</a><a id="865" href="order-theory.total-posets.html#865" class="Bound">x</a> <a id="867" href="order-theory.total-posets.html#867" class="Bound">y</a> <a id="869" class="Symbol">:</a> <a id="871" href="order-theory.posets.html#1145" class="Function">element-Poset</a> <a id="885" href="order-theory.total-posets.html#571" class="Bound">X</a><a id="886" class="Symbol">)</a> <a id="888" class="Symbol">→</a> <a id="890" href="foundation-core.propositions.html#1246" class="Function">is-prop</a> <a id="898" class="Symbol">(</a><a id="899" href="order-theory.total-posets.html#727" class="Function">incident-Poset</a> <a id="914" href="order-theory.total-posets.html#865" class="Bound">x</a> <a id="916" href="order-theory.total-posets.html#867" class="Bound">y</a><a id="917" class="Symbol">)</a>
  <a id="921" href="order-theory.total-posets.html#835" class="Function">is-prop-incident-Poset</a> <a id="944" class="Symbol">=</a> <a id="946" href="order-theory.total-preorders.html#799" class="Function">is-prop-incident-Preorder</a> <a id="972" class="Symbol">(</a><a id="973" href="order-theory.posets.html#1761" class="Function">preorder-Poset</a> <a id="988" href="order-theory.total-posets.html#571" class="Bound">X</a><a id="989" class="Symbol">)</a>

  <a id="994" href="order-theory.total-posets.html#994" class="Function">is-total-poset-Prop</a> <a id="1014" class="Symbol">:</a> <a id="1016" href="foundation-core.propositions.html#1322" class="Function">UU-Prop</a> <a id="1024" class="Symbol">(</a><a id="1025" href="order-theory.total-posets.html#555" class="Bound">l1</a> <a id="1028" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1030" href="order-theory.total-posets.html#558" class="Bound">l2</a><a id="1032" class="Symbol">)</a>
  <a id="1036" href="order-theory.total-posets.html#994" class="Function">is-total-poset-Prop</a> <a id="1056" class="Symbol">=</a> <a id="1058" href="order-theory.total-preorders.html#976" class="Function">is-total-preorder-Prop</a> <a id="1081" class="Symbol">(</a><a id="1082" href="order-theory.posets.html#1761" class="Function">preorder-Poset</a> <a id="1097" href="order-theory.total-posets.html#571" class="Bound">X</a><a id="1098" class="Symbol">)</a>

  <a id="1103" href="order-theory.total-posets.html#1103" class="Function">is-total-Poset</a> <a id="1118" class="Symbol">:</a> <a id="1120" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1123" class="Symbol">(</a><a id="1124" href="order-theory.total-posets.html#555" class="Bound">l1</a> <a id="1127" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1129" href="order-theory.total-posets.html#558" class="Bound">l2</a><a id="1131" class="Symbol">)</a>
  <a id="1135" href="order-theory.total-posets.html#1103" class="Function">is-total-Poset</a> <a id="1150" class="Symbol">=</a> <a id="1152" href="order-theory.total-preorders.html#1167" class="Function">is-total-Preorder</a> <a id="1170" class="Symbol">(</a><a id="1171" href="order-theory.posets.html#1761" class="Function">preorder-Poset</a> <a id="1186" href="order-theory.total-posets.html#571" class="Bound">X</a><a id="1187" class="Symbol">)</a>

  <a id="1192" href="order-theory.total-posets.html#1192" class="Function">is-prop-is-total-Poset</a> <a id="1215" class="Symbol">:</a> <a id="1217" href="foundation-core.propositions.html#1246" class="Function">is-prop</a> <a id="1225" href="order-theory.total-posets.html#1103" class="Function">is-total-Poset</a>
  <a id="1242" href="order-theory.total-posets.html#1192" class="Function">is-prop-is-total-Poset</a> <a id="1265" class="Symbol">=</a> <a id="1267" href="order-theory.total-preorders.html#1258" class="Function">is-prop-is-total-Preorder</a> <a id="1293" class="Symbol">(</a><a id="1294" href="order-theory.posets.html#1761" class="Function">preorder-Poset</a> <a id="1309" href="order-theory.total-posets.html#571" class="Bound">X</a><a id="1310" class="Symbol">)</a>
</pre>