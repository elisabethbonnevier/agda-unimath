# Monomorphisms in groups

<pre class="Agda"><a id="36" class="Symbol">{-#</a> <a id="40" class="Keyword">OPTIONS</a> <a id="48" class="Pragma">--without-K</a> <a id="60" class="Pragma">--exact-split</a> <a id="74" class="Symbol">#-}</a>

<a id="79" class="Keyword">module</a> <a id="86" href="group-theory.monomorphisms-groups.html" class="Module">group-theory.monomorphisms-groups</a> <a id="120" class="Keyword">where</a>

<a id="127" class="Keyword">open</a> <a id="132" class="Keyword">import</a> <a id="139" href="category-theory.monomorphisms-large-precategories.html" class="Module">category-theory.monomorphisms-large-precategories</a> <a id="189" class="Keyword">using</a>
  <a id="197" class="Symbol">(</a> <a id="199" href="category-theory.monomorphisms-large-precategories.html#1433" class="Function">is-mono-Large-Precat-Prop</a><a id="224" class="Symbol">;</a> <a id="226" href="category-theory.monomorphisms-large-precategories.html#2161" class="Function">is-mono-iso-Large-Precat</a><a id="250" class="Symbol">)</a>

<a id="253" class="Keyword">open</a> <a id="258" class="Keyword">import</a> <a id="265" href="foundation.propositions.html" class="Module">foundation.propositions</a> <a id="289" class="Keyword">using</a>
  <a id="297" class="Symbol">(</a> <a id="299" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a><a id="306" class="Symbol">;</a> <a id="308" href="foundation-core.propositions.html#1482" class="Function">type-Prop</a><a id="317" class="Symbol">;</a> <a id="319" href="foundation-core.propositions.html#1549" class="Function">is-prop-type-Prop</a><a id="336" class="Symbol">;</a> <a id="338" href="foundation-core.propositions.html#1295" class="Function">is-prop</a><a id="345" class="Symbol">)</a>
<a id="347" class="Keyword">open</a> <a id="352" class="Keyword">import</a> <a id="359" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="386" class="Keyword">using</a> <a id="392" class="Symbol">(</a><a id="393" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="398" class="Symbol">;</a> <a id="400" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="402" class="Symbol">;</a> <a id="404" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="407" class="Symbol">;</a> <a id="409" href="Agda.Primitive.html#780" class="Primitive">lsuc</a><a id="413" class="Symbol">)</a>

<a id="416" class="Keyword">open</a> <a id="421" class="Keyword">import</a> <a id="428" href="group-theory.groups.html" class="Module">group-theory.groups</a> <a id="448" class="Keyword">using</a> <a id="454" class="Symbol">(</a><a id="455" href="group-theory.groups.html#2398" class="Function">Group</a><a id="460" class="Symbol">)</a>
<a id="462" class="Keyword">open</a> <a id="467" class="Keyword">import</a> <a id="474" href="group-theory.homomorphisms-groups.html" class="Module">group-theory.homomorphisms-groups</a> <a id="508" class="Keyword">using</a> <a id="514" class="Symbol">(</a><a id="515" href="group-theory.homomorphisms-groups.html#1617" class="Function">type-hom-Group</a><a id="529" class="Symbol">)</a>
<a id="531" class="Keyword">open</a> <a id="536" class="Keyword">import</a> <a id="543" href="group-theory.isomorphisms-groups.html" class="Module">group-theory.isomorphisms-groups</a> <a id="576" class="Keyword">using</a> <a id="582" class="Symbol">(</a><a id="583" href="group-theory.isomorphisms-groups.html#1701" class="Function">type-iso-Group</a><a id="597" class="Symbol">;</a> <a id="599" href="group-theory.isomorphisms-groups.html#1793" class="Function">hom-iso-Group</a><a id="612" class="Symbol">)</a>
<a id="614" class="Keyword">open</a> <a id="619" class="Keyword">import</a> <a id="626" href="group-theory.precategory-of-groups.html" class="Module">group-theory.precategory-of-groups</a> <a id="661" class="Keyword">using</a> <a id="667" class="Symbol">(</a><a id="668" href="group-theory.precategory-of-groups.html#734" class="Function">Group-Large-Precat</a><a id="686" class="Symbol">)</a>
</pre>
## Idea

A group homomorphism `f : x → y` is a monomorphism if whenever we have two group homomorphisms `g h : w → x` such that `f ∘ g = f ∘ h`, then in fact `g = h`. The way to state this in Homotopy Type Theory is to say that postcomposition by `f` is an embedding.

## Definition

<pre class="Agda"><a id="985" class="Keyword">module</a> <a id="992" href="group-theory.monomorphisms-groups.html#992" class="Module">_</a>
  <a id="996" class="Symbol">{</a><a id="997" href="group-theory.monomorphisms-groups.html#997" class="Bound">l1</a> <a id="1000" href="group-theory.monomorphisms-groups.html#1000" class="Bound">l2</a> <a id="1003" class="Symbol">:</a> <a id="1005" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1010" class="Symbol">}</a> <a id="1012" class="Symbol">(</a><a id="1013" href="group-theory.monomorphisms-groups.html#1013" class="Bound">l3</a> <a id="1016" class="Symbol">:</a> <a id="1018" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1023" class="Symbol">)</a> <a id="1025" class="Symbol">(</a><a id="1026" href="group-theory.monomorphisms-groups.html#1026" class="Bound">G</a> <a id="1028" class="Symbol">:</a> <a id="1030" href="group-theory.groups.html#2398" class="Function">Group</a> <a id="1036" href="group-theory.monomorphisms-groups.html#997" class="Bound">l1</a><a id="1038" class="Symbol">)</a>
  <a id="1042" class="Symbol">(</a><a id="1043" href="group-theory.monomorphisms-groups.html#1043" class="Bound">H</a> <a id="1045" class="Symbol">:</a> <a id="1047" href="group-theory.groups.html#2398" class="Function">Group</a> <a id="1053" href="group-theory.monomorphisms-groups.html#1000" class="Bound">l2</a><a id="1055" class="Symbol">)</a> <a id="1057" class="Symbol">(</a><a id="1058" href="group-theory.monomorphisms-groups.html#1058" class="Bound">f</a> <a id="1060" class="Symbol">:</a> <a id="1062" href="group-theory.homomorphisms-groups.html#1617" class="Function">type-hom-Group</a> <a id="1077" href="group-theory.monomorphisms-groups.html#1026" class="Bound">G</a> <a id="1079" href="group-theory.monomorphisms-groups.html#1043" class="Bound">H</a><a id="1080" class="Symbol">)</a>
  <a id="1084" class="Keyword">where</a>

  <a id="1093" href="group-theory.monomorphisms-groups.html#1093" class="Function">is-mono-Group-Prop</a> <a id="1112" class="Symbol">:</a> <a id="1114" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a> <a id="1122" class="Symbol">(</a><a id="1123" href="group-theory.monomorphisms-groups.html#997" class="Bound">l1</a> <a id="1126" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1128" href="group-theory.monomorphisms-groups.html#1000" class="Bound">l2</a> <a id="1131" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1133" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="1138" href="group-theory.monomorphisms-groups.html#1013" class="Bound">l3</a><a id="1140" class="Symbol">)</a>
  <a id="1144" href="group-theory.monomorphisms-groups.html#1093" class="Function">is-mono-Group-Prop</a> <a id="1163" class="Symbol">=</a>
    <a id="1169" href="category-theory.monomorphisms-large-precategories.html#1433" class="Function">is-mono-Large-Precat-Prop</a> <a id="1195" href="group-theory.precategory-of-groups.html#734" class="Function">Group-Large-Precat</a> <a id="1214" href="group-theory.monomorphisms-groups.html#1013" class="Bound">l3</a> <a id="1217" href="group-theory.monomorphisms-groups.html#1026" class="Bound">G</a> <a id="1219" href="group-theory.monomorphisms-groups.html#1043" class="Bound">H</a> <a id="1221" href="group-theory.monomorphisms-groups.html#1058" class="Bound">f</a>

  <a id="1226" href="group-theory.monomorphisms-groups.html#1226" class="Function">is-mono-Group</a> <a id="1240" class="Symbol">:</a> <a id="1242" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1245" class="Symbol">(</a><a id="1246" href="group-theory.monomorphisms-groups.html#997" class="Bound">l1</a> <a id="1249" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1251" href="group-theory.monomorphisms-groups.html#1000" class="Bound">l2</a> <a id="1254" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1256" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="1261" href="group-theory.monomorphisms-groups.html#1013" class="Bound">l3</a><a id="1263" class="Symbol">)</a>
  <a id="1267" href="group-theory.monomorphisms-groups.html#1226" class="Function">is-mono-Group</a> <a id="1281" class="Symbol">=</a> <a id="1283" href="foundation-core.propositions.html#1482" class="Function">type-Prop</a> <a id="1293" href="group-theory.monomorphisms-groups.html#1093" class="Function">is-mono-Group-Prop</a>

  <a id="1315" href="group-theory.monomorphisms-groups.html#1315" class="Function">is-prop-is-mono-Group</a> <a id="1337" class="Symbol">:</a> <a id="1339" href="foundation-core.propositions.html#1295" class="Function">is-prop</a> <a id="1347" href="group-theory.monomorphisms-groups.html#1226" class="Function">is-mono-Group</a>
  <a id="1363" href="group-theory.monomorphisms-groups.html#1315" class="Function">is-prop-is-mono-Group</a> <a id="1385" class="Symbol">=</a> <a id="1387" href="foundation-core.propositions.html#1549" class="Function">is-prop-type-Prop</a> <a id="1405" href="group-theory.monomorphisms-groups.html#1093" class="Function">is-mono-Group-Prop</a>
</pre>
## Properties

### Isomorphisms are monomorphisms

<pre class="Agda"><a id="1488" class="Keyword">module</a> <a id="1495" href="group-theory.monomorphisms-groups.html#1495" class="Module">_</a>
  <a id="1499" class="Symbol">{</a><a id="1500" href="group-theory.monomorphisms-groups.html#1500" class="Bound">l1</a> <a id="1503" href="group-theory.monomorphisms-groups.html#1503" class="Bound">l2</a> <a id="1506" class="Symbol">:</a> <a id="1508" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1513" class="Symbol">}</a> <a id="1515" class="Symbol">(</a><a id="1516" href="group-theory.monomorphisms-groups.html#1516" class="Bound">l3</a> <a id="1519" class="Symbol">:</a> <a id="1521" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1526" class="Symbol">)</a> <a id="1528" class="Symbol">(</a><a id="1529" href="group-theory.monomorphisms-groups.html#1529" class="Bound">G</a> <a id="1531" class="Symbol">:</a> <a id="1533" href="group-theory.groups.html#2398" class="Function">Group</a> <a id="1539" href="group-theory.monomorphisms-groups.html#1500" class="Bound">l1</a><a id="1541" class="Symbol">)</a>
  <a id="1545" class="Symbol">(</a><a id="1546" href="group-theory.monomorphisms-groups.html#1546" class="Bound">H</a> <a id="1548" class="Symbol">:</a> <a id="1550" href="group-theory.groups.html#2398" class="Function">Group</a> <a id="1556" href="group-theory.monomorphisms-groups.html#1503" class="Bound">l2</a><a id="1558" class="Symbol">)</a> <a id="1560" class="Symbol">(</a><a id="1561" href="group-theory.monomorphisms-groups.html#1561" class="Bound">f</a> <a id="1563" class="Symbol">:</a> <a id="1565" href="group-theory.isomorphisms-groups.html#1701" class="Function">type-iso-Group</a> <a id="1580" href="group-theory.monomorphisms-groups.html#1529" class="Bound">G</a> <a id="1582" href="group-theory.monomorphisms-groups.html#1546" class="Bound">H</a><a id="1583" class="Symbol">)</a>
  <a id="1587" class="Keyword">where</a>

  <a id="1596" href="group-theory.monomorphisms-groups.html#1596" class="Function">is-mono-iso-Group</a> <a id="1614" class="Symbol">:</a>
    <a id="1620" href="group-theory.monomorphisms-groups.html#1226" class="Function">is-mono-Group</a> <a id="1634" href="group-theory.monomorphisms-groups.html#1516" class="Bound">l3</a> <a id="1637" href="group-theory.monomorphisms-groups.html#1529" class="Bound">G</a> <a id="1639" href="group-theory.monomorphisms-groups.html#1546" class="Bound">H</a> <a id="1641" class="Symbol">(</a><a id="1642" href="group-theory.isomorphisms-groups.html#1793" class="Function">hom-iso-Group</a> <a id="1656" href="group-theory.monomorphisms-groups.html#1529" class="Bound">G</a> <a id="1658" href="group-theory.monomorphisms-groups.html#1546" class="Bound">H</a> <a id="1660" href="group-theory.monomorphisms-groups.html#1561" class="Bound">f</a><a id="1661" class="Symbol">)</a>
  <a id="1665" href="group-theory.monomorphisms-groups.html#1596" class="Function">is-mono-iso-Group</a> <a id="1683" class="Symbol">=</a> <a id="1685" href="category-theory.monomorphisms-large-precategories.html#2161" class="Function">is-mono-iso-Large-Precat</a> <a id="1710" href="group-theory.precategory-of-groups.html#734" class="Function">Group-Large-Precat</a> <a id="1729" href="group-theory.monomorphisms-groups.html#1516" class="Bound">l3</a> <a id="1732" href="group-theory.monomorphisms-groups.html#1529" class="Bound">G</a> <a id="1734" href="group-theory.monomorphisms-groups.html#1546" class="Bound">H</a> <a id="1736" href="group-theory.monomorphisms-groups.html#1561" class="Bound">f</a>
</pre>