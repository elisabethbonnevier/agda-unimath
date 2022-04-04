---
title: Univalent Combinatorics
---

<pre class="Agda"><a id="49" class="Symbol">{-#</a> <a id="53" class="Keyword">OPTIONS</a> <a id="61" class="Pragma">--without-K</a> <a id="73" class="Pragma">--exact-split</a> <a id="87" class="Symbol">#-}</a>

<a id="92" class="Keyword">module</a> <a id="99" href="univalent-combinatorics.html" class="Module">univalent-combinatorics</a> <a id="123" class="Keyword">where</a>

<a id="130" class="Keyword">open</a> <a id="135" class="Keyword">import</a> <a id="142" href="univalent-combinatorics.2-element-decidable-subtypes.html" class="Module">univalent-combinatorics.2-element-decidable-subtypes</a> <a id="195" class="Keyword">public</a>
<a id="202" class="Keyword">open</a> <a id="207" class="Keyword">import</a> <a id="214" href="univalent-combinatorics.2-element-subtypes.html" class="Module">univalent-combinatorics.2-element-subtypes</a> <a id="257" class="Keyword">public</a>
<a id="264" class="Keyword">open</a> <a id="269" class="Keyword">import</a> <a id="276" href="univalent-combinatorics.2-element-types.html" class="Module">univalent-combinatorics.2-element-types</a> <a id="316" class="Keyword">public</a>
<a id="323" class="Keyword">open</a> <a id="328" class="Keyword">import</a> <a id="335" href="univalent-combinatorics.binomial-types.html" class="Module">univalent-combinatorics.binomial-types</a> <a id="374" class="Keyword">public</a>
<a id="381" class="Keyword">open</a> <a id="386" class="Keyword">import</a> <a id="393" href="univalent-combinatorics.cartesian-product-types.html" class="Module">univalent-combinatorics.cartesian-product-types</a> <a id="441" class="Keyword">public</a>
<a id="448" class="Keyword">open</a> <a id="453" class="Keyword">import</a> <a id="460" href="univalent-combinatorics.classical-finite-types.html" class="Module">univalent-combinatorics.classical-finite-types</a>
<a id="507" class="Keyword">open</a> <a id="512" class="Keyword">import</a> <a id="519" href="univalent-combinatorics.complements-isolated-points.html" class="Module">univalent-combinatorics.complements-isolated-points</a> <a id="571" class="Keyword">public</a>
<a id="578" class="Keyword">open</a> <a id="583" class="Keyword">import</a> <a id="590" href="univalent-combinatorics.coproduct-types.html" class="Module">univalent-combinatorics.coproduct-types</a> <a id="630" class="Keyword">public</a>
<a id="637" class="Keyword">open</a> <a id="642" class="Keyword">import</a> <a id="649" href="univalent-combinatorics.counting-decidable-subtypes.html" class="Module">univalent-combinatorics.counting-decidable-subtypes</a> <a id="701" class="Keyword">public</a>
<a id="708" class="Keyword">open</a> <a id="713" class="Keyword">import</a> <a id="720" href="univalent-combinatorics.counting-dependent-function-types.html" class="Module">univalent-combinatorics.counting-dependent-function-types</a> <a id="778" class="Keyword">public</a>
<a id="785" class="Keyword">open</a> <a id="790" class="Keyword">import</a> <a id="797" href="univalent-combinatorics.counting-dependent-pair-types.html" class="Module">univalent-combinatorics.counting-dependent-pair-types</a> <a id="851" class="Keyword">public</a>
<a id="858" class="Keyword">open</a> <a id="863" class="Keyword">import</a> <a id="870" href="univalent-combinatorics.counting-fibers-of-maps.html" class="Module">univalent-combinatorics.counting-fibers-of-maps</a> <a id="918" class="Keyword">public</a>
<a id="925" class="Keyword">open</a> <a id="930" class="Keyword">import</a> <a id="937" href="univalent-combinatorics.counting-function-types.html" class="Module">univalent-combinatorics.counting-function-types</a> <a id="985" class="Keyword">public</a>
<a id="992" class="Keyword">open</a> <a id="997" class="Keyword">import</a> <a id="1004" href="univalent-combinatorics.counting-maybe.html" class="Module">univalent-combinatorics.counting-maybe</a> <a id="1043" class="Keyword">public</a>
<a id="1050" class="Keyword">open</a> <a id="1055" class="Keyword">import</a> <a id="1062" href="univalent-combinatorics.counting.html" class="Module">univalent-combinatorics.counting</a> <a id="1095" class="Keyword">public</a>
<a id="1102" class="Keyword">open</a> <a id="1107" class="Keyword">import</a> <a id="1114" href="univalent-combinatorics.cubes.html" class="Module">univalent-combinatorics.cubes</a> <a id="1144" class="Keyword">public</a>
<a id="1151" class="Keyword">open</a> <a id="1156" class="Keyword">import</a> <a id="1163" href="univalent-combinatorics.decidable-dependent-function-types.html" class="Module">univalent-combinatorics.decidable-dependent-function-types</a> <a id="1222" class="Keyword">public</a>
<a id="1229" class="Keyword">open</a> <a id="1234" class="Keyword">import</a> <a id="1241" href="univalent-combinatorics.decidable-dependent-pair-types.html" class="Module">univalent-combinatorics.decidable-dependent-pair-types</a> <a id="1296" class="Keyword">public</a>
<a id="1303" class="Keyword">open</a> <a id="1308" class="Keyword">import</a> <a id="1315" href="univalent-combinatorics.decidable-subtypes.html" class="Module">univalent-combinatorics.decidable-subtypes</a> <a id="1358" class="Keyword">public</a>
<a id="1365" class="Keyword">open</a> <a id="1370" class="Keyword">import</a> <a id="1377" href="univalent-combinatorics.dependent-product-finite-types.html" class="Module">univalent-combinatorics.dependent-product-finite-types</a> <a id="1432" class="Keyword">public</a>
<a id="1439" class="Keyword">open</a> <a id="1444" class="Keyword">import</a> <a id="1451" href="univalent-combinatorics.dependent-sum-finite-types.html" class="Module">univalent-combinatorics.dependent-sum-finite-types</a> <a id="1502" class="Keyword">public</a>
<a id="1509" class="Keyword">open</a> <a id="1514" class="Keyword">import</a> <a id="1521" href="univalent-combinatorics.distributivity-of-set-truncation-over-finite-products.html" class="Module">univalent-combinatorics.distributivity-of-set-truncation-over-finite-products</a> <a id="1599" class="Keyword">public</a>
<a id="1606" class="Keyword">open</a> <a id="1611" class="Keyword">import</a> <a id="1618" href="univalent-combinatorics.double-counting.html" class="Module">univalent-combinatorics.double-counting</a> <a id="1658" class="Keyword">public</a>
<a id="1665" class="Keyword">open</a> <a id="1670" class="Keyword">import</a> <a id="1677" href="univalent-combinatorics.embeddings.html" class="Module">univalent-combinatorics.embeddings</a> <a id="1712" class="Keyword">public</a>
<a id="1719" class="Keyword">open</a> <a id="1724" class="Keyword">import</a> <a id="1731" href="univalent-combinatorics.embeddings-standard-finite-types.html" class="Module">univalent-combinatorics.embeddings-standard-finite-types</a> <a id="1788" class="Keyword">public</a>
<a id="1795" class="Keyword">open</a> <a id="1800" class="Keyword">import</a> <a id="1807" href="univalent-combinatorics.equality-finite-types.html" class="Module">univalent-combinatorics.equality-finite-types</a> <a id="1853" class="Keyword">public</a>
<a id="1860" class="Keyword">open</a> <a id="1865" class="Keyword">import</a> <a id="1872" href="univalent-combinatorics.equality-standard-finite-types.html" class="Module">univalent-combinatorics.equality-standard-finite-types</a> <a id="1927" class="Keyword">public</a>
<a id="1934" class="Keyword">open</a> <a id="1939" class="Keyword">import</a> <a id="1946" href="univalent-combinatorics.equivalences-cubes.html" class="Module">univalent-combinatorics.equivalences-cubes</a> <a id="1989" class="Keyword">public</a>
<a id="1996" class="Keyword">open</a> <a id="2001" class="Keyword">import</a> <a id="2008" href="univalent-combinatorics.equivalences-standard-finite-types.html" class="Module">univalent-combinatorics.equivalences-standard-finite-types</a> <a id="2067" class="Keyword">public</a>
<a id="2074" class="Keyword">open</a> <a id="2079" class="Keyword">import</a> <a id="2086" href="univalent-combinatorics.equivalences.html" class="Module">univalent-combinatorics.equivalences</a> <a id="2123" class="Keyword">public</a>
<a id="2130" class="Keyword">open</a> <a id="2135" class="Keyword">import</a> <a id="2142" href="univalent-combinatorics.fibers-of-maps-between-finite-types.html" class="Module">univalent-combinatorics.fibers-of-maps-between-finite-types</a> <a id="2202" class="Keyword">public</a>
<a id="2209" class="Keyword">open</a> <a id="2214" class="Keyword">import</a> <a id="2221" href="univalent-combinatorics.finite-choice.html" class="Module">univalent-combinatorics.finite-choice</a> <a id="2259" class="Keyword">public</a>
<a id="2266" class="Keyword">open</a> <a id="2271" class="Keyword">import</a> <a id="2278" href="univalent-combinatorics.finite-connected-components.html" class="Module">univalent-combinatorics.finite-connected-components</a> <a id="2330" class="Keyword">public</a>
<a id="2337" class="Keyword">open</a> <a id="2342" class="Keyword">import</a> <a id="2349" href="univalent-combinatorics.finite-function-types.html" class="Module">univalent-combinatorics.finite-function-types</a> <a id="2395" class="Keyword">public</a>
<a id="2402" class="Keyword">open</a> <a id="2407" class="Keyword">import</a> <a id="2414" href="univalent-combinatorics.finite-presentations.html" class="Module">univalent-combinatorics.finite-presentations</a> <a id="2459" class="Keyword">public</a>
<a id="2466" class="Keyword">open</a> <a id="2471" class="Keyword">import</a> <a id="2478" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a> <a id="2515" class="Keyword">public</a>
<a id="2522" class="Keyword">open</a> <a id="2527" class="Keyword">import</a> <a id="2534" href="univalent-combinatorics.presented-pi-finite-types.html" class="Module">univalent-combinatorics.presented-pi-finite-types</a> <a id="2584" class="Keyword">public</a>
<a id="2591" class="Keyword">open</a> <a id="2596" class="Keyword">import</a> <a id="2603" href="univalent-combinatorics.finitely-presented-types.html" class="Module">univalent-combinatorics.finitely-presented-types</a> <a id="2652" class="Keyword">public</a>
<a id="2659" class="Keyword">open</a> <a id="2664" class="Keyword">import</a> <a id="2671" href="univalent-combinatorics.image-of-maps.html" class="Module">univalent-combinatorics.image-of-maps</a> <a id="2709" class="Keyword">public</a>
<a id="2716" class="Keyword">open</a> <a id="2721" class="Keyword">import</a> <a id="2728" href="univalent-combinatorics.inequality-types-with-counting.html" class="Module">univalent-combinatorics.inequality-types-with-counting</a> <a id="2783" class="Keyword">public</a>
<a id="2790" class="Keyword">open</a> <a id="2795" class="Keyword">import</a> <a id="2802" href="univalent-combinatorics.injective-maps.html" class="Module">univalent-combinatorics.injective-maps</a> <a id="2841" class="Keyword">public</a>
<a id="2848" class="Keyword">open</a> <a id="2853" class="Keyword">import</a> <a id="2860" href="univalent-combinatorics.lists.html" class="Module">univalent-combinatorics.lists</a> <a id="2890" class="Keyword">public</a>
<a id="2897" class="Keyword">open</a> <a id="2902" class="Keyword">import</a> <a id="2909" href="univalent-combinatorics.maybe.html" class="Module">univalent-combinatorics.maybe</a> <a id="2939" class="Keyword">public</a>
<a id="2946" class="Keyword">open</a> <a id="2951" class="Keyword">import</a> <a id="2958" href="univalent-combinatorics.orientations-cubes.html" class="Module">univalent-combinatorics.orientations-cubes</a> <a id="3001" class="Keyword">public</a>
<a id="3008" class="Keyword">open</a> <a id="3013" class="Keyword">import</a> <a id="3020" href="univalent-combinatorics.pi-finite-types.html" class="Module">univalent-combinatorics.pi-finite-types</a> <a id="3060" class="Keyword">public</a>
<a id="3067" class="Keyword">open</a> <a id="3072" class="Keyword">import</a> <a id="3079" href="univalent-combinatorics.pigeonhole-principle.html" class="Module">univalent-combinatorics.pigeonhole-principle</a> <a id="3124" class="Keyword">public</a>
<a id="3131" class="Keyword">open</a> <a id="3136" class="Keyword">import</a> <a id="3143" href="univalent-combinatorics.ramsey-theory.html" class="Module">univalent-combinatorics.ramsey-theory</a> <a id="3181" class="Keyword">public</a>
<a id="3188" class="Keyword">open</a> <a id="3193" class="Keyword">import</a> <a id="3200" href="univalent-combinatorics.retracts-of-finite-types.html" class="Module">univalent-combinatorics.retracts-of-finite-types</a> <a id="3249" class="Keyword">public</a>
<a id="3256" class="Keyword">open</a> <a id="3261" class="Keyword">import</a> <a id="3268" href="univalent-combinatorics.skipping-element-standard-finite-types.html" class="Module">univalent-combinatorics.skipping-element-standard-finite-types</a> <a id="3331" class="Keyword">public</a>
<a id="3338" class="Keyword">open</a> <a id="3343" class="Keyword">import</a> <a id="3350" href="univalent-combinatorics.standard-finite-pruned-trees.html" class="Module">univalent-combinatorics.standard-finite-pruned-trees</a> <a id="3403" class="Keyword">public</a>
<a id="3410" class="Keyword">open</a> <a id="3415" class="Keyword">import</a> <a id="3422" href="univalent-combinatorics.standard-finite-trees.html" class="Module">univalent-combinatorics.standard-finite-trees</a> <a id="3468" class="Keyword">public</a>
<a id="3475" class="Keyword">open</a> <a id="3480" class="Keyword">import</a> <a id="3487" href="univalent-combinatorics.standard-finite-types.html" class="Module">univalent-combinatorics.standard-finite-types</a> <a id="3533" class="Keyword">public</a>
<a id="3540" class="Keyword">open</a> <a id="3545" class="Keyword">import</a> <a id="3552" href="univalent-combinatorics.sums-of-natural-numbers.html" class="Module">univalent-combinatorics.sums-of-natural-numbers</a> <a id="3600" class="Keyword">public</a>
<a id="3607" class="Keyword">open</a> <a id="3612" class="Keyword">import</a> <a id="3619" href="univalent-combinatorics.surjective-maps.html" class="Module">univalent-combinatorics.surjective-maps</a> <a id="3659" class="Keyword">public</a>
</pre>