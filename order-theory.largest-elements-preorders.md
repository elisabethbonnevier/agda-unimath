# Largest elements in preorders

<pre class="Agda"><a id="42" class="Symbol">{-#</a> <a id="46" class="Keyword">OPTIONS</a> <a id="54" class="Pragma">--without-K</a> <a id="66" class="Pragma">--exact-split</a> <a id="80" class="Symbol">#-}</a>

<a id="85" class="Keyword">module</a> <a id="92" href="order-theory.largest-elements-preorders.html" class="Module">order-theory.largest-elements-preorders</a> <a id="132" class="Keyword">where</a>

<a id="139" class="Keyword">open</a> <a id="144" class="Keyword">import</a> <a id="151" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="183" class="Keyword">using</a> <a id="189" class="Symbol">(</a><a id="190" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="191" class="Symbol">;</a> <a id="193" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="197" class="Symbol">;</a> <a id="199" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="202" class="Symbol">;</a> <a id="204" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="207" class="Symbol">)</a>
<a id="209" class="Keyword">open</a> <a id="214" class="Keyword">import</a> <a id="221" href="foundation.propositions.html" class="Module">foundation.propositions</a> <a id="245" class="Keyword">using</a>
  <a id="253" class="Symbol">(</a> <a id="255" href="foundation-core.propositions.html#1322" class="Function">UU-Prop</a><a id="262" class="Symbol">;</a> <a id="264" href="foundation.propositions.html#1941" class="Function">Π-Prop</a><a id="270" class="Symbol">;</a> <a id="272" href="foundation-core.propositions.html#1424" class="Function">type-Prop</a><a id="281" class="Symbol">;</a> <a id="283" href="foundation-core.propositions.html#1246" class="Function">is-prop</a><a id="290" class="Symbol">;</a> <a id="292" href="foundation-core.propositions.html#1491" class="Function">is-prop-type-Prop</a><a id="309" class="Symbol">)</a>
<a id="311" class="Keyword">open</a> <a id="316" class="Keyword">import</a> <a id="323" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="350" class="Keyword">using</a> <a id="356" class="Symbol">(</a><a id="357" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="362" class="Symbol">;</a> <a id="364" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="366" class="Symbol">;</a> <a id="368" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="371" class="Symbol">)</a>

<a id="374" class="Keyword">open</a> <a id="379" class="Keyword">import</a> <a id="386" href="order-theory.preorders.html" class="Module">order-theory.preorders</a> <a id="409" class="Keyword">using</a>
  <a id="417" class="Symbol">(</a> <a id="419" href="order-theory.preorders.html#531" class="Function">Preorder</a><a id="427" class="Symbol">;</a> <a id="429" href="order-theory.preorders.html#873" class="Function">element-Preorder</a><a id="445" class="Symbol">;</a> <a id="447" href="order-theory.preorders.html#928" class="Function">leq-preorder-Prop</a><a id="464" class="Symbol">)</a>
</pre>
## Definition

<pre class="Agda"><a id="490" class="Keyword">module</a> <a id="497" href="order-theory.largest-elements-preorders.html#497" class="Module">_</a>
  <a id="501" class="Symbol">{</a><a id="502" href="order-theory.largest-elements-preorders.html#502" class="Bound">l1</a> <a id="505" href="order-theory.largest-elements-preorders.html#505" class="Bound">l2</a> <a id="508" class="Symbol">:</a> <a id="510" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="515" class="Symbol">}</a> <a id="517" class="Symbol">(</a><a id="518" href="order-theory.largest-elements-preorders.html#518" class="Bound">X</a> <a id="520" class="Symbol">:</a> <a id="522" href="order-theory.preorders.html#531" class="Function">Preorder</a> <a id="531" href="order-theory.largest-elements-preorders.html#502" class="Bound">l1</a> <a id="534" href="order-theory.largest-elements-preorders.html#505" class="Bound">l2</a><a id="536" class="Symbol">)</a>
  <a id="540" class="Keyword">where</a>

  <a id="549" href="order-theory.largest-elements-preorders.html#549" class="Function">is-largest-element-preorder-Prop</a> <a id="582" class="Symbol">:</a> <a id="584" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="601" href="order-theory.largest-elements-preorders.html#518" class="Bound">X</a> <a id="603" class="Symbol">→</a> <a id="605" href="foundation-core.propositions.html#1322" class="Function">UU-Prop</a> <a id="613" class="Symbol">(</a><a id="614" href="order-theory.largest-elements-preorders.html#502" class="Bound">l1</a> <a id="617" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="619" href="order-theory.largest-elements-preorders.html#505" class="Bound">l2</a><a id="621" class="Symbol">)</a>
  <a id="625" href="order-theory.largest-elements-preorders.html#549" class="Function">is-largest-element-preorder-Prop</a> <a id="658" href="order-theory.largest-elements-preorders.html#658" class="Bound">x</a> <a id="660" class="Symbol">=</a>
    <a id="666" href="foundation.propositions.html#1941" class="Function">Π-Prop</a> <a id="673" class="Symbol">(</a><a id="674" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="691" href="order-theory.largest-elements-preorders.html#518" class="Bound">X</a><a id="692" class="Symbol">)</a> <a id="694" class="Symbol">(λ</a> <a id="697" href="order-theory.largest-elements-preorders.html#697" class="Bound">y</a> <a id="699" class="Symbol">→</a> <a id="701" href="order-theory.preorders.html#928" class="Function">leq-preorder-Prop</a> <a id="719" href="order-theory.largest-elements-preorders.html#518" class="Bound">X</a> <a id="721" href="order-theory.largest-elements-preorders.html#697" class="Bound">y</a> <a id="723" href="order-theory.largest-elements-preorders.html#658" class="Bound">x</a><a id="724" class="Symbol">)</a>

  <a id="729" href="order-theory.largest-elements-preorders.html#729" class="Function">is-largest-element-Preorder</a> <a id="757" class="Symbol">:</a> <a id="759" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="776" href="order-theory.largest-elements-preorders.html#518" class="Bound">X</a> <a id="778" class="Symbol">→</a> <a id="780" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="783" class="Symbol">(</a><a id="784" href="order-theory.largest-elements-preorders.html#502" class="Bound">l1</a> <a id="787" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="789" href="order-theory.largest-elements-preorders.html#505" class="Bound">l2</a><a id="791" class="Symbol">)</a>
  <a id="795" href="order-theory.largest-elements-preorders.html#729" class="Function">is-largest-element-Preorder</a> <a id="823" href="order-theory.largest-elements-preorders.html#823" class="Bound">x</a> <a id="825" class="Symbol">=</a> <a id="827" href="foundation-core.propositions.html#1424" class="Function">type-Prop</a> <a id="837" class="Symbol">(</a><a id="838" href="order-theory.largest-elements-preorders.html#549" class="Function">is-largest-element-preorder-Prop</a> <a id="871" href="order-theory.largest-elements-preorders.html#823" class="Bound">x</a><a id="872" class="Symbol">)</a>

  <a id="877" href="order-theory.largest-elements-preorders.html#877" class="Function">is-prop-is-largest-element-Preorder</a> <a id="913" class="Symbol">:</a>
    <a id="919" class="Symbol">(</a><a id="920" href="order-theory.largest-elements-preorders.html#920" class="Bound">x</a> <a id="922" class="Symbol">:</a> <a id="924" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="941" href="order-theory.largest-elements-preorders.html#518" class="Bound">X</a><a id="942" class="Symbol">)</a> <a id="944" class="Symbol">→</a> <a id="946" href="foundation-core.propositions.html#1246" class="Function">is-prop</a> <a id="954" class="Symbol">(</a><a id="955" href="order-theory.largest-elements-preorders.html#729" class="Function">is-largest-element-Preorder</a> <a id="983" href="order-theory.largest-elements-preorders.html#920" class="Bound">x</a><a id="984" class="Symbol">)</a>
  <a id="988" href="order-theory.largest-elements-preorders.html#877" class="Function">is-prop-is-largest-element-Preorder</a> <a id="1024" href="order-theory.largest-elements-preorders.html#1024" class="Bound">x</a> <a id="1026" class="Symbol">=</a>
    <a id="1032" href="foundation-core.propositions.html#1491" class="Function">is-prop-type-Prop</a> <a id="1050" class="Symbol">(</a><a id="1051" href="order-theory.largest-elements-preorders.html#549" class="Function">is-largest-element-preorder-Prop</a> <a id="1084" href="order-theory.largest-elements-preorders.html#1024" class="Bound">x</a><a id="1085" class="Symbol">)</a>

  <a id="1090" href="order-theory.largest-elements-preorders.html#1090" class="Function">largest-element-Preorder</a> <a id="1115" class="Symbol">:</a> <a id="1117" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1120" class="Symbol">(</a><a id="1121" href="order-theory.largest-elements-preorders.html#502" class="Bound">l1</a> <a id="1124" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1126" href="order-theory.largest-elements-preorders.html#505" class="Bound">l2</a><a id="1128" class="Symbol">)</a>
  <a id="1132" href="order-theory.largest-elements-preorders.html#1090" class="Function">largest-element-Preorder</a> <a id="1157" class="Symbol">=</a> <a id="1159" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="1161" class="Symbol">(</a><a id="1162" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="1179" href="order-theory.largest-elements-preorders.html#518" class="Bound">X</a><a id="1180" class="Symbol">)</a> <a id="1182" href="order-theory.largest-elements-preorders.html#729" class="Function">is-largest-element-Preorder</a>
</pre>