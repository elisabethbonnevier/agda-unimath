---
title: Cartesian products of abelian groups
---

<pre class="Agda"><a id="62" class="Symbol">{-#</a> <a id="66" class="Keyword">OPTIONS</a> <a id="74" class="Pragma">--without-K</a> <a id="86" class="Pragma">--exact-split</a> <a id="100" class="Symbol">#-}</a>

<a id="105" class="Keyword">module</a> <a id="112" href="group-theory.cartesian-products-abelian-groups.html" class="Module">group-theory.cartesian-products-abelian-groups</a> <a id="159" class="Keyword">where</a>

<a id="166" class="Keyword">open</a> <a id="171" class="Keyword">import</a> <a id="178" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a>
<a id="210" class="Keyword">open</a> <a id="215" class="Keyword">import</a> <a id="222" href="foundation.equality-cartesian-product-types.html" class="Module">foundation.equality-cartesian-product-types</a>
<a id="266" class="Keyword">open</a> <a id="271" class="Keyword">import</a> <a id="278" href="foundation.identity-types.html" class="Module">foundation.identity-types</a>
<a id="304" class="Keyword">open</a> <a id="309" class="Keyword">import</a> <a id="316" href="foundation.sets.html" class="Module">foundation.sets</a>
<a id="332" class="Keyword">open</a> <a id="337" class="Keyword">import</a> <a id="344" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a>

<a id="372" class="Keyword">open</a> <a id="377" class="Keyword">import</a> <a id="384" href="group-theory.abelian-groups.html" class="Module">group-theory.abelian-groups</a>
<a id="412" class="Keyword">open</a> <a id="417" class="Keyword">import</a> <a id="424" href="group-theory.cartesian-products-groups.html" class="Module">group-theory.cartesian-products-groups</a>
<a id="463" class="Keyword">open</a> <a id="468" class="Keyword">import</a> <a id="475" href="group-theory.groups.html" class="Module">group-theory.groups</a>
<a id="495" class="Keyword">open</a> <a id="500" class="Keyword">import</a> <a id="507" href="group-theory.monoids.html" class="Module">group-theory.monoids</a>
<a id="528" class="Keyword">open</a> <a id="533" class="Keyword">import</a> <a id="540" href="group-theory.semigroups.html" class="Module">group-theory.semigroups</a>
</pre>
## Idea

The cartesian product of two abelian groups `A` and `B` is an abelian group structure on the cartesian product of the underlying sets.

## Definition

<pre class="Agda"><a id="737" class="Keyword">module</a> <a id="744" href="group-theory.cartesian-products-abelian-groups.html#744" class="Module">_</a>
  <a id="748" class="Symbol">{</a><a id="749" href="group-theory.cartesian-products-abelian-groups.html#749" class="Bound">l1</a> <a id="752" href="group-theory.cartesian-products-abelian-groups.html#752" class="Bound">l2</a> <a id="755" class="Symbol">:</a> <a id="757" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="762" class="Symbol">}</a> <a id="764" class="Symbol">(</a><a id="765" href="group-theory.cartesian-products-abelian-groups.html#765" class="Bound">A</a> <a id="767" class="Symbol">:</a> <a id="769" href="group-theory.abelian-groups.html#2453" class="Function">Ab</a> <a id="772" href="group-theory.cartesian-products-abelian-groups.html#749" class="Bound">l1</a><a id="774" class="Symbol">)</a> <a id="776" class="Symbol">(</a><a id="777" href="group-theory.cartesian-products-abelian-groups.html#777" class="Bound">B</a> <a id="779" class="Symbol">:</a> <a id="781" href="group-theory.abelian-groups.html#2453" class="Function">Ab</a> <a id="784" href="group-theory.cartesian-products-abelian-groups.html#752" class="Bound">l2</a><a id="786" class="Symbol">)</a>
  <a id="790" class="Keyword">where</a>

  <a id="799" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a> <a id="813" class="Symbol">:</a> <a id="815" href="group-theory.groups.html#2398" class="Function">Group</a> <a id="821" class="Symbol">(</a><a id="822" href="group-theory.cartesian-products-abelian-groups.html#749" class="Bound">l1</a> <a id="825" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="827" href="group-theory.cartesian-products-abelian-groups.html#752" class="Bound">l2</a><a id="829" class="Symbol">)</a>
  <a id="833" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a> <a id="847" class="Symbol">=</a> <a id="849" href="group-theory.cartesian-products-groups.html#2787" class="Function">prod-Group</a> <a id="860" class="Symbol">(</a><a id="861" href="group-theory.abelian-groups.html#2521" class="Function">group-Ab</a> <a id="870" href="group-theory.cartesian-products-abelian-groups.html#765" class="Bound">A</a><a id="871" class="Symbol">)</a> <a id="873" class="Symbol">(</a><a id="874" href="group-theory.abelian-groups.html#2521" class="Function">group-Ab</a> <a id="883" href="group-theory.cartesian-products-abelian-groups.html#777" class="Bound">B</a><a id="884" class="Symbol">)</a>

  <a id="889" href="group-theory.cartesian-products-abelian-groups.html#889" class="Function">monoid-prod-Ab</a> <a id="904" class="Symbol">:</a> <a id="906" href="group-theory.monoids.html#1054" class="Function">Monoid</a> <a id="913" class="Symbol">(</a><a id="914" href="group-theory.cartesian-products-abelian-groups.html#749" class="Bound">l1</a> <a id="917" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="919" href="group-theory.cartesian-products-abelian-groups.html#752" class="Bound">l2</a><a id="921" class="Symbol">)</a>
  <a id="925" href="group-theory.cartesian-products-abelian-groups.html#889" class="Function">monoid-prod-Ab</a> <a id="940" class="Symbol">=</a> <a id="942" href="group-theory.groups.html#3574" class="Function">monoid-Group</a> <a id="955" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="972" href="group-theory.cartesian-products-abelian-groups.html#972" class="Function">semigroup-prod-Ab</a> <a id="990" class="Symbol">:</a> <a id="992" href="group-theory.semigroups.html#737" class="Function">Semigroup</a> <a id="1002" class="Symbol">(</a><a id="1003" href="group-theory.cartesian-products-abelian-groups.html#749" class="Bound">l1</a> <a id="1006" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1008" href="group-theory.cartesian-products-abelian-groups.html#752" class="Bound">l2</a><a id="1010" class="Symbol">)</a>
  <a id="1014" href="group-theory.cartesian-products-abelian-groups.html#972" class="Function">semigroup-prod-Ab</a> <a id="1032" class="Symbol">=</a> <a id="1034" href="group-theory.groups.html#2520" class="Function">semigroup-Group</a> <a id="1050" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="1067" href="group-theory.cartesian-products-abelian-groups.html#1067" class="Function">set-prod-Ab</a> <a id="1079" class="Symbol">:</a> <a id="1081" href="foundation-core.sets.html#1177" class="Function">UU-Set</a> <a id="1088" class="Symbol">(</a><a id="1089" href="group-theory.cartesian-products-abelian-groups.html#749" class="Bound">l1</a> <a id="1092" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1094" href="group-theory.cartesian-products-abelian-groups.html#752" class="Bound">l2</a><a id="1096" class="Symbol">)</a>
  <a id="1100" href="group-theory.cartesian-products-abelian-groups.html#1067" class="Function">set-prod-Ab</a> <a id="1112" class="Symbol">=</a> <a id="1114" href="group-theory.groups.html#2581" class="Function">set-Group</a> <a id="1124" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="1141" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a> <a id="1154" class="Symbol">:</a> <a id="1156" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1159" class="Symbol">(</a><a id="1160" href="group-theory.cartesian-products-abelian-groups.html#749" class="Bound">l1</a> <a id="1163" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1165" href="group-theory.cartesian-products-abelian-groups.html#752" class="Bound">l2</a><a id="1167" class="Symbol">)</a>
  <a id="1171" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a> <a id="1184" class="Symbol">=</a> <a id="1186" href="group-theory.groups.html#2641" class="Function">type-Group</a> <a id="1197" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="1214" href="group-theory.cartesian-products-abelian-groups.html#1214" class="Function">is-set-type-prod-Ab</a> <a id="1234" class="Symbol">:</a> <a id="1236" href="foundation-core.sets.html#1099" class="Function">is-set</a> <a id="1243" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a>
  <a id="1258" href="group-theory.cartesian-products-abelian-groups.html#1214" class="Function">is-set-type-prod-Ab</a> <a id="1278" class="Symbol">=</a> <a id="1280" href="group-theory.groups.html#2693" class="Function">is-set-type-Group</a> <a id="1298" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="1315" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="1327" class="Symbol">:</a> <a id="1329" class="Symbol">(</a><a id="1330" href="group-theory.cartesian-products-abelian-groups.html#1330" class="Bound">x</a> <a id="1332" href="group-theory.cartesian-products-abelian-groups.html#1332" class="Bound">y</a> <a id="1334" class="Symbol">:</a> <a id="1336" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a><a id="1348" class="Symbol">)</a> <a id="1350" class="Symbol">→</a> <a id="1352" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a>
  <a id="1367" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="1379" class="Symbol">=</a> <a id="1381" href="group-theory.groups.html#2886" class="Function">mul-Group</a> <a id="1391" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="1408" href="group-theory.cartesian-products-abelian-groups.html#1408" class="Function">zero-prod-Ab</a> <a id="1421" class="Symbol">:</a> <a id="1423" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a>
  <a id="1438" href="group-theory.cartesian-products-abelian-groups.html#1408" class="Function">zero-prod-Ab</a> <a id="1451" class="Symbol">=</a> <a id="1453" href="group-theory.groups.html#3677" class="Function">unit-Group</a> <a id="1464" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="1481" href="group-theory.cartesian-products-abelian-groups.html#1481" class="Function">neg-prod-Ab</a> <a id="1493" class="Symbol">:</a> <a id="1495" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a> <a id="1508" class="Symbol">→</a> <a id="1510" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a>
  <a id="1525" href="group-theory.cartesian-products-abelian-groups.html#1481" class="Function">neg-prod-Ab</a> <a id="1537" class="Symbol">=</a> <a id="1539" href="group-theory.groups.html#4466" class="Function">inv-Group</a> <a id="1549" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="1566" href="group-theory.cartesian-products-abelian-groups.html#1566" class="Function">associative-add-prod-Ab</a> <a id="1590" class="Symbol">:</a>
    <a id="1596" class="Symbol">(</a><a id="1597" href="group-theory.cartesian-products-abelian-groups.html#1597" class="Bound">x</a> <a id="1599" href="group-theory.cartesian-products-abelian-groups.html#1599" class="Bound">y</a> <a id="1601" href="group-theory.cartesian-products-abelian-groups.html#1601" class="Bound">z</a> <a id="1603" class="Symbol">:</a> <a id="1605" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a><a id="1617" class="Symbol">)</a> <a id="1619" class="Symbol">→</a>
    <a id="1625" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1628" class="Symbol">(</a><a id="1629" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="1641" class="Symbol">(</a><a id="1642" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="1654" href="group-theory.cartesian-products-abelian-groups.html#1597" class="Bound">x</a> <a id="1656" href="group-theory.cartesian-products-abelian-groups.html#1599" class="Bound">y</a><a id="1657" class="Symbol">)</a> <a id="1659" href="group-theory.cartesian-products-abelian-groups.html#1601" class="Bound">z</a><a id="1660" class="Symbol">)</a> <a id="1662" class="Symbol">(</a><a id="1663" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="1675" href="group-theory.cartesian-products-abelian-groups.html#1597" class="Bound">x</a> <a id="1677" class="Symbol">(</a><a id="1678" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="1690" href="group-theory.cartesian-products-abelian-groups.html#1599" class="Bound">y</a> <a id="1692" href="group-theory.cartesian-products-abelian-groups.html#1601" class="Bound">z</a><a id="1693" class="Symbol">))</a>
  <a id="1698" href="group-theory.cartesian-products-abelian-groups.html#1566" class="Function">associative-add-prod-Ab</a> <a id="1722" class="Symbol">=</a> <a id="1724" href="group-theory.groups.html#3235" class="Function">associative-mul-Group</a> <a id="1746" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="1763" href="group-theory.cartesian-products-abelian-groups.html#1763" class="Function">left-unit-law-add-prod-Ab</a> <a id="1789" class="Symbol">:</a>
    <a id="1795" class="Symbol">(</a><a id="1796" href="group-theory.cartesian-products-abelian-groups.html#1796" class="Bound">x</a> <a id="1798" class="Symbol">:</a> <a id="1800" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a><a id="1812" class="Symbol">)</a> <a id="1814" class="Symbol">→</a> <a id="1816" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1819" class="Symbol">(</a><a id="1820" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="1832" href="group-theory.cartesian-products-abelian-groups.html#1408" class="Function">zero-prod-Ab</a> <a id="1845" href="group-theory.cartesian-products-abelian-groups.html#1796" class="Bound">x</a><a id="1846" class="Symbol">)</a> <a id="1848" href="group-theory.cartesian-products-abelian-groups.html#1796" class="Bound">x</a>
  <a id="1852" href="group-theory.cartesian-products-abelian-groups.html#1763" class="Function">left-unit-law-add-prod-Ab</a> <a id="1878" class="Symbol">=</a> <a id="1880" href="group-theory.groups.html#4094" class="Function">left-unit-law-Group</a> <a id="1900" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="1917" href="group-theory.cartesian-products-abelian-groups.html#1917" class="Function">right-unit-law-add-prod-Ab</a> <a id="1944" class="Symbol">:</a>
    <a id="1950" class="Symbol">(</a><a id="1951" href="group-theory.cartesian-products-abelian-groups.html#1951" class="Bound">x</a> <a id="1953" class="Symbol">:</a> <a id="1955" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a><a id="1967" class="Symbol">)</a> <a id="1969" class="Symbol">→</a> <a id="1971" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1974" class="Symbol">(</a><a id="1975" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="1987" href="group-theory.cartesian-products-abelian-groups.html#1951" class="Bound">x</a> <a id="1989" href="group-theory.cartesian-products-abelian-groups.html#1408" class="Function">zero-prod-Ab</a><a id="2001" class="Symbol">)</a> <a id="2003" href="group-theory.cartesian-products-abelian-groups.html#1951" class="Bound">x</a>
  <a id="2007" href="group-theory.cartesian-products-abelian-groups.html#1917" class="Function">right-unit-law-add-prod-Ab</a> <a id="2034" class="Symbol">=</a> <a id="2036" href="group-theory.groups.html#4224" class="Function">right-unit-law-Group</a> <a id="2057" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="2074" href="group-theory.cartesian-products-abelian-groups.html#2074" class="Function">left-inverse-law-add-prod-Ab</a> <a id="2103" class="Symbol">:</a>
    <a id="2109" class="Symbol">(</a><a id="2110" href="group-theory.cartesian-products-abelian-groups.html#2110" class="Bound">x</a> <a id="2112" class="Symbol">:</a> <a id="2114" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a><a id="2126" class="Symbol">)</a> <a id="2128" class="Symbol">→</a> <a id="2130" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="2133" class="Symbol">(</a><a id="2134" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="2146" class="Symbol">(</a><a id="2147" href="group-theory.cartesian-products-abelian-groups.html#1481" class="Function">neg-prod-Ab</a> <a id="2159" href="group-theory.cartesian-products-abelian-groups.html#2110" class="Bound">x</a><a id="2160" class="Symbol">)</a> <a id="2162" href="group-theory.cartesian-products-abelian-groups.html#2110" class="Bound">x</a><a id="2163" class="Symbol">)</a> <a id="2165" href="group-theory.cartesian-products-abelian-groups.html#1408" class="Function">zero-prod-Ab</a>
  <a id="2180" href="group-theory.cartesian-products-abelian-groups.html#2074" class="Function">left-inverse-law-add-prod-Ab</a> <a id="2209" class="Symbol">=</a> <a id="2211" href="group-theory.groups.html#4544" class="Function">left-inverse-law-Group</a> <a id="2234" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="2251" href="group-theory.cartesian-products-abelian-groups.html#2251" class="Function">right-inverse-law-add-prod-Ab</a> <a id="2281" class="Symbol">:</a>
    <a id="2287" class="Symbol">(</a><a id="2288" href="group-theory.cartesian-products-abelian-groups.html#2288" class="Bound">x</a> <a id="2290" class="Symbol">:</a> <a id="2292" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a><a id="2304" class="Symbol">)</a> <a id="2306" class="Symbol">→</a> <a id="2308" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="2311" class="Symbol">(</a><a id="2312" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="2324" href="group-theory.cartesian-products-abelian-groups.html#2288" class="Bound">x</a> <a id="2326" class="Symbol">(</a><a id="2327" href="group-theory.cartesian-products-abelian-groups.html#1481" class="Function">neg-prod-Ab</a> <a id="2339" href="group-theory.cartesian-products-abelian-groups.html#2288" class="Bound">x</a><a id="2340" class="Symbol">))</a> <a id="2343" href="group-theory.cartesian-products-abelian-groups.html#1408" class="Function">zero-prod-Ab</a>
  <a id="2358" href="group-theory.cartesian-products-abelian-groups.html#2251" class="Function">right-inverse-law-add-prod-Ab</a> <a id="2388" class="Symbol">=</a> <a id="2390" href="group-theory.groups.html#4695" class="Function">right-inverse-law-Group</a> <a id="2414" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>

  <a id="2431" href="group-theory.cartesian-products-abelian-groups.html#2431" class="Function">commutative-add-prod-Ab</a> <a id="2455" class="Symbol">:</a>
    <a id="2461" class="Symbol">(</a><a id="2462" href="group-theory.cartesian-products-abelian-groups.html#2462" class="Bound">x</a> <a id="2464" href="group-theory.cartesian-products-abelian-groups.html#2464" class="Bound">y</a> <a id="2466" class="Symbol">:</a> <a id="2468" href="group-theory.cartesian-products-abelian-groups.html#1141" class="Function">type-prod-Ab</a><a id="2480" class="Symbol">)</a> <a id="2482" class="Symbol">→</a> <a id="2484" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="2487" class="Symbol">(</a><a id="2488" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="2500" href="group-theory.cartesian-products-abelian-groups.html#2462" class="Bound">x</a> <a id="2502" href="group-theory.cartesian-products-abelian-groups.html#2464" class="Bound">y</a><a id="2503" class="Symbol">)</a> <a id="2505" class="Symbol">(</a><a id="2506" href="group-theory.cartesian-products-abelian-groups.html#1315" class="Function">add-prod-Ab</a> <a id="2518" href="group-theory.cartesian-products-abelian-groups.html#2464" class="Bound">y</a> <a id="2520" href="group-theory.cartesian-products-abelian-groups.html#2462" class="Bound">x</a><a id="2521" class="Symbol">)</a>
  <a id="2525" href="group-theory.cartesian-products-abelian-groups.html#2431" class="Function">commutative-add-prod-Ab</a> <a id="2549" class="Symbol">(</a><a id="2550" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="2555" href="group-theory.cartesian-products-abelian-groups.html#2555" class="Bound">x1</a> <a id="2558" href="group-theory.cartesian-products-abelian-groups.html#2558" class="Bound">y1</a><a id="2560" class="Symbol">)</a> <a id="2562" class="Symbol">(</a><a id="2563" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="2568" href="group-theory.cartesian-products-abelian-groups.html#2568" class="Bound">x2</a> <a id="2571" href="group-theory.cartesian-products-abelian-groups.html#2571" class="Bound">y2</a><a id="2573" class="Symbol">)</a> <a id="2575" class="Symbol">=</a>
    <a id="2581" href="foundation.equality-cartesian-product-types.html#1267" class="Function">eq-pair</a> <a id="2589" class="Symbol">(</a><a id="2590" href="group-theory.abelian-groups.html#5002" class="Function">commutative-add-Ab</a> <a id="2609" href="group-theory.cartesian-products-abelian-groups.html#765" class="Bound">A</a> <a id="2611" href="group-theory.cartesian-products-abelian-groups.html#2555" class="Bound">x1</a> <a id="2614" href="group-theory.cartesian-products-abelian-groups.html#2568" class="Bound">x2</a><a id="2616" class="Symbol">)</a> <a id="2618" class="Symbol">(</a><a id="2619" href="group-theory.abelian-groups.html#5002" class="Function">commutative-add-Ab</a> <a id="2638" href="group-theory.cartesian-products-abelian-groups.html#777" class="Bound">B</a> <a id="2640" href="group-theory.cartesian-products-abelian-groups.html#2558" class="Bound">y1</a> <a id="2643" href="group-theory.cartesian-products-abelian-groups.html#2571" class="Bound">y2</a><a id="2645" class="Symbol">)</a>

  <a id="2650" href="group-theory.cartesian-products-abelian-groups.html#2650" class="Function">prod-Ab</a> <a id="2658" class="Symbol">:</a> <a id="2660" href="group-theory.abelian-groups.html#2453" class="Function">Ab</a> <a id="2663" class="Symbol">(</a><a id="2664" href="group-theory.cartesian-products-abelian-groups.html#749" class="Bound">l1</a> <a id="2667" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="2669" href="group-theory.cartesian-products-abelian-groups.html#752" class="Bound">l2</a><a id="2671" class="Symbol">)</a>
  <a id="2675" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="2679" href="group-theory.cartesian-products-abelian-groups.html#2650" class="Function">prod-Ab</a> <a id="2687" class="Symbol">=</a> <a id="2689" href="group-theory.cartesian-products-abelian-groups.html#799" class="Function">group-prod-Ab</a>
  <a id="2705" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="2709" href="group-theory.cartesian-products-abelian-groups.html#2650" class="Function">prod-Ab</a> <a id="2717" class="Symbol">=</a> <a id="2719" href="group-theory.cartesian-products-abelian-groups.html#2431" class="Function">commutative-add-prod-Ab</a>
</pre>