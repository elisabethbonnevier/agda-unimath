---
title: Wild algebra
---

<pre class="Agda"><a id="38" class="Symbol">{-#</a> <a id="42" class="Keyword">OPTIONS</a> <a id="50" class="Pragma">--without-K</a> <a id="62" class="Pragma">--exact-split</a> <a id="76" class="Symbol">#-}</a>

<a id="81" class="Keyword">module</a> <a id="88" href="structured-types.html" class="Module">structured-types</a> <a id="105" class="Keyword">where</a>
</pre>
<pre class="Agda"><a id="124" class="Keyword">open</a> <a id="129" class="Keyword">import</a> <a id="136" href="structured-types.contractible-pointed-types.html" class="Module">structured-types.contractible-pointed-types</a> <a id="180" class="Keyword">public</a>
<a id="187" class="Keyword">open</a> <a id="192" class="Keyword">import</a> <a id="199" href="structured-types.equivalences-types-equipped-with-endomorphisms.html" class="Module">structured-types.equivalences-types-equipped-with-endomorphisms</a> <a id="263" class="Keyword">public</a>
<a id="270" class="Keyword">open</a> <a id="275" class="Keyword">import</a> <a id="282" href="structured-types.finite-multiplication-magmas.html" class="Module">structured-types.finite-multiplication-magmas</a> <a id="328" class="Keyword">public</a>
<a id="335" class="Keyword">open</a> <a id="340" class="Keyword">import</a> <a id="347" href="structured-types.magmas.html" class="Module">structured-types.magmas</a> <a id="371" class="Keyword">public</a>
<a id="378" class="Keyword">open</a> <a id="383" class="Keyword">import</a> <a id="390" href="structured-types.mere-equivalences-types-equipped-with-endomorphisms.html" class="Module">structured-types.mere-equivalences-types-equipped-with-endomorphisms</a> <a id="459" class="Keyword">public</a>
<a id="466" class="Keyword">open</a> <a id="471" class="Keyword">import</a> <a id="478" href="structured-types.morphisms-magmas.html" class="Module">structured-types.morphisms-magmas</a> <a id="512" class="Keyword">public</a>
<a id="519" class="Keyword">open</a> <a id="524" class="Keyword">import</a> <a id="531" href="structured-types.morphisms-types-equipped-with-endomorphisms.html" class="Module">structured-types.morphisms-types-equipped-with-endomorphisms</a> <a id="592" class="Keyword">public</a>
<a id="599" class="Keyword">open</a> <a id="604" class="Keyword">import</a> <a id="611" href="structured-types.morphisms-wild-unital-magmas.html" class="Module">structured-types.morphisms-wild-unital-magmas</a> <a id="657" class="Keyword">public</a>
<a id="664" class="Keyword">open</a> <a id="669" class="Keyword">import</a> <a id="676" href="structured-types.pointed-dependent-functions.html" class="Module">structured-types.pointed-dependent-functions</a> <a id="721" class="Keyword">public</a>
<a id="728" class="Keyword">open</a> <a id="733" class="Keyword">import</a> <a id="740" href="structured-types.pointed-equivalences.html" class="Module">structured-types.pointed-equivalences</a> <a id="778" class="Keyword">public</a>
<a id="785" class="Keyword">open</a> <a id="790" class="Keyword">import</a> <a id="797" href="structured-types.pointed-families-of-types.html" class="Module">structured-types.pointed-families-of-types</a> <a id="840" class="Keyword">public</a>
<a id="847" class="Keyword">open</a> <a id="852" class="Keyword">import</a> <a id="859" href="structured-types.pointed-homotopies.html" class="Module">structured-types.pointed-homotopies</a> <a id="895" class="Keyword">public</a>
<a id="902" class="Keyword">open</a> <a id="907" class="Keyword">import</a> <a id="914" href="structured-types.pointed-maps.html" class="Module">structured-types.pointed-maps</a> <a id="944" class="Keyword">public</a>
<a id="951" class="Keyword">open</a> <a id="956" class="Keyword">import</a> <a id="963" href="structured-types.pointed-types.html" class="Module">structured-types.pointed-types</a> <a id="994" class="Keyword">public</a>
<a id="1001" class="Keyword">open</a> <a id="1006" class="Keyword">import</a> <a id="1013" href="structured-types.types-equipped-with-endomorphisms.html" class="Module">structured-types.types-equipped-with-endomorphisms</a> <a id="1064" class="Keyword">public</a>
<a id="1071" class="Keyword">open</a> <a id="1076" class="Keyword">import</a> <a id="1083" href="structured-types.universal-property-lists-wild-monoids.html" class="Module">structured-types.universal-property-lists-wild-monoids</a> <a id="1138" class="Keyword">public</a>
<a id="1145" class="Keyword">open</a> <a id="1150" class="Keyword">import</a> <a id="1157" href="structured-types.wild-groups.html" class="Module">structured-types.wild-groups</a> <a id="1186" class="Keyword">public</a>
<a id="1193" class="Keyword">open</a> <a id="1198" class="Keyword">import</a> <a id="1205" href="structured-types.wild-loops.html" class="Module">structured-types.wild-loops</a> <a id="1233" class="Keyword">public</a>
<a id="1240" class="Keyword">open</a> <a id="1245" class="Keyword">import</a> <a id="1252" href="structured-types.wild-monoids.html" class="Module">structured-types.wild-monoids</a> <a id="1282" class="Keyword">public</a>
<a id="1289" class="Keyword">open</a> <a id="1294" class="Keyword">import</a> <a id="1301" href="structured-types.wild-quasigroups.html" class="Module">structured-types.wild-quasigroups</a> <a id="1335" class="Keyword">public</a>
<a id="1342" class="Keyword">open</a> <a id="1347" class="Keyword">import</a> <a id="1354" href="structured-types.wild-semigroups.html" class="Module">structured-types.wild-semigroups</a> <a id="1387" class="Keyword">public</a>
<a id="1394" class="Keyword">open</a> <a id="1399" class="Keyword">import</a> <a id="1406" href="structured-types.wild-unital-magmas.html" class="Module">structured-types.wild-unital-magmas</a> <a id="1442" class="Keyword">public</a>
</pre>