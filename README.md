# Univalent mathematics in Agda

Welcome to the website of the `agda-unimath` formalization project.

[![build](https://github.com/UniMath/agda-unimath/actions/workflows/ci.yaml/badge.svg?branch=master)](https://github.com/UniMath/agda-unimath/actions/workflows/ci.yaml)

<pre class="Agda"><a id="281" class="Symbol">{-#</a> <a id="285" class="Keyword">OPTIONS</a> <a id="293" class="Pragma">--without-K</a> <a id="305" class="Pragma">--exact-split</a> <a id="319" class="Symbol">#-}</a>
</pre>
## Category theory

<pre class="Agda"><a id="356" class="Keyword">open</a> <a id="361" class="Keyword">import</a> <a id="368" href="category-theory.html" class="Module">category-theory</a>
<a id="384" class="Keyword">open</a> <a id="389" class="Keyword">import</a> <a id="396" href="category-theory.adjunctions-large-precategories.html" class="Module">category-theory.adjunctions-large-precategories</a>
<a id="444" class="Keyword">open</a> <a id="449" class="Keyword">import</a> <a id="456" href="category-theory.anafunctors.html" class="Module">category-theory.anafunctors</a>
<a id="484" class="Keyword">open</a> <a id="489" class="Keyword">import</a> <a id="496" href="category-theory.categories.html" class="Module">category-theory.categories</a>
<a id="523" class="Keyword">open</a> <a id="528" class="Keyword">import</a> <a id="535" href="category-theory.equivalences-categories.html" class="Module">category-theory.equivalences-categories</a>
<a id="575" class="Keyword">open</a> <a id="580" class="Keyword">import</a> <a id="587" href="category-theory.equivalences-large-precategories.html" class="Module">category-theory.equivalences-large-precategories</a>
<a id="636" class="Keyword">open</a> <a id="641" class="Keyword">import</a> <a id="648" href="category-theory.equivalences-precategories.html" class="Module">category-theory.equivalences-precategories</a>
<a id="691" class="Keyword">open</a> <a id="696" class="Keyword">import</a> <a id="703" href="category-theory.functors-categories.html" class="Module">category-theory.functors-categories</a>
<a id="739" class="Keyword">open</a> <a id="744" class="Keyword">import</a> <a id="751" href="category-theory.functors-large-precategories.html" class="Module">category-theory.functors-large-precategories</a>
<a id="796" class="Keyword">open</a> <a id="801" class="Keyword">import</a> <a id="808" href="category-theory.functors-precategories.html" class="Module">category-theory.functors-precategories</a>
<a id="847" class="Keyword">open</a> <a id="852" class="Keyword">import</a> <a id="859" href="category-theory.homotopies-natural-transformations-large-precategories.html" class="Module">category-theory.homotopies-natural-transformations-large-precategories</a>
<a id="930" class="Keyword">open</a> <a id="935" class="Keyword">import</a> <a id="942" href="category-theory.initial-objects-precategories.html" class="Module">category-theory.initial-objects-precategories</a>
<a id="988" class="Keyword">open</a> <a id="993" class="Keyword">import</a> <a id="1000" href="category-theory.isomorphisms-categories.html" class="Module">category-theory.isomorphisms-categories</a>
<a id="1040" class="Keyword">open</a> <a id="1045" class="Keyword">import</a> <a id="1052" href="category-theory.isomorphisms-large-precategories.html" class="Module">category-theory.isomorphisms-large-precategories</a>
<a id="1101" class="Keyword">open</a> <a id="1106" class="Keyword">import</a> <a id="1113" href="category-theory.isomorphisms-precategories.html" class="Module">category-theory.isomorphisms-precategories</a>
<a id="1156" class="Keyword">open</a> <a id="1161" class="Keyword">import</a> <a id="1168" href="category-theory.large-categories.html" class="Module">category-theory.large-categories</a>
<a id="1201" class="Keyword">open</a> <a id="1206" class="Keyword">import</a> <a id="1213" href="category-theory.large-precategories.html" class="Module">category-theory.large-precategories</a>
<a id="1249" class="Keyword">open</a> <a id="1254" class="Keyword">import</a> <a id="1261" href="category-theory.monomorphisms-large-precategories.html" class="Module">category-theory.monomorphisms-large-precategories</a>
<a id="1311" class="Keyword">open</a> <a id="1316" class="Keyword">import</a> <a id="1323" href="category-theory.natural-isomorphisms-categories.html" class="Module">category-theory.natural-isomorphisms-categories</a>
<a id="1371" class="Keyword">open</a> <a id="1376" class="Keyword">import</a> <a id="1383" href="category-theory.natural-isomorphisms-large-precategories.html" class="Module">category-theory.natural-isomorphisms-large-precategories</a>
<a id="1440" class="Keyword">open</a> <a id="1445" class="Keyword">import</a> <a id="1452" href="category-theory.natural-isomorphisms-precategories.html" class="Module">category-theory.natural-isomorphisms-precategories</a>
<a id="1503" class="Keyword">open</a> <a id="1508" class="Keyword">import</a> <a id="1515" href="category-theory.natural-transformations-categories.html" class="Module">category-theory.natural-transformations-categories</a>
<a id="1566" class="Keyword">open</a> <a id="1571" class="Keyword">import</a> <a id="1578" href="category-theory.natural-transformations-large-precategories.html" class="Module">category-theory.natural-transformations-large-precategories</a>
<a id="1638" class="Keyword">open</a> <a id="1643" class="Keyword">import</a> <a id="1650" href="category-theory.natural-transformations-precategories.html" class="Module">category-theory.natural-transformations-precategories</a>
<a id="1704" class="Keyword">open</a> <a id="1709" class="Keyword">import</a> <a id="1716" href="category-theory.precategories.html" class="Module">category-theory.precategories</a>
<a id="1746" class="Keyword">open</a> <a id="1751" class="Keyword">import</a> <a id="1758" href="category-theory.slice-precategories.html" class="Module">category-theory.slice-precategories</a>
<a id="1794" class="Keyword">open</a> <a id="1799" class="Keyword">import</a> <a id="1806" href="category-theory.terminal-objects-precategories.html" class="Module">category-theory.terminal-objects-precategories</a>
</pre>
## Elementary number theory

<pre class="Agda"><a id="1895" class="Keyword">open</a> <a id="1900" class="Keyword">import</a> <a id="1907" href="elementary-number-theory.html" class="Module">elementary-number-theory</a>
<a id="1932" class="Keyword">open</a> <a id="1937" class="Keyword">import</a> <a id="1944" href="elementary-number-theory.absolute-value-integers.html" class="Module">elementary-number-theory.absolute-value-integers</a>
<a id="1993" class="Keyword">open</a> <a id="1998" class="Keyword">import</a> <a id="2005" href="elementary-number-theory.addition-integers.html" class="Module">elementary-number-theory.addition-integers</a>
<a id="2048" class="Keyword">open</a> <a id="2053" class="Keyword">import</a> <a id="2060" href="elementary-number-theory.addition-natural-numbers.html" class="Module">elementary-number-theory.addition-natural-numbers</a>
<a id="2110" class="Keyword">open</a> <a id="2115" class="Keyword">import</a> <a id="2122" href="elementary-number-theory.arithmetic-functions.html" class="Module">elementary-number-theory.arithmetic-functions</a>
<a id="2168" class="Keyword">open</a> <a id="2173" class="Keyword">import</a> <a id="2180" href="elementary-number-theory.binomial-coefficients.html" class="Module">elementary-number-theory.binomial-coefficients</a>
<a id="2227" class="Keyword">open</a> <a id="2232" class="Keyword">import</a> <a id="2239" href="elementary-number-theory.bounded-sums-arithmetic-functions.html" class="Module">elementary-number-theory.bounded-sums-arithmetic-functions</a>
<a id="2298" class="Keyword">open</a> <a id="2303" class="Keyword">import</a> <a id="2310" href="elementary-number-theory.catalan-numbers.html" class="Module">elementary-number-theory.catalan-numbers</a>
<a id="2351" class="Keyword">open</a> <a id="2356" class="Keyword">import</a> <a id="2363" href="elementary-number-theory.collatz-bijection.html" class="Module">elementary-number-theory.collatz-bijection</a>
<a id="2406" class="Keyword">open</a> <a id="2411" class="Keyword">import</a> <a id="2418" href="elementary-number-theory.collatz-conjecture.html" class="Module">elementary-number-theory.collatz-conjecture</a>
<a id="2462" class="Keyword">open</a> <a id="2467" class="Keyword">import</a> <a id="2474" href="elementary-number-theory.congruence-integers.html" class="Module">elementary-number-theory.congruence-integers</a>
<a id="2519" class="Keyword">open</a> <a id="2524" class="Keyword">import</a> <a id="2531" href="elementary-number-theory.congruence-natural-numbers.html" class="Module">elementary-number-theory.congruence-natural-numbers</a>
<a id="2583" class="Keyword">open</a> <a id="2588" class="Keyword">import</a> <a id="2595" href="elementary-number-theory.decidable-dependent-function-types.html" class="Module">elementary-number-theory.decidable-dependent-function-types</a>
<a id="2655" class="Keyword">open</a> <a id="2660" class="Keyword">import</a> <a id="2667" href="elementary-number-theory.decidable-types.html" class="Module">elementary-number-theory.decidable-types</a>
<a id="2708" class="Keyword">open</a> <a id="2713" class="Keyword">import</a> <a id="2720" href="elementary-number-theory.difference-integers.html" class="Module">elementary-number-theory.difference-integers</a>
<a id="2765" class="Keyword">open</a> <a id="2770" class="Keyword">import</a> <a id="2777" href="elementary-number-theory.dirichlet-convolution.html" class="Module">elementary-number-theory.dirichlet-convolution</a>
<a id="2824" class="Keyword">open</a> <a id="2829" class="Keyword">import</a> <a id="2836" href="elementary-number-theory.distance-integers.html" class="Module">elementary-number-theory.distance-integers</a>
<a id="2879" class="Keyword">open</a> <a id="2884" class="Keyword">import</a> <a id="2891" href="elementary-number-theory.distance-natural-numbers.html" class="Module">elementary-number-theory.distance-natural-numbers</a>
<a id="2941" class="Keyword">open</a> <a id="2946" class="Keyword">import</a> <a id="2953" href="elementary-number-theory.divisibility-integers.html" class="Module">elementary-number-theory.divisibility-integers</a>
<a id="3000" class="Keyword">open</a> <a id="3005" class="Keyword">import</a> <a id="3012" href="elementary-number-theory.divisibility-modular-arithmetic.html" class="Module">elementary-number-theory.divisibility-modular-arithmetic</a>
<a id="3069" class="Keyword">open</a> <a id="3074" class="Keyword">import</a> <a id="3081" href="elementary-number-theory.divisibility-natural-numbers.html" class="Module">elementary-number-theory.divisibility-natural-numbers</a>
<a id="3135" class="Keyword">open</a> <a id="3140" class="Keyword">import</a> <a id="3147" href="elementary-number-theory.divisibility-standard-finite-types.html" class="Module">elementary-number-theory.divisibility-standard-finite-types</a>
<a id="3207" class="Keyword">open</a> <a id="3212" class="Keyword">import</a> <a id="3219" href="elementary-number-theory.equality-integers.html" class="Module">elementary-number-theory.equality-integers</a>
<a id="3262" class="Keyword">open</a> <a id="3267" class="Keyword">import</a> <a id="3274" href="elementary-number-theory.equality-natural-numbers.html" class="Module">elementary-number-theory.equality-natural-numbers</a>
<a id="3324" class="Keyword">open</a> <a id="3329" class="Keyword">import</a> <a id="3336" href="elementary-number-theory.euclidean-division-natural-numbers.html" class="Module">elementary-number-theory.euclidean-division-natural-numbers</a>
<a id="3396" class="Keyword">open</a> <a id="3401" class="Keyword">import</a> <a id="3408" href="elementary-number-theory.eulers-totient-function.html" class="Module">elementary-number-theory.eulers-totient-function</a>
<a id="3457" class="Keyword">open</a> <a id="3462" class="Keyword">import</a> <a id="3469" href="elementary-number-theory.exponentiation-natural-numbers.html" class="Module">elementary-number-theory.exponentiation-natural-numbers</a>
<a id="3525" class="Keyword">open</a> <a id="3530" class="Keyword">import</a> <a id="3537" href="elementary-number-theory.factorials.html" class="Module">elementary-number-theory.factorials</a>
<a id="3573" class="Keyword">open</a> <a id="3578" class="Keyword">import</a> <a id="3585" href="elementary-number-theory.falling-factorials.html" class="Module">elementary-number-theory.falling-factorials</a>
<a id="3629" class="Keyword">open</a> <a id="3634" class="Keyword">import</a> <a id="3641" href="elementary-number-theory.fibonacci-sequence.html" class="Module">elementary-number-theory.fibonacci-sequence</a>
<a id="3685" class="Keyword">open</a> <a id="3690" class="Keyword">import</a> <a id="3697" href="elementary-number-theory.finitary-natural-numbers.html" class="Module">elementary-number-theory.finitary-natural-numbers</a>
<a id="3747" class="Keyword">open</a> <a id="3752" class="Keyword">import</a> <a id="3759" href="elementary-number-theory.finitely-cyclic-maps.html" class="Module">elementary-number-theory.finitely-cyclic-maps</a>
<a id="3805" class="Keyword">open</a> <a id="3810" class="Keyword">import</a> <a id="3817" href="elementary-number-theory.fractions.html" class="Module">elementary-number-theory.fractions</a>
<a id="3852" class="Keyword">open</a> <a id="3857" class="Keyword">import</a> <a id="3864" href="elementary-number-theory.goldbach-conjecture.html" class="Module">elementary-number-theory.goldbach-conjecture</a>
<a id="3909" class="Keyword">open</a> <a id="3914" class="Keyword">import</a> <a id="3921" href="elementary-number-theory.greatest-common-divisor-integers.html" class="Module">elementary-number-theory.greatest-common-divisor-integers</a>
<a id="3979" class="Keyword">open</a> <a id="3984" class="Keyword">import</a> <a id="3991" href="elementary-number-theory.greatest-common-divisor-natural-numbers.html" class="Module">elementary-number-theory.greatest-common-divisor-natural-numbers</a>
<a id="4056" class="Keyword">open</a> <a id="4061" class="Keyword">import</a> <a id="4068" href="elementary-number-theory.group-of-integers.html" class="Module">elementary-number-theory.group-of-integers</a>
<a id="4111" class="Keyword">open</a> <a id="4116" class="Keyword">import</a> <a id="4123" href="elementary-number-theory.groups-of-modular-arithmetic.html" class="Module">elementary-number-theory.groups-of-modular-arithmetic</a>
<a id="4177" class="Keyword">open</a> <a id="4182" class="Keyword">import</a> <a id="4189" href="elementary-number-theory.inequality-integers.html" class="Module">elementary-number-theory.inequality-integers</a>
<a id="4234" class="Keyword">open</a> <a id="4239" class="Keyword">import</a> <a id="4246" href="elementary-number-theory.inequality-natural-numbers.html" class="Module">elementary-number-theory.inequality-natural-numbers</a>
<a id="4298" class="Keyword">open</a> <a id="4303" class="Keyword">import</a> <a id="4310" href="elementary-number-theory.inequality-standard-finite-types.html" class="Module">elementary-number-theory.inequality-standard-finite-types</a>
<a id="4368" class="Keyword">open</a> <a id="4373" class="Keyword">import</a> <a id="4380" href="elementary-number-theory.infinitude-of-primes.html" class="Module">elementary-number-theory.infinitude-of-primes</a>
<a id="4426" class="Keyword">open</a> <a id="4431" class="Keyword">import</a> <a id="4438" href="elementary-number-theory.integers.html" class="Module">elementary-number-theory.integers</a>
<a id="4472" class="Keyword">open</a> <a id="4477" class="Keyword">import</a> <a id="4484" href="elementary-number-theory.iterating-functions.html" class="Module">elementary-number-theory.iterating-functions</a>
<a id="4529" class="Keyword">open</a> <a id="4534" class="Keyword">import</a> <a id="4541" href="elementary-number-theory.lower-bounds-natural-numbers.html" class="Module">elementary-number-theory.lower-bounds-natural-numbers</a>
<a id="4595" class="Keyword">open</a> <a id="4600" class="Keyword">import</a> <a id="4607" href="elementary-number-theory.maximum-natural-numbers.html" class="Module">elementary-number-theory.maximum-natural-numbers</a>
<a id="4656" class="Keyword">open</a> <a id="4661" class="Keyword">import</a> <a id="4668" href="elementary-number-theory.mersenne-primes.html" class="Module">elementary-number-theory.mersenne-primes</a>
<a id="4709" class="Keyword">open</a> <a id="4714" class="Keyword">import</a> <a id="4721" href="elementary-number-theory.minimum-natural-numbers.html" class="Module">elementary-number-theory.minimum-natural-numbers</a>
<a id="4770" class="Keyword">open</a> <a id="4775" class="Keyword">import</a> <a id="4782" href="elementary-number-theory.modular-arithmetic-standard-finite-types.html" class="Module">elementary-number-theory.modular-arithmetic-standard-finite-types</a>
<a id="4848" class="Keyword">open</a> <a id="4853" class="Keyword">import</a> <a id="4860" href="elementary-number-theory.modular-arithmetic.html" class="Module">elementary-number-theory.modular-arithmetic</a>
<a id="4904" class="Keyword">open</a> <a id="4909" class="Keyword">import</a> <a id="4916" href="elementary-number-theory.multiplication-integers.html" class="Module">elementary-number-theory.multiplication-integers</a>
<a id="4965" class="Keyword">open</a> <a id="4970" class="Keyword">import</a> <a id="4977" href="elementary-number-theory.multiplication-natural-numbers.html" class="Module">elementary-number-theory.multiplication-natural-numbers</a>
<a id="5033" class="Keyword">open</a> <a id="5038" class="Keyword">import</a> <a id="5045" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a>
<a id="5086" class="Keyword">open</a> <a id="5091" class="Keyword">import</a> <a id="5098" href="elementary-number-theory.nonzero-natural-numbers.html" class="Module">elementary-number-theory.nonzero-natural-numbers</a>
<a id="5147" class="Keyword">open</a> <a id="5152" class="Keyword">import</a> <a id="5159" href="elementary-number-theory.ordinal-induction-natural-numbers.html" class="Module">elementary-number-theory.ordinal-induction-natural-numbers</a>
<a id="5218" class="Keyword">open</a> <a id="5223" class="Keyword">import</a> <a id="5230" href="elementary-number-theory.prime-numbers.html" class="Module">elementary-number-theory.prime-numbers</a>
<a id="5269" class="Keyword">open</a> <a id="5274" class="Keyword">import</a> <a id="5281" href="elementary-number-theory.products-of-natural-numbers.html" class="Module">elementary-number-theory.products-of-natural-numbers</a>
<a id="5334" class="Keyword">open</a> <a id="5339" class="Keyword">import</a> <a id="5346" href="elementary-number-theory.proper-divisors-natural-numbers.html" class="Module">elementary-number-theory.proper-divisors-natural-numbers</a>
<a id="5403" class="Keyword">open</a> <a id="5408" class="Keyword">import</a> <a id="5415" href="elementary-number-theory.rational-numbers.html" class="Module">elementary-number-theory.rational-numbers</a>
<a id="5457" class="Keyword">open</a> <a id="5462" class="Keyword">import</a> <a id="5469" href="elementary-number-theory.relatively-prime-integers.html" class="Module">elementary-number-theory.relatively-prime-integers</a>
<a id="5520" class="Keyword">open</a> <a id="5525" class="Keyword">import</a> <a id="5532" href="elementary-number-theory.relatively-prime-natural-numbers.html" class="Module">elementary-number-theory.relatively-prime-natural-numbers</a>
<a id="5590" class="Keyword">open</a> <a id="5595" class="Keyword">import</a> <a id="5602" href="elementary-number-theory.repeating-element-standard-finite-type.html" class="Module">elementary-number-theory.repeating-element-standard-finite-type</a>
<a id="5666" class="Keyword">open</a> <a id="5671" class="Keyword">import</a> <a id="5678" href="elementary-number-theory.retracts-of-natural-numbers.html" class="Module">elementary-number-theory.retracts-of-natural-numbers</a>
<a id="5731" class="Keyword">open</a> <a id="5736" class="Keyword">import</a> <a id="5743" href="elementary-number-theory.square-free-natural-numbers.html" class="Module">elementary-number-theory.square-free-natural-numbers</a>
<a id="5796" class="Keyword">open</a> <a id="5801" class="Keyword">import</a> <a id="5808" href="elementary-number-theory.stirling-numbers-of-the-second-kind.html" class="Module">elementary-number-theory.stirling-numbers-of-the-second-kind</a>
<a id="5869" class="Keyword">open</a> <a id="5874" class="Keyword">import</a> <a id="5881" href="elementary-number-theory.strong-induction-natural-numbers.html" class="Module">elementary-number-theory.strong-induction-natural-numbers</a>
<a id="5939" class="Keyword">open</a> <a id="5944" class="Keyword">import</a> <a id="5951" href="elementary-number-theory.sums-of-natural-numbers.html" class="Module">elementary-number-theory.sums-of-natural-numbers</a>
<a id="6000" class="Keyword">open</a> <a id="6005" class="Keyword">import</a> <a id="6012" href="elementary-number-theory.triangular-numbers.html" class="Module">elementary-number-theory.triangular-numbers</a>
<a id="6056" class="Keyword">open</a> <a id="6061" class="Keyword">import</a> <a id="6068" href="elementary-number-theory.telephone-numbers.html" class="Module">elementary-number-theory.telephone-numbers</a>
<a id="6111" class="Keyword">open</a> <a id="6116" class="Keyword">import</a> <a id="6123" href="elementary-number-theory.twin-prime-conjecture.html" class="Module">elementary-number-theory.twin-prime-conjecture</a>
<a id="6170" class="Keyword">open</a> <a id="6175" class="Keyword">import</a> <a id="6182" href="elementary-number-theory.unit-elements-standard-finite-types.html" class="Module">elementary-number-theory.unit-elements-standard-finite-types</a>
<a id="6243" class="Keyword">open</a> <a id="6248" class="Keyword">import</a> <a id="6255" href="elementary-number-theory.unit-similarity-standard-finite-types.html" class="Module">elementary-number-theory.unit-similarity-standard-finite-types</a>
<a id="6318" class="Keyword">open</a> <a id="6323" class="Keyword">import</a> <a id="6330" href="elementary-number-theory.universal-property-natural-numbers.html" class="Module">elementary-number-theory.universal-property-natural-numbers</a>
<a id="6390" class="Keyword">open</a> <a id="6395" class="Keyword">import</a> <a id="6402" href="elementary-number-theory.upper-bounds-natural-numbers.html" class="Module">elementary-number-theory.upper-bounds-natural-numbers</a>
<a id="6456" class="Keyword">open</a> <a id="6461" class="Keyword">import</a> <a id="6468" href="elementary-number-theory.well-ordering-principle-natural-numbers.html" class="Module">elementary-number-theory.well-ordering-principle-natural-numbers</a>
<a id="6533" class="Keyword">open</a> <a id="6538" class="Keyword">import</a> <a id="6545" href="elementary-number-theory.well-ordering-principle-standard-finite-types.html" class="Module">elementary-number-theory.well-ordering-principle-standard-finite-types</a>
</pre>
## Finite group theory

<pre class="Agda"><a id="6653" class="Keyword">open</a> <a id="6658" class="Keyword">import</a> <a id="6665" href="finite-group-theory.html" class="Module">finite-group-theory</a>
<a id="6685" class="Keyword">open</a> <a id="6690" class="Keyword">import</a> <a id="6697" href="finite-group-theory.abstract-quaternion-group.html" class="Module">finite-group-theory.abstract-quaternion-group</a>
<a id="6743" class="Keyword">open</a> <a id="6748" class="Keyword">import</a> <a id="6755" href="finite-group-theory.concrete-quaternion-group.html" class="Module">finite-group-theory.concrete-quaternion-group</a>
<a id="6801" class="Keyword">open</a> <a id="6806" class="Keyword">import</a> <a id="6813" href="finite-group-theory.finite-groups.html" class="Module">finite-group-theory.finite-groups</a>
<a id="6847" class="Keyword">open</a> <a id="6852" class="Keyword">import</a> <a id="6859" href="finite-group-theory.orbits-permutations.html" class="Module">finite-group-theory.orbits-permutations</a>
<a id="6899" class="Keyword">open</a> <a id="6904" class="Keyword">import</a> <a id="6911" href="finite-group-theory.permutations.html" class="Module">finite-group-theory.permutations</a>
<a id="6944" class="Keyword">open</a> <a id="6949" class="Keyword">import</a> <a id="6956" href="finite-group-theory.sign-homomorphism.html" class="Module">finite-group-theory.sign-homomorphism</a>
<a id="6994" class="Keyword">open</a> <a id="6999" class="Keyword">import</a> <a id="7006" href="finite-group-theory.transpositions.html" class="Module">finite-group-theory.transpositions</a>
</pre>
## Foundation

<pre class="Agda"><a id="7069" class="Keyword">open</a> <a id="7074" class="Keyword">import</a> <a id="7081" href="foundation.html" class="Module">foundation</a>
<a id="7092" class="Keyword">open</a> <a id="7097" class="Keyword">import</a> <a id="7104" href="foundation.0-maps.html" class="Module">foundation.0-maps</a>
<a id="7122" class="Keyword">open</a> <a id="7127" class="Keyword">import</a> <a id="7134" href="foundation.1-types.html" class="Module">foundation.1-types</a>
<a id="7153" class="Keyword">open</a> <a id="7158" class="Keyword">import</a> <a id="7165" href="foundation.2-types.html" class="Module">foundation.2-types</a>
<a id="7184" class="Keyword">open</a> <a id="7189" class="Keyword">import</a> <a id="7196" href="foundation.algebras-polynomial-endofunctors.html" class="Module">foundation.algebras-polynomial-endofunctors</a>
<a id="7240" class="Keyword">open</a> <a id="7245" class="Keyword">import</a> <a id="7252" href="foundation.automorphisms.html" class="Module">foundation.automorphisms</a>
<a id="7277" class="Keyword">open</a> <a id="7282" class="Keyword">import</a> <a id="7289" href="foundation.axiom-of-choice.html" class="Module">foundation.axiom-of-choice</a>
<a id="7316" class="Keyword">open</a> <a id="7321" class="Keyword">import</a> <a id="7328" href="foundation.binary-embeddings.html" class="Module">foundation.binary-embeddings</a>
<a id="7357" class="Keyword">open</a> <a id="7362" class="Keyword">import</a> <a id="7369" href="foundation.binary-equivalences.html" class="Module">foundation.binary-equivalences</a>
<a id="7400" class="Keyword">open</a> <a id="7405" class="Keyword">import</a> <a id="7412" href="foundation.binary-relations.html" class="Module">foundation.binary-relations</a>
<a id="7440" class="Keyword">open</a> <a id="7445" class="Keyword">import</a> <a id="7452" href="foundation.boolean-reflection.html" class="Module">foundation.boolean-reflection</a>
<a id="7482" class="Keyword">open</a> <a id="7487" class="Keyword">import</a> <a id="7494" href="foundation.booleans.html" class="Module">foundation.booleans</a>
<a id="7514" class="Keyword">open</a> <a id="7519" class="Keyword">import</a> <a id="7526" href="foundation.cantors-diagonal-argument.html" class="Module">foundation.cantors-diagonal-argument</a>
<a id="7563" class="Keyword">open</a> <a id="7568" class="Keyword">import</a> <a id="7575" href="foundation.cartesian-product-types.html" class="Module">foundation.cartesian-product-types</a>
<a id="7610" class="Keyword">open</a> <a id="7615" class="Keyword">import</a> <a id="7622" href="foundation.choice-of-representatives-equivalence-relation.html" class="Module">foundation.choice-of-representatives-equivalence-relation</a>
<a id="7680" class="Keyword">open</a> <a id="7685" class="Keyword">import</a> <a id="7692" href="foundation.coherently-invertible-maps.html" class="Module">foundation.coherently-invertible-maps</a>
<a id="7730" class="Keyword">open</a> <a id="7735" class="Keyword">import</a> <a id="7742" href="foundation.commuting-squares.html" class="Module">foundation.commuting-squares</a>
<a id="7771" class="Keyword">open</a> <a id="7776" class="Keyword">import</a> <a id="7783" href="foundation.complements.html" class="Module">foundation.complements</a>
<a id="7806" class="Keyword">open</a> <a id="7811" class="Keyword">import</a> <a id="7818" href="foundation.conjunction.html" class="Module">foundation.conjunction</a>
<a id="7841" class="Keyword">open</a> <a id="7846" class="Keyword">import</a> <a id="7853" href="foundation.connected-components-universes.html" class="Module">foundation.connected-components-universes</a>
<a id="7895" class="Keyword">open</a> <a id="7900" class="Keyword">import</a> <a id="7907" href="foundation.connected-components.html" class="Module">foundation.connected-components</a>
<a id="7939" class="Keyword">open</a> <a id="7944" class="Keyword">import</a> <a id="7951" href="foundation.connected-types.html" class="Module">foundation.connected-types</a>
<a id="7978" class="Keyword">open</a> <a id="7983" class="Keyword">import</a> <a id="7990" href="foundation.constant-maps.html" class="Module">foundation.constant-maps</a>
<a id="8015" class="Keyword">open</a> <a id="8020" class="Keyword">import</a> <a id="8027" href="foundation.contractible-maps.html" class="Module">foundation.contractible-maps</a>
<a id="8056" class="Keyword">open</a> <a id="8061" class="Keyword">import</a> <a id="8068" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a>
<a id="8098" class="Keyword">open</a> <a id="8103" class="Keyword">import</a> <a id="8110" href="foundation.coproduct-types.html" class="Module">foundation.coproduct-types</a>
<a id="8137" class="Keyword">open</a> <a id="8142" class="Keyword">import</a> <a id="8149" href="foundation.coslice.html" class="Module">foundation.coslice</a>
<a id="8168" class="Keyword">open</a> <a id="8173" class="Keyword">import</a> <a id="8180" href="foundation.decidable-dependent-function-types.html" class="Module">foundation.decidable-dependent-function-types</a>
<a id="8226" class="Keyword">open</a> <a id="8231" class="Keyword">import</a> <a id="8238" href="foundation.decidable-dependent-pair-types.html" class="Module">foundation.decidable-dependent-pair-types</a>
<a id="8280" class="Keyword">open</a> <a id="8285" class="Keyword">import</a> <a id="8292" href="foundation.decidable-embeddings.html" class="Module">foundation.decidable-embeddings</a>
<a id="8324" class="Keyword">open</a> <a id="8329" class="Keyword">import</a> <a id="8336" href="foundation.decidable-equality.html" class="Module">foundation.decidable-equality</a>
<a id="8366" class="Keyword">open</a> <a id="8371" class="Keyword">import</a> <a id="8378" href="foundation.decidable-maps.html" class="Module">foundation.decidable-maps</a>
<a id="8404" class="Keyword">open</a> <a id="8409" class="Keyword">import</a> <a id="8416" href="foundation.decidable-propositions.html" class="Module">foundation.decidable-propositions</a>
<a id="8450" class="Keyword">open</a> <a id="8455" class="Keyword">import</a> <a id="8462" href="foundation.decidable-subtypes.html" class="Module">foundation.decidable-subtypes</a>
<a id="8492" class="Keyword">open</a> <a id="8497" class="Keyword">import</a> <a id="8504" href="foundation.decidable-types.html" class="Module">foundation.decidable-types</a>
<a id="8531" class="Keyword">open</a> <a id="8536" class="Keyword">import</a> <a id="8543" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a>
<a id="8575" class="Keyword">open</a> <a id="8580" class="Keyword">import</a> <a id="8587" href="foundation.diagonal-maps-of-types.html" class="Module">foundation.diagonal-maps-of-types</a>
<a id="8621" class="Keyword">open</a> <a id="8626" class="Keyword">import</a> <a id="8633" href="foundation.disjunction.html" class="Module">foundation.disjunction</a>
<a id="8656" class="Keyword">open</a> <a id="8661" class="Keyword">import</a> <a id="8668" href="foundation.distributivity-of-dependent-functions-over-coproduct-types.html" class="Module">foundation.distributivity-of-dependent-functions-over-coproduct-types</a>
<a id="8738" class="Keyword">open</a> <a id="8743" class="Keyword">import</a> <a id="8750" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html" class="Module">foundation.distributivity-of-dependent-functions-over-dependent-pairs</a>
<a id="8820" class="Keyword">open</a> <a id="8825" class="Keyword">import</a> <a id="8832" href="foundation.double-negation.html" class="Module">foundation.double-negation</a>
<a id="8859" class="Keyword">open</a> <a id="8864" class="Keyword">import</a> <a id="8871" href="foundation.effective-maps-equivalence-relations.html" class="Module">foundation.effective-maps-equivalence-relations</a>
<a id="8919" class="Keyword">open</a> <a id="8924" class="Keyword">import</a> <a id="8931" href="foundation.elementhood-relation-w-types.html" class="Module">foundation.elementhood-relation-w-types</a>
<a id="8971" class="Keyword">open</a> <a id="8976" class="Keyword">import</a> <a id="8983" href="foundation.embeddings.html" class="Module">foundation.embeddings</a>
<a id="9005" class="Keyword">open</a> <a id="9010" class="Keyword">import</a> <a id="9017" href="foundation.empty-types.html" class="Module">foundation.empty-types</a>
<a id="9040" class="Keyword">open</a> <a id="9045" class="Keyword">import</a> <a id="9052" href="foundation.epimorphisms-with-respect-to-sets.html" class="Module">foundation.epimorphisms-with-respect-to-sets</a>
<a id="9097" class="Keyword">open</a> <a id="9102" class="Keyword">import</a> <a id="9109" href="foundation.equality-cartesian-product-types.html" class="Module">foundation.equality-cartesian-product-types</a>
<a id="9153" class="Keyword">open</a> <a id="9158" class="Keyword">import</a> <a id="9165" href="foundation.equality-coproduct-types.html" class="Module">foundation.equality-coproduct-types</a>
<a id="9201" class="Keyword">open</a> <a id="9206" class="Keyword">import</a> <a id="9213" href="foundation.equality-dependent-function-types.html" class="Module">foundation.equality-dependent-function-types</a>
<a id="9258" class="Keyword">open</a> <a id="9263" class="Keyword">import</a> <a id="9270" href="foundation.equality-dependent-pair-types.html" class="Module">foundation.equality-dependent-pair-types</a>
<a id="9311" class="Keyword">open</a> <a id="9316" class="Keyword">import</a> <a id="9323" href="foundation.equality-fibers-of-maps.html" class="Module">foundation.equality-fibers-of-maps</a>
<a id="9358" class="Keyword">open</a> <a id="9363" class="Keyword">import</a> <a id="9370" href="foundation.equivalence-classes.html" class="Module">foundation.equivalence-classes</a>
<a id="9401" class="Keyword">open</a> <a id="9406" class="Keyword">import</a> <a id="9413" href="foundation.equivalence-induction.html" class="Module">foundation.equivalence-induction</a>
<a id="9446" class="Keyword">open</a> <a id="9451" class="Keyword">import</a> <a id="9458" href="foundation.equivalence-relations.html" class="Module">foundation.equivalence-relations</a>
<a id="9491" class="Keyword">open</a> <a id="9496" class="Keyword">import</a> <a id="9503" href="foundation.equivalences-maybe.html" class="Module">foundation.equivalences-maybe</a>
<a id="9533" class="Keyword">open</a> <a id="9538" class="Keyword">import</a> <a id="9545" href="foundation.equivalences.html" class="Module">foundation.equivalences</a>
<a id="9569" class="Keyword">open</a> <a id="9574" class="Keyword">import</a> <a id="9581" href="foundation.existential-quantification.html" class="Module">foundation.existential-quantification</a>
<a id="9619" class="Keyword">open</a> <a id="9624" class="Keyword">import</a> <a id="9631" href="foundation.extensional-w-types.html" class="Module">foundation.extensional-w-types</a>
<a id="9662" class="Keyword">open</a> <a id="9667" class="Keyword">import</a> <a id="9674" href="foundation.faithful-maps.html" class="Module">foundation.faithful-maps</a>
<a id="9699" class="Keyword">open</a> <a id="9704" class="Keyword">import</a> <a id="9711" href="foundation.fiber-inclusions.html" class="Module">foundation.fiber-inclusions</a>
<a id="9739" class="Keyword">open</a> <a id="9744" class="Keyword">import</a> <a id="9751" href="foundation.fibered-maps.html" class="Module">foundation.fibered-maps</a>
<a id="9775" class="Keyword">open</a> <a id="9780" class="Keyword">import</a> <a id="9787" href="foundation.fibers-of-maps.html" class="Module">foundation.fibers-of-maps</a>
<a id="9813" class="Keyword">open</a> <a id="9818" class="Keyword">import</a> <a id="9825" href="foundation.function-extensionality.html" class="Module">foundation.function-extensionality</a>
<a id="9860" class="Keyword">open</a> <a id="9865" class="Keyword">import</a> <a id="9872" href="foundation.functions.html" class="Module">foundation.functions</a>
<a id="9893" class="Keyword">open</a> <a id="9898" class="Keyword">import</a> <a id="9905" href="foundation.functoriality-cartesian-product-types.html" class="Module">foundation.functoriality-cartesian-product-types</a>
<a id="9954" class="Keyword">open</a> <a id="9959" class="Keyword">import</a> <a id="9966" href="foundation.functoriality-coproduct-types.html" class="Module">foundation.functoriality-coproduct-types</a>
<a id="10007" class="Keyword">open</a> <a id="10012" class="Keyword">import</a> <a id="10019" href="foundation.functoriality-dependent-function-types.html" class="Module">foundation.functoriality-dependent-function-types</a>
<a id="10069" class="Keyword">open</a> <a id="10074" class="Keyword">import</a> <a id="10081" href="foundation.functoriality-dependent-pair-types.html" class="Module">foundation.functoriality-dependent-pair-types</a>
<a id="10127" class="Keyword">open</a> <a id="10132" class="Keyword">import</a> <a id="10139" href="foundation.functoriality-function-types.html" class="Module">foundation.functoriality-function-types</a>
<a id="10179" class="Keyword">open</a> <a id="10184" class="Keyword">import</a> <a id="10191" href="foundation.functoriality-propositional-truncation.html" class="Module">foundation.functoriality-propositional-truncation</a>
<a id="10241" class="Keyword">open</a> <a id="10246" class="Keyword">import</a> <a id="10253" href="foundation.functoriality-set-quotients.html" class="Module">foundation.functoriality-set-quotients</a>
<a id="10292" class="Keyword">open</a> <a id="10297" class="Keyword">import</a> <a id="10304" href="foundation.functoriality-set-truncation.html" class="Module">foundation.functoriality-set-truncation</a>
<a id="10344" class="Keyword">open</a> <a id="10349" class="Keyword">import</a> <a id="10356" href="foundation.functoriality-w-types.html" class="Module">foundation.functoriality-w-types</a>
<a id="10389" class="Keyword">open</a> <a id="10394" class="Keyword">import</a> <a id="10401" href="foundation.fundamental-theorem-of-identity-types.html" class="Module">foundation.fundamental-theorem-of-identity-types</a>
<a id="10450" class="Keyword">open</a> <a id="10455" class="Keyword">import</a> <a id="10462" href="foundation.global-choice.html" class="Module">foundation.global-choice</a>
<a id="10487" class="Keyword">open</a> <a id="10492" class="Keyword">import</a> <a id="10499" href="foundation.homotopies.html" class="Module">foundation.homotopies</a>
<a id="10521" class="Keyword">open</a> <a id="10526" class="Keyword">import</a> <a id="10533" href="foundation.identity-systems.html" class="Module">foundation.identity-systems</a>
<a id="10561" class="Keyword">open</a> <a id="10566" class="Keyword">import</a> <a id="10573" href="foundation.identity-types.html" class="Module">foundation.identity-types</a>
<a id="10599" class="Keyword">open</a> <a id="10604" class="Keyword">import</a> <a id="10611" href="foundation.images.html" class="Module">foundation.images</a>
<a id="10629" class="Keyword">open</a> <a id="10634" class="Keyword">import</a> <a id="10641" href="foundation.impredicative-encodings.html" class="Module">foundation.impredicative-encodings</a>
<a id="10676" class="Keyword">open</a> <a id="10681" class="Keyword">import</a> <a id="10688" href="foundation.indexed-w-types.html" class="Module">foundation.indexed-w-types</a>
<a id="10715" class="Keyword">open</a> <a id="10720" class="Keyword">import</a> <a id="10727" href="foundation.induction-principle-propositional-truncation.html" class="Module">foundation.induction-principle-propositional-truncation</a>
<a id="10783" class="Keyword">open</a> <a id="10788" class="Keyword">import</a> <a id="10795" href="foundation.induction-w-types.html" class="Module">foundation.induction-w-types</a>
<a id="10824" class="Keyword">open</a> <a id="10829" class="Keyword">import</a> <a id="10836" href="foundation.inequality-w-types.html" class="Module">foundation.inequality-w-types</a>
<a id="10866" class="Keyword">open</a> <a id="10871" class="Keyword">import</a> <a id="10878" href="foundation.injective-maps.html" class="Module">foundation.injective-maps</a>
<a id="10904" class="Keyword">open</a> <a id="10909" class="Keyword">import</a> <a id="10916" href="foundation.interchange-law.html" class="Module">foundation.interchange-law</a>
<a id="10943" class="Keyword">open</a> <a id="10948" class="Keyword">import</a> <a id="10955" href="foundation.involutions.html" class="Module">foundation.involutions</a>
<a id="10978" class="Keyword">open</a> <a id="10983" class="Keyword">import</a> <a id="10990" href="foundation.isolated-points.html" class="Module">foundation.isolated-points</a>
<a id="11017" class="Keyword">open</a> <a id="11022" class="Keyword">import</a> <a id="11029" href="foundation.isomorphisms-of-sets.html" class="Module">foundation.isomorphisms-of-sets</a>
<a id="11061" class="Keyword">open</a> <a id="11066" class="Keyword">import</a> <a id="11073" href="foundation.law-of-excluded-middle.html" class="Module">foundation.law-of-excluded-middle</a>
<a id="11107" class="Keyword">open</a> <a id="11112" class="Keyword">import</a> <a id="11119" href="foundation.lawveres-fixed-point-theorem.html" class="Module">foundation.lawveres-fixed-point-theorem</a>
<a id="11159" class="Keyword">open</a> <a id="11164" class="Keyword">import</a> <a id="11171" href="foundation.locally-small-types.html" class="Module">foundation.locally-small-types</a>
<a id="11202" class="Keyword">open</a> <a id="11207" class="Keyword">import</a> <a id="11214" href="foundation.logical-equivalences.html" class="Module">foundation.logical-equivalences</a>
<a id="11246" class="Keyword">open</a> <a id="11251" class="Keyword">import</a> <a id="11258" href="foundation.lower-types-w-types.html" class="Module">foundation.lower-types-w-types</a>
<a id="11289" class="Keyword">open</a> <a id="11294" class="Keyword">import</a> <a id="11301" href="foundation.maybe.html" class="Module">foundation.maybe</a>
<a id="11318" class="Keyword">open</a> <a id="11323" class="Keyword">import</a> <a id="11330" href="foundation.mere-equality.html" class="Module">foundation.mere-equality</a>
<a id="11355" class="Keyword">open</a> <a id="11360" class="Keyword">import</a> <a id="11367" href="foundation.mere-equivalences.html" class="Module">foundation.mere-equivalences</a>
<a id="11396" class="Keyword">open</a> <a id="11401" class="Keyword">import</a> <a id="11408" href="foundation.monomorphisms.html" class="Module">foundation.monomorphisms</a>
<a id="11433" class="Keyword">open</a> <a id="11438" class="Keyword">import</a> <a id="11445" href="foundation.multisets.html" class="Module">foundation.multisets</a>
<a id="11466" class="Keyword">open</a> <a id="11471" class="Keyword">import</a> <a id="11478" href="foundation.negation.html" class="Module">foundation.negation</a>
<a id="11498" class="Keyword">open</a> <a id="11503" class="Keyword">import</a> <a id="11510" href="foundation.non-contractible-types.html" class="Module">foundation.non-contractible-types</a>
<a id="11544" class="Keyword">open</a> <a id="11549" class="Keyword">import</a> <a id="11556" href="foundation.path-algebra.html" class="Module">foundation.path-algebra</a>
<a id="11580" class="Keyword">open</a> <a id="11585" class="Keyword">import</a> <a id="11592" href="foundation.path-split-maps.html" class="Module">foundation.path-split-maps</a>
<a id="11619" class="Keyword">open</a> <a id="11624" class="Keyword">import</a> <a id="11631" href="foundation.polynomial-endofunctors.html" class="Module">foundation.polynomial-endofunctors</a>
<a id="11666" class="Keyword">open</a> <a id="11671" class="Keyword">import</a> <a id="11678" href="foundation.propositional-extensionality.html" class="Module">foundation.propositional-extensionality</a>
<a id="11718" class="Keyword">open</a> <a id="11723" class="Keyword">import</a> <a id="11730" href="foundation.propositional-maps.html" class="Module">foundation.propositional-maps</a>
<a id="11760" class="Keyword">open</a> <a id="11765" class="Keyword">import</a> <a id="11772" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a>
<a id="11809" class="Keyword">open</a> <a id="11814" class="Keyword">import</a> <a id="11821" href="foundation.propositions.html" class="Module">foundation.propositions</a>
<a id="11845" class="Keyword">open</a> <a id="11850" class="Keyword">import</a> <a id="11857" href="foundation.pullbacks.html" class="Module">foundation.pullbacks</a>
<a id="11878" class="Keyword">open</a> <a id="11883" class="Keyword">import</a> <a id="11890" href="foundation.raising-universe-levels.html" class="Module">foundation.raising-universe-levels</a>
<a id="11925" class="Keyword">open</a> <a id="11930" class="Keyword">import</a> <a id="11937" href="foundation.ranks-of-elements-w-types.html" class="Module">foundation.ranks-of-elements-w-types</a>
<a id="11974" class="Keyword">open</a> <a id="11979" class="Keyword">import</a> <a id="11986" href="foundation.reflecting-maps-equivalence-relations.html" class="Module">foundation.reflecting-maps-equivalence-relations</a>
<a id="12035" class="Keyword">open</a> <a id="12040" class="Keyword">import</a> <a id="12047" href="foundation.replacement.html" class="Module">foundation.replacement</a>
<a id="12070" class="Keyword">open</a> <a id="12075" class="Keyword">import</a> <a id="12082" href="foundation.retractions.html" class="Module">foundation.retractions</a>
<a id="12105" class="Keyword">open</a> <a id="12110" class="Keyword">import</a> <a id="12117" href="foundation.russells-paradox.html" class="Module">foundation.russells-paradox</a>
<a id="12145" class="Keyword">open</a> <a id="12150" class="Keyword">import</a> <a id="12157" href="foundation.sections.html" class="Module">foundation.sections</a>
<a id="12177" class="Keyword">open</a> <a id="12182" class="Keyword">import</a> <a id="12189" href="foundation.set-presented-types.html" class="Module">foundation.set-presented-types</a>
<a id="12220" class="Keyword">open</a> <a id="12225" class="Keyword">import</a> <a id="12232" href="foundation.set-truncations.html" class="Module">foundation.set-truncations</a>
<a id="12259" class="Keyword">open</a> <a id="12264" class="Keyword">import</a> <a id="12271" href="foundation.sets.html" class="Module">foundation.sets</a>
<a id="12287" class="Keyword">open</a> <a id="12292" class="Keyword">import</a> <a id="12299" href="foundation.singleton-induction.html" class="Module">foundation.singleton-induction</a>
<a id="12330" class="Keyword">open</a> <a id="12335" class="Keyword">import</a> <a id="12342" href="foundation.slice.html" class="Module">foundation.slice</a>
<a id="12359" class="Keyword">open</a> <a id="12364" class="Keyword">import</a> <a id="12371" href="foundation.small-maps.html" class="Module">foundation.small-maps</a>
<a id="12393" class="Keyword">open</a> <a id="12398" class="Keyword">import</a> <a id="12405" href="foundation.small-multisets.html" class="Module">foundation.small-multisets</a>
<a id="12432" class="Keyword">open</a> <a id="12437" class="Keyword">import</a> <a id="12444" href="foundation.small-types.html" class="Module">foundation.small-types</a>
<a id="12467" class="Keyword">open</a> <a id="12472" class="Keyword">import</a> <a id="12479" href="foundation.small-universes.html" class="Module">foundation.small-universes</a>
<a id="12506" class="Keyword">open</a> <a id="12511" class="Keyword">import</a> <a id="12518" href="foundation.split-surjective-maps.html" class="Module">foundation.split-surjective-maps</a>
<a id="12551" class="Keyword">open</a> <a id="12556" class="Keyword">import</a> <a id="12563" href="foundation.structure-identity-principle.html" class="Module">foundation.structure-identity-principle</a>
<a id="12603" class="Keyword">open</a> <a id="12608" class="Keyword">import</a> <a id="12615" href="foundation.structure.html" class="Module">foundation.structure</a>
<a id="12636" class="Keyword">open</a> <a id="12641" class="Keyword">import</a> <a id="12648" href="foundation.subterminal-types.html" class="Module">foundation.subterminal-types</a>
<a id="12677" class="Keyword">open</a> <a id="12682" class="Keyword">import</a> <a id="12689" href="foundation.subtype-identity-principle.html" class="Module">foundation.subtype-identity-principle</a>
<a id="12727" class="Keyword">open</a> <a id="12732" class="Keyword">import</a> <a id="12739" href="foundation.subtypes.html" class="Module">foundation.subtypes</a>
<a id="12759" class="Keyword">open</a> <a id="12764" class="Keyword">import</a> <a id="12771" href="foundation.subuniverses.html" class="Module">foundation.subuniverses</a>
<a id="12795" class="Keyword">open</a> <a id="12800" class="Keyword">import</a> <a id="12807" href="foundation.surjective-maps.html" class="Module">foundation.surjective-maps</a>
<a id="12834" class="Keyword">open</a> <a id="12839" class="Keyword">import</a> <a id="12846" href="foundation.truncated-equality.html" class="Module">foundation.truncated-equality</a>
<a id="12876" class="Keyword">open</a> <a id="12881" class="Keyword">import</a> <a id="12888" href="foundation.truncated-maps.html" class="Module">foundation.truncated-maps</a>
<a id="12914" class="Keyword">open</a> <a id="12919" class="Keyword">import</a> <a id="12926" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a>
<a id="12953" class="Keyword">open</a> <a id="12958" class="Keyword">import</a> <a id="12965" href="foundation.truncation-levels.html" class="Module">foundation.truncation-levels</a>
<a id="12994" class="Keyword">open</a> <a id="12999" class="Keyword">import</a> <a id="13006" href="foundation.truncations.html" class="Module">foundation.truncations</a>
<a id="13029" class="Keyword">open</a> <a id="13034" class="Keyword">import</a> <a id="13041" href="foundation.type-arithmetic-cartesian-product-types.html" class="Module">foundation.type-arithmetic-cartesian-product-types</a>
<a id="13092" class="Keyword">open</a> <a id="13097" class="Keyword">import</a> <a id="13104" href="foundation.type-arithmetic-coproduct-types.html" class="Module">foundation.type-arithmetic-coproduct-types</a>
<a id="13147" class="Keyword">open</a> <a id="13152" class="Keyword">import</a> <a id="13159" href="foundation.type-arithmetic-dependent-pair-types.html" class="Module">foundation.type-arithmetic-dependent-pair-types</a>
<a id="13207" class="Keyword">open</a> <a id="13212" class="Keyword">import</a> <a id="13219" href="foundation.type-arithmetic-empty-type.html" class="Module">foundation.type-arithmetic-empty-type</a>
<a id="13257" class="Keyword">open</a> <a id="13262" class="Keyword">import</a> <a id="13269" href="foundation.type-arithmetic-unit-type.html" class="Module">foundation.type-arithmetic-unit-type</a>
<a id="13306" class="Keyword">open</a> <a id="13311" class="Keyword">import</a> <a id="13318" href="foundation.uniqueness-image.html" class="Module">foundation.uniqueness-image</a>
<a id="13346" class="Keyword">open</a> <a id="13351" class="Keyword">import</a> <a id="13358" href="foundation.uniqueness-set-quotients.html" class="Module">foundation.uniqueness-set-quotients</a>
<a id="13394" class="Keyword">open</a> <a id="13399" class="Keyword">import</a> <a id="13406" href="foundation.uniqueness-set-truncations.html" class="Module">foundation.uniqueness-set-truncations</a>
<a id="13444" class="Keyword">open</a> <a id="13449" class="Keyword">import</a> <a id="13456" href="foundation.uniqueness-truncation.html" class="Module">foundation.uniqueness-truncation</a>
<a id="13489" class="Keyword">open</a> <a id="13494" class="Keyword">import</a> <a id="13501" href="foundation.unit-type.html" class="Module">foundation.unit-type</a>
<a id="13522" class="Keyword">open</a> <a id="13527" class="Keyword">import</a> <a id="13534" href="foundation.univalence-implies-function-extensionality.html" class="Module">foundation.univalence-implies-function-extensionality</a>
<a id="13588" class="Keyword">open</a> <a id="13593" class="Keyword">import</a> <a id="13600" href="foundation.univalence.html" class="Module">foundation.univalence</a>
<a id="13622" class="Keyword">open</a> <a id="13627" class="Keyword">import</a> <a id="13634" href="foundation.univalent-type-families.html" class="Module">foundation.univalent-type-families</a>
<a id="13669" class="Keyword">open</a> <a id="13674" class="Keyword">import</a> <a id="13681" href="foundation.universal-multiset.html" class="Module">foundation.universal-multiset</a>
<a id="13711" class="Keyword">open</a> <a id="13716" class="Keyword">import</a> <a id="13723" href="foundation.universal-property-booleans.html" class="Module">foundation.universal-property-booleans</a>
<a id="13762" class="Keyword">open</a> <a id="13767" class="Keyword">import</a> <a id="13774" href="foundation.universal-property-cartesian-product-types.html" class="Module">foundation.universal-property-cartesian-product-types</a>
<a id="13828" class="Keyword">open</a> <a id="13833" class="Keyword">import</a> <a id="13840" href="foundation.universal-property-coproduct-types.html" class="Module">foundation.universal-property-coproduct-types</a>
<a id="13886" class="Keyword">open</a> <a id="13891" class="Keyword">import</a> <a id="13898" href="foundation.universal-property-dependent-pair-types.html" class="Module">foundation.universal-property-dependent-pair-types</a>
<a id="13949" class="Keyword">open</a> <a id="13954" class="Keyword">import</a> <a id="13961" href="foundation.universal-property-empty-type.html" class="Module">foundation.universal-property-empty-type</a>
<a id="14002" class="Keyword">open</a> <a id="14007" class="Keyword">import</a> <a id="14014" href="foundation.universal-property-fiber-products.html" class="Module">foundation.universal-property-fiber-products</a>
<a id="14059" class="Keyword">open</a> <a id="14064" class="Keyword">import</a> <a id="14071" href="foundation.universal-property-identity-types.html" class="Module">foundation.universal-property-identity-types</a>
<a id="14116" class="Keyword">open</a> <a id="14121" class="Keyword">import</a> <a id="14128" href="foundation.universal-property-image.html" class="Module">foundation.universal-property-image</a>
<a id="14164" class="Keyword">open</a> <a id="14169" class="Keyword">import</a> <a id="14176" href="foundation.universal-property-maybe.html" class="Module">foundation.universal-property-maybe</a>
<a id="14212" class="Keyword">open</a> <a id="14217" class="Keyword">import</a> <a id="14224" href="foundation.universal-property-propositional-truncation-into-sets.html" class="Module">foundation.universal-property-propositional-truncation-into-sets</a>
<a id="14289" class="Keyword">open</a> <a id="14294" class="Keyword">import</a> <a id="14301" href="foundation.universal-property-propositional-truncation.html" class="Module">foundation.universal-property-propositional-truncation</a>
<a id="14356" class="Keyword">open</a> <a id="14361" class="Keyword">import</a> <a id="14368" href="foundation.universal-property-pullbacks.html" class="Module">foundation.universal-property-pullbacks</a>
<a id="14408" class="Keyword">open</a> <a id="14413" class="Keyword">import</a> <a id="14420" href="foundation.universal-property-set-quotients.html" class="Module">foundation.universal-property-set-quotients</a>
<a id="14464" class="Keyword">open</a> <a id="14469" class="Keyword">import</a> <a id="14476" href="foundation.universal-property-set-truncation.html" class="Module">foundation.universal-property-set-truncation</a>
<a id="14521" class="Keyword">open</a> <a id="14526" class="Keyword">import</a> <a id="14533" href="foundation.universal-property-truncation.html" class="Module">foundation.universal-property-truncation</a>
<a id="14574" class="Keyword">open</a> <a id="14579" class="Keyword">import</a> <a id="14586" href="foundation.universal-property-unit-type.html" class="Module">foundation.universal-property-unit-type</a>
<a id="14626" class="Keyword">open</a> <a id="14631" class="Keyword">import</a> <a id="14638" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a>
<a id="14665" class="Keyword">open</a> <a id="14670" class="Keyword">import</a> <a id="14677" href="foundation.unordered-pairs.html" class="Module">foundation.unordered-pairs</a>
<a id="14704" class="Keyword">open</a> <a id="14709" class="Keyword">import</a> <a id="14716" href="foundation.w-types.html" class="Module">foundation.w-types</a>
<a id="14735" class="Keyword">open</a> <a id="14740" class="Keyword">import</a> <a id="14747" href="foundation.weak-function-extensionality.html" class="Module">foundation.weak-function-extensionality</a>
<a id="14787" class="Keyword">open</a> <a id="14792" class="Keyword">import</a> <a id="14799" href="foundation.weakly-constant-maps.html" class="Module">foundation.weakly-constant-maps</a>
</pre>
## Foundation Core

<pre class="Agda"><a id="14864" class="Keyword">open</a> <a id="14869" class="Keyword">import</a> <a id="14876" href="foundation-core.0-maps.html" class="Module">foundation-core.0-maps</a>
<a id="14899" class="Keyword">open</a> <a id="14904" class="Keyword">import</a> <a id="14911" href="foundation-core.1-types.html" class="Module">foundation-core.1-types</a>
<a id="14935" class="Keyword">open</a> <a id="14940" class="Keyword">import</a> <a id="14947" href="foundation-core.cartesian-product-types.html" class="Module">foundation-core.cartesian-product-types</a>
<a id="14987" class="Keyword">open</a> <a id="14992" class="Keyword">import</a> <a id="14999" href="foundation-core.coherently-invertible-maps.html" class="Module">foundation-core.coherently-invertible-maps</a>
<a id="15042" class="Keyword">open</a> <a id="15047" class="Keyword">import</a> <a id="15054" href="foundation-core.commuting-squares.html" class="Module">foundation-core.commuting-squares</a>
<a id="15088" class="Keyword">open</a> <a id="15093" class="Keyword">import</a> <a id="15100" href="foundation-core.constant-maps.html" class="Module">foundation-core.constant-maps</a>
<a id="15130" class="Keyword">open</a> <a id="15135" class="Keyword">import</a> <a id="15142" href="foundation-core.contractible-maps.html" class="Module">foundation-core.contractible-maps</a>
<a id="15176" class="Keyword">open</a> <a id="15181" class="Keyword">import</a> <a id="15188" href="foundation-core.contractible-types.html" class="Module">foundation-core.contractible-types</a>
<a id="15223" class="Keyword">open</a> <a id="15228" class="Keyword">import</a> <a id="15235" href="foundation-core.dependent-pair-types.html" class="Module">foundation-core.dependent-pair-types</a>
<a id="15272" class="Keyword">open</a> <a id="15277" class="Keyword">import</a> <a id="15284" href="foundation-core.embeddings.html" class="Module">foundation-core.embeddings</a>
<a id="15311" class="Keyword">open</a> <a id="15316" class="Keyword">import</a> <a id="15323" href="foundation-core.empty-types.html" class="Module">foundation-core.empty-types</a>
<a id="15351" class="Keyword">open</a> <a id="15356" class="Keyword">import</a> <a id="15363" href="foundation-core.equality-cartesian-product-types.html" class="Module">foundation-core.equality-cartesian-product-types</a>
<a id="15412" class="Keyword">open</a> <a id="15417" class="Keyword">import</a> <a id="15424" href="foundation-core.equality-dependent-pair-types.html" class="Module">foundation-core.equality-dependent-pair-types</a>
<a id="15470" class="Keyword">open</a> <a id="15475" class="Keyword">import</a> <a id="15482" href="foundation-core.equality-fibers-of-maps.html" class="Module">foundation-core.equality-fibers-of-maps</a>
<a id="15522" class="Keyword">open</a> <a id="15527" class="Keyword">import</a> <a id="15534" href="foundation-core.equivalence-induction.html" class="Module">foundation-core.equivalence-induction</a>
<a id="15572" class="Keyword">open</a> <a id="15577" class="Keyword">import</a> <a id="15584" href="foundation-core.equivalences.html" class="Module">foundation-core.equivalences</a>
<a id="15613" class="Keyword">open</a> <a id="15618" class="Keyword">import</a> <a id="15625" href="foundation-core.faithful-maps.html" class="Module">foundation-core.faithful-maps</a>
<a id="15655" class="Keyword">open</a> <a id="15660" class="Keyword">import</a> <a id="15667" href="foundation-core.fibers-of-maps.html" class="Module">foundation-core.fibers-of-maps</a>
<a id="15698" class="Keyword">open</a> <a id="15703" class="Keyword">import</a> <a id="15710" href="foundation-core.functions.html" class="Module">foundation-core.functions</a>
<a id="15736" class="Keyword">open</a> <a id="15741" class="Keyword">import</a> <a id="15748" href="foundation-core.functoriality-dependent-pair-types.html" class="Module">foundation-core.functoriality-dependent-pair-types</a>
<a id="15799" class="Keyword">open</a> <a id="15804" class="Keyword">import</a> <a id="15811" href="foundation-core.fundamental-theorem-of-identity-types.html" class="Module">foundation-core.fundamental-theorem-of-identity-types</a>
<a id="15865" class="Keyword">open</a> <a id="15870" class="Keyword">import</a> <a id="15877" href="foundation-core.homotopies.html" class="Module">foundation-core.homotopies</a>
<a id="15904" class="Keyword">open</a> <a id="15909" class="Keyword">import</a> <a id="15916" href="foundation-core.identity-systems.html" class="Module">foundation-core.identity-systems</a>
<a id="15949" class="Keyword">open</a> <a id="15954" class="Keyword">import</a> <a id="15961" href="foundation-core.identity-types.html" class="Module">foundation-core.identity-types</a>
<a id="15992" class="Keyword">open</a> <a id="15997" class="Keyword">import</a> <a id="16004" href="foundation-core.logical-equivalences.html" class="Module">foundation-core.logical-equivalences</a>
<a id="16041" class="Keyword">open</a> <a id="16046" class="Keyword">import</a> <a id="16053" href="foundation-core.negation.html" class="Module">foundation-core.negation</a>
<a id="16078" class="Keyword">open</a> <a id="16083" class="Keyword">import</a> <a id="16090" href="foundation-core.path-split-maps.html" class="Module">foundation-core.path-split-maps</a>
<a id="16122" class="Keyword">open</a> <a id="16127" class="Keyword">import</a> <a id="16134" href="foundation-core.propositional-maps.html" class="Module">foundation-core.propositional-maps</a>
<a id="16169" class="Keyword">open</a> <a id="16174" class="Keyword">import</a> <a id="16181" href="foundation-core.propositions.html" class="Module">foundation-core.propositions</a>
<a id="16210" class="Keyword">open</a> <a id="16215" class="Keyword">import</a> <a id="16222" href="foundation-core.retractions.html" class="Module">foundation-core.retractions</a>
<a id="16250" class="Keyword">open</a> <a id="16255" class="Keyword">import</a> <a id="16262" href="foundation-core.sections.html" class="Module">foundation-core.sections</a>
<a id="16287" class="Keyword">open</a> <a id="16292" class="Keyword">import</a> <a id="16299" href="foundation-core.sets.html" class="Module">foundation-core.sets</a>
<a id="16320" class="Keyword">open</a> <a id="16325" class="Keyword">import</a> <a id="16332" href="foundation-core.singleton-induction.html" class="Module">foundation-core.singleton-induction</a>
<a id="16368" class="Keyword">open</a> <a id="16373" class="Keyword">import</a> <a id="16380" href="foundation-core.subtype-identity-principle.html" class="Module">foundation-core.subtype-identity-principle</a>
<a id="16423" class="Keyword">open</a> <a id="16428" class="Keyword">import</a> <a id="16435" href="foundation-core.subtypes.html" class="Module">foundation-core.subtypes</a>
<a id="16460" class="Keyword">open</a> <a id="16465" class="Keyword">import</a> <a id="16472" href="foundation-core.truncated-maps.html" class="Module">foundation-core.truncated-maps</a>
<a id="16503" class="Keyword">open</a> <a id="16508" class="Keyword">import</a> <a id="16515" href="foundation-core.truncated-types.html" class="Module">foundation-core.truncated-types</a>
<a id="16547" class="Keyword">open</a> <a id="16552" class="Keyword">import</a> <a id="16559" href="foundation-core.truncation-levels.html" class="Module">foundation-core.truncation-levels</a>
<a id="16593" class="Keyword">open</a> <a id="16598" class="Keyword">import</a> <a id="16605" href="foundation-core.type-arithmetic-cartesian-product-types.html" class="Module">foundation-core.type-arithmetic-cartesian-product-types</a>
<a id="16661" class="Keyword">open</a> <a id="16666" class="Keyword">import</a> <a id="16673" href="foundation-core.type-arithmetic-dependent-pair-types.html" class="Module">foundation-core.type-arithmetic-dependent-pair-types</a>
<a id="16726" class="Keyword">open</a> <a id="16731" class="Keyword">import</a> <a id="16738" href="foundation-core.univalence.html" class="Module">foundation-core.univalence</a>
<a id="16765" class="Keyword">open</a> <a id="16770" class="Keyword">import</a> <a id="16777" href="foundation-core.universe-levels.html" class="Module">foundation-core.universe-levels</a>
</pre>
## Graph theory

<pre class="Agda"><a id="16839" class="Keyword">open</a> <a id="16844" class="Keyword">import</a> <a id="16851" href="graph-theory.html" class="Module">graph-theory</a>
<a id="16864" class="Keyword">open</a> <a id="16869" class="Keyword">import</a> <a id="16876" href="graph-theory.connected-undirected-graphs.html" class="Module">graph-theory.connected-undirected-graphs</a>
<a id="16917" class="Keyword">open</a> <a id="16922" class="Keyword">import</a> <a id="16929" href="graph-theory.directed-graphs.html" class="Module">graph-theory.directed-graphs</a>
<a id="16958" class="Keyword">open</a> <a id="16963" class="Keyword">import</a> <a id="16970" href="graph-theory.edge-coloured-undirected-graphs.html" class="Module">graph-theory.edge-coloured-undirected-graphs</a>
<a id="17015" class="Keyword">open</a> <a id="17020" class="Keyword">import</a> <a id="17027" href="graph-theory.equivalences-undirected-graphs.html" class="Module">graph-theory.equivalences-undirected-graphs</a>
<a id="17071" class="Keyword">open</a> <a id="17076" class="Keyword">import</a> <a id="17083" href="graph-theory.finite-graphs.html" class="Module">graph-theory.finite-graphs</a>
<a id="17110" class="Keyword">open</a> <a id="17115" class="Keyword">import</a> <a id="17122" href="graph-theory.incidence-undirected-graphs.html" class="Module">graph-theory.incidence-undirected-graphs</a>
<a id="17163" class="Keyword">open</a> <a id="17168" class="Keyword">import</a> <a id="17175" href="graph-theory.mere-equivalences-undirected-graphs.html" class="Module">graph-theory.mere-equivalences-undirected-graphs</a>
<a id="17224" class="Keyword">open</a> <a id="17229" class="Keyword">import</a> <a id="17236" href="graph-theory.morphisms-directed-graphs.html" class="Module">graph-theory.morphisms-directed-graphs</a>
<a id="17275" class="Keyword">open</a> <a id="17280" class="Keyword">import</a> <a id="17287" href="graph-theory.morphisms-undirected-graphs.html" class="Module">graph-theory.morphisms-undirected-graphs</a>
<a id="17328" class="Keyword">open</a> <a id="17333" class="Keyword">import</a> <a id="17340" href="graph-theory.orientations-undirected-graphs.html" class="Module">graph-theory.orientations-undirected-graphs</a>
<a id="17384" class="Keyword">open</a> <a id="17389" class="Keyword">import</a> <a id="17396" href="graph-theory.paths-undirected-graphs.html" class="Module">graph-theory.paths-undirected-graphs</a>
<a id="17433" class="Keyword">open</a> <a id="17438" class="Keyword">import</a> <a id="17445" href="graph-theory.polygons.html" class="Module">graph-theory.polygons</a>
<a id="17467" class="Keyword">open</a> <a id="17472" class="Keyword">import</a> <a id="17479" href="graph-theory.reflexive-graphs.html" class="Module">graph-theory.reflexive-graphs</a>
<a id="17509" class="Keyword">open</a> <a id="17514" class="Keyword">import</a> <a id="17521" href="graph-theory.regular-undirected-graphs.html" class="Module">graph-theory.regular-undirected-graphs</a>
<a id="17560" class="Keyword">open</a> <a id="17565" class="Keyword">import</a> <a id="17572" href="graph-theory.simple-undirected-graphs.html" class="Module">graph-theory.simple-undirected-graphs</a>
<a id="17610" class="Keyword">open</a> <a id="17615" class="Keyword">import</a> <a id="17622" href="graph-theory.undirected-graphs.html" class="Module">graph-theory.undirected-graphs</a>
</pre>
## Group theory

<pre class="Agda"><a id="17683" class="Keyword">open</a> <a id="17688" class="Keyword">import</a> <a id="17695" href="group-theory.html" class="Module">group-theory</a>
<a id="17708" class="Keyword">open</a> <a id="17713" class="Keyword">import</a> <a id="17720" href="group-theory.abelian-groups.html" class="Module">group-theory.abelian-groups</a>
<a id="17748" class="Keyword">open</a> <a id="17753" class="Keyword">import</a> <a id="17760" href="group-theory.abelian-subgroups.html" class="Module">group-theory.abelian-subgroups</a>
<a id="17791" class="Keyword">open</a> <a id="17796" class="Keyword">import</a> <a id="17803" href="group-theory.abstract-group-torsors.html" class="Module">group-theory.abstract-group-torsors</a>
<a id="17839" class="Keyword">open</a> <a id="17844" class="Keyword">import</a> <a id="17851" href="group-theory.category-of-groups.html" class="Module">group-theory.category-of-groups</a>
<a id="17883" class="Keyword">open</a> <a id="17888" class="Keyword">import</a> <a id="17895" href="group-theory.category-of-semigroups.html" class="Module">group-theory.category-of-semigroups</a>
<a id="17931" class="Keyword">open</a> <a id="17936" class="Keyword">import</a> <a id="17943" href="group-theory.cayleys-theorem.html" class="Module">group-theory.cayleys-theorem</a>
<a id="17972" class="Keyword">open</a> <a id="17977" class="Keyword">import</a> <a id="17984" href="group-theory.concrete-group-actions.html" class="Module">group-theory.concrete-group-actions</a>
<a id="18020" class="Keyword">open</a> <a id="18025" class="Keyword">import</a> <a id="18032" href="group-theory.concrete-groups.html" class="Module">group-theory.concrete-groups</a>
<a id="18061" class="Keyword">open</a> <a id="18066" class="Keyword">import</a> <a id="18073" href="group-theory.concrete-subgroups.html" class="Module">group-theory.concrete-subgroups</a>
<a id="18105" class="Keyword">open</a> <a id="18110" class="Keyword">import</a> <a id="18117" href="group-theory.conjugation.html" class="Module">group-theory.conjugation</a>
<a id="18142" class="Keyword">open</a> <a id="18147" class="Keyword">import</a> <a id="18154" href="group-theory.embeddings-groups.html" class="Module">group-theory.embeddings-groups</a>
<a id="18185" class="Keyword">open</a> <a id="18190" class="Keyword">import</a> <a id="18197" href="group-theory.equivalences-group-actions.html" class="Module">group-theory.equivalences-group-actions</a>
<a id="18237" class="Keyword">open</a> <a id="18242" class="Keyword">import</a> <a id="18249" href="group-theory.equivalences-semigroups.html" class="Module">group-theory.equivalences-semigroups</a>
<a id="18286" class="Keyword">open</a> <a id="18291" class="Keyword">import</a> <a id="18298" href="group-theory.examples-higher-groups.html" class="Module">group-theory.examples-higher-groups</a>
<a id="18334" class="Keyword">open</a> <a id="18339" class="Keyword">import</a> <a id="18346" href="group-theory.furstenberg-groups.html" class="Module">group-theory.furstenberg-groups</a>
<a id="18378" class="Keyword">open</a> <a id="18383" class="Keyword">import</a> <a id="18390" href="group-theory.group-actions.html" class="Module">group-theory.group-actions</a>
<a id="18417" class="Keyword">open</a> <a id="18422" class="Keyword">import</a> <a id="18429" href="group-theory.groups.html" class="Module">group-theory.groups</a>
<a id="18449" class="Keyword">open</a> <a id="18454" class="Keyword">import</a> <a id="18461" href="group-theory.higher-groups.html" class="Module">group-theory.higher-groups</a>
<a id="18488" class="Keyword">open</a> <a id="18493" class="Keyword">import</a> <a id="18500" href="group-theory.homomorphisms-abelian-groups.html" class="Module">group-theory.homomorphisms-abelian-groups</a>
<a id="18542" class="Keyword">open</a> <a id="18547" class="Keyword">import</a> <a id="18554" href="group-theory.homomorphisms-group-actions.html" class="Module">group-theory.homomorphisms-group-actions</a>
<a id="18595" class="Keyword">open</a> <a id="18600" class="Keyword">import</a> <a id="18607" href="group-theory.homomorphisms-groups.html" class="Module">group-theory.homomorphisms-groups</a>
<a id="18641" class="Keyword">open</a> <a id="18646" class="Keyword">import</a> <a id="18653" href="group-theory.homomorphisms-monoids.html" class="Module">group-theory.homomorphisms-monoids</a>
<a id="18688" class="Keyword">open</a> <a id="18693" class="Keyword">import</a> <a id="18700" href="group-theory.homomorphisms-semigroups.html" class="Module">group-theory.homomorphisms-semigroups</a>
<a id="18738" class="Keyword">open</a> <a id="18743" class="Keyword">import</a> <a id="18750" href="group-theory.invertible-elements-monoids.html" class="Module">group-theory.invertible-elements-monoids</a>
<a id="18791" class="Keyword">open</a> <a id="18796" class="Keyword">import</a> <a id="18803" href="group-theory.isomorphisms-abelian-groups.html" class="Module">group-theory.isomorphisms-abelian-groups</a>
<a id="18844" class="Keyword">open</a> <a id="18849" class="Keyword">import</a> <a id="18856" href="group-theory.isomorphisms-group-actions.html" class="Module">group-theory.isomorphisms-group-actions</a>
<a id="18896" class="Keyword">open</a> <a id="18901" class="Keyword">import</a> <a id="18908" href="group-theory.isomorphisms-groups.html" class="Module">group-theory.isomorphisms-groups</a>
<a id="18941" class="Keyword">open</a> <a id="18946" class="Keyword">import</a> <a id="18953" href="group-theory.isomorphisms-semigroups.html" class="Module">group-theory.isomorphisms-semigroups</a>
<a id="18990" class="Keyword">open</a> <a id="18995" class="Keyword">import</a> <a id="19002" href="group-theory.mere-equivalences-group-actions.html" class="Module">group-theory.mere-equivalences-group-actions</a>
<a id="19047" class="Keyword">open</a> <a id="19052" class="Keyword">import</a> <a id="19059" href="group-theory.monoids.html" class="Module">group-theory.monoids</a>
<a id="19080" class="Keyword">open</a> <a id="19085" class="Keyword">import</a> <a id="19092" href="group-theory.orbits-group-actions.html" class="Module">group-theory.orbits-group-actions</a>
<a id="19126" class="Keyword">open</a> <a id="19131" class="Keyword">import</a> <a id="19138" href="group-theory.precategory-of-group-actions.html" class="Module">group-theory.precategory-of-group-actions</a>
<a id="19180" class="Keyword">open</a> <a id="19185" class="Keyword">import</a> <a id="19192" href="group-theory.precategory-of-groups.html" class="Module">group-theory.precategory-of-groups</a>
<a id="19227" class="Keyword">open</a> <a id="19232" class="Keyword">import</a> <a id="19239" href="group-theory.precategory-of-semigroups.html" class="Module">group-theory.precategory-of-semigroups</a>
<a id="19278" class="Keyword">open</a> <a id="19283" class="Keyword">import</a> <a id="19290" href="group-theory.principal-group-actions.html" class="Module">group-theory.principal-group-actions</a>
<a id="19327" class="Keyword">open</a> <a id="19332" class="Keyword">import</a> <a id="19339" href="group-theory.semigroups.html" class="Module">group-theory.semigroups</a>
<a id="19363" class="Keyword">open</a> <a id="19368" class="Keyword">import</a> <a id="19375" href="group-theory.sheargroups.html" class="Module">group-theory.sheargroups</a>
<a id="19400" class="Keyword">open</a> <a id="19405" class="Keyword">import</a> <a id="19412" href="group-theory.stabilizer-groups.html" class="Module">group-theory.stabilizer-groups</a>
<a id="19443" class="Keyword">open</a> <a id="19448" class="Keyword">import</a> <a id="19455" href="group-theory.subgroups.html" class="Module">group-theory.subgroups</a>
<a id="19478" class="Keyword">open</a> <a id="19483" class="Keyword">import</a> <a id="19490" href="group-theory.substitution-functor-group-actions.html" class="Module">group-theory.substitution-functor-group-actions</a>
<a id="19538" class="Keyword">open</a> <a id="19543" class="Keyword">import</a> <a id="19550" href="group-theory.symmetric-groups.html" class="Module">group-theory.symmetric-groups</a>
<a id="19580" class="Keyword">open</a> <a id="19585" class="Keyword">import</a> <a id="19592" href="group-theory.transitive-group-actions.html" class="Module">group-theory.transitive-group-actions</a>
</pre>
## Linear algebra

<pre class="Agda"><a id="19662" class="Keyword">open</a> <a id="19667" class="Keyword">import</a> <a id="19674" href="linear-algebra.html" class="Module">linear-algebra</a>
<a id="19689" class="Keyword">open</a> <a id="19694" class="Keyword">import</a> <a id="19701" href="linear-algebra.constant-matrices.html" class="Module">linear-algebra.constant-matrices</a>
<a id="19734" class="Keyword">open</a> <a id="19739" class="Keyword">import</a> <a id="19746" href="linear-algebra.constant-vectors.html" class="Module">linear-algebra.constant-vectors</a>
<a id="19778" class="Keyword">open</a> <a id="19783" class="Keyword">import</a> <a id="19790" href="linear-algebra.diagonal-matrices-on-rings.html" class="Module">linear-algebra.diagonal-matrices-on-rings</a>
<a id="19832" class="Keyword">open</a> <a id="19837" class="Keyword">import</a> <a id="19844" href="linear-algebra.functoriality-matrices.html" class="Module">linear-algebra.functoriality-matrices</a>
<a id="19882" class="Keyword">open</a> <a id="19887" class="Keyword">import</a> <a id="19894" href="linear-algebra.functoriality-vectors.html" class="Module">linear-algebra.functoriality-vectors</a>
<a id="19931" class="Keyword">open</a> <a id="19936" class="Keyword">import</a> <a id="19943" href="linear-algebra.matrices-on-rings.html" class="Module">linear-algebra.matrices-on-rings</a>
<a id="19976" class="Keyword">open</a> <a id="19981" class="Keyword">import</a> <a id="19988" href="linear-algebra.matrices.html" class="Module">linear-algebra.matrices</a>
<a id="20012" class="Keyword">open</a> <a id="20017" class="Keyword">import</a> <a id="20024" href="linear-algebra.multiplication-matrices.html" class="Module">linear-algebra.multiplication-matrices</a>
<a id="20063" class="Keyword">open</a> <a id="20068" class="Keyword">import</a> <a id="20075" href="linear-algebra.scalar-multiplication-matrices.html" class="Module">linear-algebra.scalar-multiplication-matrices</a>
<a id="20121" class="Keyword">open</a> <a id="20126" class="Keyword">import</a> <a id="20133" href="linear-algebra.scalar-multiplication-vectors.html" class="Module">linear-algebra.scalar-multiplication-vectors</a>
<a id="20178" class="Keyword">open</a> <a id="20183" class="Keyword">import</a> <a id="20190" href="linear-algebra.transposition-matrices.html" class="Module">linear-algebra.transposition-matrices</a>
<a id="20228" class="Keyword">open</a> <a id="20233" class="Keyword">import</a> <a id="20240" href="linear-algebra.vectors-on-rings.html" class="Module">linear-algebra.vectors-on-rings</a>
<a id="20272" class="Keyword">open</a> <a id="20277" class="Keyword">import</a> <a id="20284" href="linear-algebra.vectors.html" class="Module">linear-algebra.vectors</a>
</pre>
## Order theory

<pre class="Agda"><a id="20337" class="Keyword">open</a> <a id="20342" class="Keyword">import</a> <a id="20349" href="order-theory.html" class="Module">order-theory</a>
<a id="20362" class="Keyword">open</a> <a id="20367" class="Keyword">import</a> <a id="20374" href="order-theory.chains-posets.html" class="Module">order-theory.chains-posets</a>
<a id="20401" class="Keyword">open</a> <a id="20406" class="Keyword">import</a> <a id="20413" href="order-theory.chains-preorders.html" class="Module">order-theory.chains-preorders</a>
<a id="20443" class="Keyword">open</a> <a id="20448" class="Keyword">import</a> <a id="20455" href="order-theory.decidable-subposets.html" class="Module">order-theory.decidable-subposets</a>
<a id="20488" class="Keyword">open</a> <a id="20493" class="Keyword">import</a> <a id="20500" href="order-theory.decidable-subpreorders.html" class="Module">order-theory.decidable-subpreorders</a>
<a id="20536" class="Keyword">open</a> <a id="20541" class="Keyword">import</a> <a id="20548" href="order-theory.finite-posets.html" class="Module">order-theory.finite-posets</a>
<a id="20575" class="Keyword">open</a> <a id="20580" class="Keyword">import</a> <a id="20587" href="order-theory.finite-preorders.html" class="Module">order-theory.finite-preorders</a>
<a id="20617" class="Keyword">open</a> <a id="20622" class="Keyword">import</a> <a id="20629" href="order-theory.finitely-graded-posets.html" class="Module">order-theory.finitely-graded-posets</a>
<a id="20665" class="Keyword">open</a> <a id="20670" class="Keyword">import</a> <a id="20677" href="order-theory.interval-subposets.html" class="Module">order-theory.interval-subposets</a>
<a id="20709" class="Keyword">open</a> <a id="20714" class="Keyword">import</a> <a id="20721" href="order-theory.largest-elements-posets.html" class="Module">order-theory.largest-elements-posets</a>
<a id="20758" class="Keyword">open</a> <a id="20763" class="Keyword">import</a> <a id="20770" href="order-theory.largest-elements-preorders.html" class="Module">order-theory.largest-elements-preorders</a>
<a id="20810" class="Keyword">open</a> <a id="20815" class="Keyword">import</a> <a id="20822" href="order-theory.least-elements-posets.html" class="Module">order-theory.least-elements-posets</a>
<a id="20857" class="Keyword">open</a> <a id="20862" class="Keyword">import</a> <a id="20869" href="order-theory.least-elements-preorders.html" class="Module">order-theory.least-elements-preorders</a>
<a id="20907" class="Keyword">open</a> <a id="20912" class="Keyword">import</a> <a id="20919" href="order-theory.locally-finite-posets.html" class="Module">order-theory.locally-finite-posets</a>
<a id="20954" class="Keyword">open</a> <a id="20959" class="Keyword">import</a> <a id="20966" href="order-theory.maximal-chains-posets.html" class="Module">order-theory.maximal-chains-posets</a>
<a id="21001" class="Keyword">open</a> <a id="21006" class="Keyword">import</a> <a id="21013" href="order-theory.maximal-chains-preorders.html" class="Module">order-theory.maximal-chains-preorders</a>
<a id="21051" class="Keyword">open</a> <a id="21056" class="Keyword">import</a> <a id="21063" href="order-theory.planar-binary-trees.html" class="Module">order-theory.planar-binary-trees</a>
<a id="21096" class="Keyword">open</a> <a id="21101" class="Keyword">import</a> <a id="21108" href="order-theory.posets.html" class="Module">order-theory.posets</a>
<a id="21128" class="Keyword">open</a> <a id="21133" class="Keyword">import</a> <a id="21140" href="order-theory.preorders.html" class="Module">order-theory.preorders</a>
<a id="21163" class="Keyword">open</a> <a id="21168" class="Keyword">import</a> <a id="21175" href="order-theory.subposets.html" class="Module">order-theory.subposets</a>
<a id="21198" class="Keyword">open</a> <a id="21203" class="Keyword">import</a> <a id="21210" href="order-theory.subpreorders.html" class="Module">order-theory.subpreorders</a>
<a id="21236" class="Keyword">open</a> <a id="21241" class="Keyword">import</a> <a id="21248" href="order-theory.total-posets.html" class="Module">order-theory.total-posets</a>
<a id="21274" class="Keyword">open</a> <a id="21279" class="Keyword">import</a> <a id="21286" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a>
</pre>
## Polytopes

<pre class="Agda"><a id="21342" class="Keyword">open</a> <a id="21347" class="Keyword">import</a> <a id="21354" href="polytopes.html" class="Module">polytopes</a>
<a id="21364" class="Keyword">open</a> <a id="21369" class="Keyword">import</a> <a id="21376" href="polytopes.abstract-polytopes.html" class="Module">polytopes.abstract-polytopes</a>
</pre>
## Ring theory

<pre class="Agda"><a id="21434" class="Keyword">open</a> <a id="21439" class="Keyword">import</a> <a id="21446" href="ring-theory.html" class="Module">ring-theory</a>
<a id="21458" class="Keyword">open</a> <a id="21463" class="Keyword">import</a> <a id="21470" href="ring-theory.commutative-rings.html" class="Module">ring-theory.commutative-rings</a>
<a id="21500" class="Keyword">open</a> <a id="21505" class="Keyword">import</a> <a id="21512" href="ring-theory.discrete-fields.html" class="Module">ring-theory.discrete-fields</a>
<a id="21540" class="Keyword">open</a> <a id="21545" class="Keyword">import</a> <a id="21552" href="ring-theory.division-rings.html" class="Module">ring-theory.division-rings</a>
<a id="21579" class="Keyword">open</a> <a id="21584" class="Keyword">import</a> <a id="21591" href="ring-theory.eisenstein-integers.html" class="Module">ring-theory.eisenstein-integers</a>
<a id="21623" class="Keyword">open</a> <a id="21628" class="Keyword">import</a> <a id="21635" href="ring-theory.gaussian-integers.html" class="Module">ring-theory.gaussian-integers</a>
<a id="21665" class="Keyword">open</a> <a id="21670" class="Keyword">import</a> <a id="21677" href="ring-theory.homomorphisms-commutative-rings.html" class="Module">ring-theory.homomorphisms-commutative-rings</a>
<a id="21721" class="Keyword">open</a> <a id="21726" class="Keyword">import</a> <a id="21733" href="ring-theory.homomorphisms-rings.html" class="Module">ring-theory.homomorphisms-rings</a>
<a id="21765" class="Keyword">open</a> <a id="21770" class="Keyword">import</a> <a id="21777" href="ring-theory.ideals.html" class="Module">ring-theory.ideals</a>
<a id="21796" class="Keyword">open</a> <a id="21801" class="Keyword">import</a> <a id="21808" href="ring-theory.invertible-elements-rings.html" class="Module">ring-theory.invertible-elements-rings</a>
<a id="21846" class="Keyword">open</a> <a id="21851" class="Keyword">import</a> <a id="21858" href="ring-theory.isomorphisms-commutative-rings.html" class="Module">ring-theory.isomorphisms-commutative-rings</a>
<a id="21901" class="Keyword">open</a> <a id="21906" class="Keyword">import</a> <a id="21913" href="ring-theory.isomorphisms-rings.html" class="Module">ring-theory.isomorphisms-rings</a>
<a id="21944" class="Keyword">open</a> <a id="21949" class="Keyword">import</a> <a id="21956" href="ring-theory.localizations-rings.html" class="Module">ring-theory.localizations-rings</a>
<a id="21988" class="Keyword">open</a> <a id="21993" class="Keyword">import</a> <a id="22000" href="ring-theory.nontrivial-rings.html" class="Module">ring-theory.nontrivial-rings</a>
<a id="22029" class="Keyword">open</a> <a id="22034" class="Keyword">import</a> <a id="22041" href="ring-theory.rings.html" class="Module">ring-theory.rings</a>
</pre>
## Synthetic homotopy theory

<pre class="Agda"><a id="22102" class="Keyword">open</a> <a id="22107" class="Keyword">import</a> <a id="22114" href="synthetic-homotopy-theory.html" class="Module">synthetic-homotopy-theory</a>
<a id="22140" class="Keyword">open</a> <a id="22145" class="Keyword">import</a> <a id="22152" href="synthetic-homotopy-theory.23-pullbacks.html" class="Module">synthetic-homotopy-theory.23-pullbacks</a>
<a id="22191" class="Keyword">open</a> <a id="22196" class="Keyword">import</a> <a id="22203" href="synthetic-homotopy-theory.24-pushouts.html" class="Module">synthetic-homotopy-theory.24-pushouts</a>
<a id="22241" class="Keyword">open</a> <a id="22246" class="Keyword">import</a> <a id="22253" href="synthetic-homotopy-theory.25-cubical-diagrams.html" class="Module">synthetic-homotopy-theory.25-cubical-diagrams</a>
<a id="22299" class="Keyword">open</a> <a id="22304" class="Keyword">import</a> <a id="22311" href="synthetic-homotopy-theory.26-descent.html" class="Module">synthetic-homotopy-theory.26-descent</a>
<a id="22348" class="Keyword">open</a> <a id="22353" class="Keyword">import</a> <a id="22360" href="synthetic-homotopy-theory.26-id-pushout.html" class="Module">synthetic-homotopy-theory.26-id-pushout</a>
<a id="22400" class="Keyword">open</a> <a id="22405" class="Keyword">import</a> <a id="22412" href="synthetic-homotopy-theory.27-sequences.html" class="Module">synthetic-homotopy-theory.27-sequences</a>
<a id="22451" class="Keyword">open</a> <a id="22456" class="Keyword">import</a> <a id="22463" href="synthetic-homotopy-theory.circle.html" class="Module">synthetic-homotopy-theory.circle</a>
<a id="22496" class="Keyword">open</a> <a id="22501" class="Keyword">import</a> <a id="22508" href="synthetic-homotopy-theory.cyclic-types.html" class="Module">synthetic-homotopy-theory.cyclic-types</a>
<a id="22547" class="Keyword">open</a> <a id="22552" class="Keyword">import</a> <a id="22559" href="synthetic-homotopy-theory.double-loop-spaces.html" class="Module">synthetic-homotopy-theory.double-loop-spaces</a>
<a id="22604" class="Keyword">open</a> <a id="22609" class="Keyword">import</a> <a id="22616" href="synthetic-homotopy-theory.functoriality-loop-spaces.html" class="Module">synthetic-homotopy-theory.functoriality-loop-spaces</a>
<a id="22668" class="Keyword">open</a> <a id="22673" class="Keyword">import</a> <a id="22680" href="synthetic-homotopy-theory.groups-of-loops-in-1-types.html" class="Module">synthetic-homotopy-theory.groups-of-loops-in-1-types</a>
<a id="22733" class="Keyword">open</a> <a id="22738" class="Keyword">import</a> <a id="22745" href="synthetic-homotopy-theory.infinite-cyclic-types.html" class="Module">synthetic-homotopy-theory.infinite-cyclic-types</a>
<a id="22793" class="Keyword">open</a> <a id="22798" class="Keyword">import</a> <a id="22805" href="synthetic-homotopy-theory.interval-type.html" class="Module">synthetic-homotopy-theory.interval-type</a>
<a id="22845" class="Keyword">open</a> <a id="22850" class="Keyword">import</a> <a id="22857" href="synthetic-homotopy-theory.iterated-loop-spaces.html" class="Module">synthetic-homotopy-theory.iterated-loop-spaces</a>
<a id="22904" class="Keyword">open</a> <a id="22909" class="Keyword">import</a> <a id="22916" href="synthetic-homotopy-theory.loop-spaces.html" class="Module">synthetic-homotopy-theory.loop-spaces</a>
<a id="22954" class="Keyword">open</a> <a id="22959" class="Keyword">import</a> <a id="22966" href="synthetic-homotopy-theory.pointed-dependent-functions.html" class="Module">synthetic-homotopy-theory.pointed-dependent-functions</a>
<a id="23020" class="Keyword">open</a> <a id="23025" class="Keyword">import</a> <a id="23032" href="synthetic-homotopy-theory.pointed-equivalences.html" class="Module">synthetic-homotopy-theory.pointed-equivalences</a>
<a id="23079" class="Keyword">open</a> <a id="23084" class="Keyword">import</a> <a id="23091" href="synthetic-homotopy-theory.pointed-families-of-types.html" class="Module">synthetic-homotopy-theory.pointed-families-of-types</a>
<a id="23143" class="Keyword">open</a> <a id="23148" class="Keyword">import</a> <a id="23155" href="synthetic-homotopy-theory.pointed-homotopies.html" class="Module">synthetic-homotopy-theory.pointed-homotopies</a>
<a id="23200" class="Keyword">open</a> <a id="23205" class="Keyword">import</a> <a id="23212" href="synthetic-homotopy-theory.pointed-maps.html" class="Module">synthetic-homotopy-theory.pointed-maps</a>
<a id="23251" class="Keyword">open</a> <a id="23256" class="Keyword">import</a> <a id="23263" href="synthetic-homotopy-theory.pointed-types.html" class="Module">synthetic-homotopy-theory.pointed-types</a>
<a id="23303" class="Keyword">open</a> <a id="23308" class="Keyword">import</a> <a id="23315" href="synthetic-homotopy-theory.spaces.html" class="Module">synthetic-homotopy-theory.spaces</a>
<a id="23348" class="Keyword">open</a> <a id="23353" class="Keyword">import</a> <a id="23360" href="synthetic-homotopy-theory.triple-loop-spaces.html" class="Module">synthetic-homotopy-theory.triple-loop-spaces</a>
<a id="23405" class="Keyword">open</a> <a id="23410" class="Keyword">import</a> <a id="23417" href="synthetic-homotopy-theory.universal-cover-circle.html" class="Module">synthetic-homotopy-theory.universal-cover-circle</a>
</pre>
## Tutorials

<pre class="Agda"><a id="23493" class="Keyword">open</a> <a id="23498" class="Keyword">import</a> <a id="23505" href="tutorials.basic-agda.html" class="Module">tutorials.basic-agda</a>
</pre>
## Univalent combinatorics

<pre class="Agda"><a id="23567" class="Keyword">open</a> <a id="23572" class="Keyword">import</a> <a id="23579" href="univalent-combinatorics.html" class="Module">univalent-combinatorics</a>
<a id="23603" class="Keyword">open</a> <a id="23608" class="Keyword">import</a> <a id="23615" href="univalent-combinatorics.2-element-subtypes.html" class="Module">univalent-combinatorics.2-element-subtypes</a>
<a id="23658" class="Keyword">open</a> <a id="23663" class="Keyword">import</a> <a id="23670" href="univalent-combinatorics.2-element-types.html" class="Module">univalent-combinatorics.2-element-types</a>
<a id="23710" class="Keyword">open</a> <a id="23715" class="Keyword">import</a> <a id="23722" href="univalent-combinatorics.binomial-types.html" class="Module">univalent-combinatorics.binomial-types</a>
<a id="23761" class="Keyword">open</a> <a id="23766" class="Keyword">import</a> <a id="23773" href="univalent-combinatorics.cartesian-product-types.html" class="Module">univalent-combinatorics.cartesian-product-types</a>
<a id="23821" class="Keyword">open</a> <a id="23826" class="Keyword">import</a> <a id="23833" href="univalent-combinatorics.classical-finite-types.html" class="Module">univalent-combinatorics.classical-finite-types</a>
<a id="23880" class="Keyword">open</a> <a id="23885" class="Keyword">import</a> <a id="23892" href="univalent-combinatorics.complements-isolated-points.html" class="Module">univalent-combinatorics.complements-isolated-points</a>
<a id="23944" class="Keyword">open</a> <a id="23949" class="Keyword">import</a> <a id="23956" href="univalent-combinatorics.coproduct-types.html" class="Module">univalent-combinatorics.coproduct-types</a>
<a id="23996" class="Keyword">open</a> <a id="24001" class="Keyword">import</a> <a id="24008" href="univalent-combinatorics.counting-decidable-subtypes.html" class="Module">univalent-combinatorics.counting-decidable-subtypes</a>
<a id="24060" class="Keyword">open</a> <a id="24065" class="Keyword">import</a> <a id="24072" href="univalent-combinatorics.counting-dependent-function-types.html" class="Module">univalent-combinatorics.counting-dependent-function-types</a>
<a id="24130" class="Keyword">open</a> <a id="24135" class="Keyword">import</a> <a id="24142" href="univalent-combinatorics.counting-dependent-pair-types.html" class="Module">univalent-combinatorics.counting-dependent-pair-types</a>
<a id="24196" class="Keyword">open</a> <a id="24201" class="Keyword">import</a> <a id="24208" href="univalent-combinatorics.counting-fibers-of-maps.html" class="Module">univalent-combinatorics.counting-fibers-of-maps</a>
<a id="24256" class="Keyword">open</a> <a id="24261" class="Keyword">import</a> <a id="24268" href="univalent-combinatorics.counting-function-types.html" class="Module">univalent-combinatorics.counting-function-types</a>
<a id="24316" class="Keyword">open</a> <a id="24321" class="Keyword">import</a> <a id="24328" href="univalent-combinatorics.counting-maybe.html" class="Module">univalent-combinatorics.counting-maybe</a>
<a id="24367" class="Keyword">open</a> <a id="24372" class="Keyword">import</a> <a id="24379" href="univalent-combinatorics.counting.html" class="Module">univalent-combinatorics.counting</a>
<a id="24412" class="Keyword">open</a> <a id="24417" class="Keyword">import</a> <a id="24424" href="univalent-combinatorics.cubes.html" class="Module">univalent-combinatorics.cubes</a>
<a id="24454" class="Keyword">open</a> <a id="24459" class="Keyword">import</a> <a id="24466" href="univalent-combinatorics.decidable-dependent-function-types.html" class="Module">univalent-combinatorics.decidable-dependent-function-types</a>
<a id="24525" class="Keyword">open</a> <a id="24530" class="Keyword">import</a> <a id="24537" href="univalent-combinatorics.decidable-dependent-pair-types.html" class="Module">univalent-combinatorics.decidable-dependent-pair-types</a>
<a id="24592" class="Keyword">open</a> <a id="24597" class="Keyword">import</a> <a id="24604" href="univalent-combinatorics.decidable-subtypes.html" class="Module">univalent-combinatorics.decidable-subtypes</a>
<a id="24647" class="Keyword">open</a> <a id="24652" class="Keyword">import</a> <a id="24659" href="univalent-combinatorics.dependent-product-finite-types.html" class="Module">univalent-combinatorics.dependent-product-finite-types</a>
<a id="24714" class="Keyword">open</a> <a id="24719" class="Keyword">import</a> <a id="24726" href="univalent-combinatorics.dependent-sum-finite-types.html" class="Module">univalent-combinatorics.dependent-sum-finite-types</a>
<a id="24777" class="Keyword">open</a> <a id="24782" class="Keyword">import</a> <a id="24789" href="univalent-combinatorics.distributivity-of-set-truncation-over-finite-products.html" class="Module">univalent-combinatorics.distributivity-of-set-truncation-over-finite-products</a>
<a id="24867" class="Keyword">open</a> <a id="24872" class="Keyword">import</a> <a id="24879" href="univalent-combinatorics.double-counting.html" class="Module">univalent-combinatorics.double-counting</a>
<a id="24919" class="Keyword">open</a> <a id="24924" class="Keyword">import</a> <a id="24931" href="univalent-combinatorics.embeddings-standard-finite-types.html" class="Module">univalent-combinatorics.embeddings-standard-finite-types</a>
<a id="24988" class="Keyword">open</a> <a id="24993" class="Keyword">import</a> <a id="25000" href="univalent-combinatorics.embeddings.html" class="Module">univalent-combinatorics.embeddings</a>
<a id="25035" class="Keyword">open</a> <a id="25040" class="Keyword">import</a> <a id="25047" href="univalent-combinatorics.equality-finite-types.html" class="Module">univalent-combinatorics.equality-finite-types</a>
<a id="25093" class="Keyword">open</a> <a id="25098" class="Keyword">import</a> <a id="25105" href="univalent-combinatorics.equality-standard-finite-types.html" class="Module">univalent-combinatorics.equality-standard-finite-types</a>
<a id="25160" class="Keyword">open</a> <a id="25165" class="Keyword">import</a> <a id="25172" href="univalent-combinatorics.equivalences-cubes.html" class="Module">univalent-combinatorics.equivalences-cubes</a>
<a id="25215" class="Keyword">open</a> <a id="25220" class="Keyword">import</a> <a id="25227" href="univalent-combinatorics.equivalences-standard-finite-types.html" class="Module">univalent-combinatorics.equivalences-standard-finite-types</a>
<a id="25286" class="Keyword">open</a> <a id="25291" class="Keyword">import</a> <a id="25298" href="univalent-combinatorics.equivalences.html" class="Module">univalent-combinatorics.equivalences</a>
<a id="25335" class="Keyword">open</a> <a id="25340" class="Keyword">import</a> <a id="25347" href="univalent-combinatorics.fibers-of-maps-between-finite-types.html" class="Module">univalent-combinatorics.fibers-of-maps-between-finite-types</a>
<a id="25407" class="Keyword">open</a> <a id="25412" class="Keyword">import</a> <a id="25419" href="univalent-combinatorics.finite-choice.html" class="Module">univalent-combinatorics.finite-choice</a>
<a id="25457" class="Keyword">open</a> <a id="25462" class="Keyword">import</a> <a id="25469" href="univalent-combinatorics.finite-connected-components.html" class="Module">univalent-combinatorics.finite-connected-components</a>
<a id="25521" class="Keyword">open</a> <a id="25526" class="Keyword">import</a> <a id="25533" href="univalent-combinatorics.finite-function-types.html" class="Module">univalent-combinatorics.finite-function-types</a>
<a id="25579" class="Keyword">open</a> <a id="25584" class="Keyword">import</a> <a id="25591" href="univalent-combinatorics.finite-presentations.html" class="Module">univalent-combinatorics.finite-presentations</a>
<a id="25636" class="Keyword">open</a> <a id="25641" class="Keyword">import</a> <a id="25648" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a>
<a id="25685" class="Keyword">open</a> <a id="25690" class="Keyword">import</a> <a id="25697" href="univalent-combinatorics.finitely-presented-types.html" class="Module">univalent-combinatorics.finitely-presented-types</a>
<a id="25746" class="Keyword">open</a> <a id="25751" class="Keyword">import</a> <a id="25758" href="univalent-combinatorics.image-of-maps.html" class="Module">univalent-combinatorics.image-of-maps</a>
<a id="25796" class="Keyword">open</a> <a id="25801" class="Keyword">import</a> <a id="25808" href="univalent-combinatorics.inequality-types-with-counting.html" class="Module">univalent-combinatorics.inequality-types-with-counting</a>
<a id="25863" class="Keyword">open</a> <a id="25868" class="Keyword">import</a> <a id="25875" href="univalent-combinatorics.injective-maps.html" class="Module">univalent-combinatorics.injective-maps</a>
<a id="25914" class="Keyword">open</a> <a id="25919" class="Keyword">import</a> <a id="25926" href="univalent-combinatorics.lists.html" class="Module">univalent-combinatorics.lists</a>
<a id="25956" class="Keyword">open</a> <a id="25961" class="Keyword">import</a> <a id="25968" href="univalent-combinatorics.maybe.html" class="Module">univalent-combinatorics.maybe</a>
<a id="25998" class="Keyword">open</a> <a id="26003" class="Keyword">import</a> <a id="26010" href="univalent-combinatorics.orientations-cubes.html" class="Module">univalent-combinatorics.orientations-cubes</a>
<a id="26053" class="Keyword">open</a> <a id="26058" class="Keyword">import</a> <a id="26065" href="univalent-combinatorics.pi-finite-types.html" class="Module">univalent-combinatorics.pi-finite-types</a>
<a id="26105" class="Keyword">open</a> <a id="26110" class="Keyword">import</a> <a id="26117" href="univalent-combinatorics.pigeonhole-principle.html" class="Module">univalent-combinatorics.pigeonhole-principle</a>
<a id="26162" class="Keyword">open</a> <a id="26167" class="Keyword">import</a> <a id="26174" href="univalent-combinatorics.presented-pi-finite-types.html" class="Module">univalent-combinatorics.presented-pi-finite-types</a>
<a id="26224" class="Keyword">open</a> <a id="26229" class="Keyword">import</a> <a id="26236" href="univalent-combinatorics.ramsey-theory.html" class="Module">univalent-combinatorics.ramsey-theory</a>
<a id="26274" class="Keyword">open</a> <a id="26279" class="Keyword">import</a> <a id="26286" href="univalent-combinatorics.retracts-of-finite-types.html" class="Module">univalent-combinatorics.retracts-of-finite-types</a>
<a id="26335" class="Keyword">open</a> <a id="26340" class="Keyword">import</a> <a id="26347" href="univalent-combinatorics.skipping-element-standard-finite-types.html" class="Module">univalent-combinatorics.skipping-element-standard-finite-types</a>
<a id="26410" class="Keyword">open</a> <a id="26415" class="Keyword">import</a> <a id="26422" href="univalent-combinatorics.species.html" class="Module">univalent-combinatorics.species</a>
<a id="26454" class="Keyword">open</a> <a id="26459" class="Keyword">import</a> <a id="26466" href="univalent-combinatorics.standard-finite-pruned-trees.html" class="Module">univalent-combinatorics.standard-finite-pruned-trees</a>
<a id="26519" class="Keyword">open</a> <a id="26524" class="Keyword">import</a> <a id="26531" href="univalent-combinatorics.standard-finite-trees.html" class="Module">univalent-combinatorics.standard-finite-trees</a>
<a id="26577" class="Keyword">open</a> <a id="26582" class="Keyword">import</a> <a id="26589" href="univalent-combinatorics.standard-finite-types.html" class="Module">univalent-combinatorics.standard-finite-types</a>
<a id="26635" class="Keyword">open</a> <a id="26640" class="Keyword">import</a> <a id="26647" href="univalent-combinatorics.sums-of-natural-numbers.html" class="Module">univalent-combinatorics.sums-of-natural-numbers</a>
<a id="26695" class="Keyword">open</a> <a id="26700" class="Keyword">import</a> <a id="26707" href="univalent-combinatorics.surjective-maps.html" class="Module">univalent-combinatorics.surjective-maps</a>
</pre>
## Wild algebra

<pre class="Agda"><a id="26777" class="Keyword">open</a> <a id="26782" class="Keyword">import</a> <a id="26789" href="wild-algebra.html" class="Module">wild-algebra</a>
<a id="26802" class="Keyword">open</a> <a id="26807" class="Keyword">import</a> <a id="26814" href="wild-algebra.magmas.html" class="Module">wild-algebra.magmas</a>
<a id="26834" class="Keyword">open</a> <a id="26839" class="Keyword">import</a> <a id="26846" href="wild-algebra.universal-property-lists-wild-monoids.html" class="Module">wild-algebra.universal-property-lists-wild-monoids</a>
<a id="26897" class="Keyword">open</a> <a id="26902" class="Keyword">import</a> <a id="26909" href="wild-algebra.wild-groups.html" class="Module">wild-algebra.wild-groups</a>
<a id="26934" class="Keyword">open</a> <a id="26939" class="Keyword">import</a> <a id="26946" href="wild-algebra.wild-monoids.html" class="Module">wild-algebra.wild-monoids</a>
<a id="26972" class="Keyword">open</a> <a id="26977" class="Keyword">import</a> <a id="26984" href="wild-algebra.wild-unital-magmas.html" class="Module">wild-algebra.wild-unital-magmas</a>
</pre>
## Everything

See the list of all Agda modules [here](everything.html).

