# Univalent mathematics in Agda

Welcome to the website of the `agda-unimath` formalization project.

[![CI](https://github.com/UniMath/agda-unimath/actions/workflows/ci.yaml/badge.svg)](https://github.com/UniMath/agda-unimath/actions/workflows/ci.yaml) [![pages-build-deployment](https://github.com/UniMath/agda-unimath/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/UniMath/agda-unimath/actions/workflows/pages/pages-build-deployment)

The `agda-unimath` library is a new formalisation project for univalent mathematics in Agda. Our goal is to formalize an extensive curriculum of mathematics from the univalent point of view. Furthermore, we think libraries of formalized mathematics have the potential to be useful, and informative resources for mathematicians. Our library is designed to work towards this goal, and we welcome contributions to the library about any topic in mathematics.

The library is built in Agda 2.6.2. It can be compiled by running `make check` from the main folder of the repository.

## Joining the project

Great, you want to contribute something! The best way to start is to find us in our chat channels on the [agda-unimath discord](https://discord.gg/Zp2e8hYsuX). We have a vibing community there, and you're more than welcome to join us just to hang out.

Once you've decided what you want to contribute, the best way to proceed is to make your own fork of the library. Within your fork, make a separate branch in which you will be making your contributions. Now you're ready to start your project! When you've completed your formalization you can proceed by making a pull request. Then we will review your contributions, and merge it when it is ready for the `agda-unimath` library.

## Statement of inclusion

There are many reasons to contribute something to a library of formalized mathematics. Some do it just for fun, some do it for their research, some do it to learn something. Whatever your reason is, we welcome your contributions! To keep the experience of contributing something to our library enjoyable for everyone, we strive for an inclusive community of contributors. You can expect from us that we are kind and respectful in discussions, that we will be mindful of your pronouns and use [inclusive language](https://www.apa.org/about/apa/equity-diversity-inclusion/language-guidelines), and that we value your input regardless of your level of experience or status in the community. We're commited to providing a safe and welcoming environment to people of any gender identity, sexual orientation, race, colour, age, ability, ethnicity, background, or fluency in English -- here on github, in online communication channels, and in person. Homotopy type theory is difficult enough without all the barriers that many of us have to face, so we hope to bring some of those down a bit.

:rainbow: Happy contributing!

Elisabeth Bonnevier  
Jonathan Prieto-Cubides  
Egbert Rijke

<pre class="Agda"><a id="2967" class="Symbol">{-#</a> <a id="2971" class="Keyword">OPTIONS</a> <a id="2979" class="Pragma">--without-K</a> <a id="2991" class="Pragma">--exact-split</a> <a id="3005" class="Pragma">--guardedness</a> <a id="3019" class="Symbol">#-}</a>
</pre>
## Category theory

<pre class="Agda"><a id="3056" class="Keyword">open</a> <a id="3061" class="Keyword">import</a> <a id="3068" href="category-theory.html" class="Module">category-theory</a>
<a id="3084" class="Keyword">open</a> <a id="3089" class="Keyword">import</a> <a id="3096" href="category-theory.adjunctions-large-precategories.html" class="Module">category-theory.adjunctions-large-precategories</a>
<a id="3144" class="Keyword">open</a> <a id="3149" class="Keyword">import</a> <a id="3156" href="category-theory.anafunctors.html" class="Module">category-theory.anafunctors</a>
<a id="3184" class="Keyword">open</a> <a id="3189" class="Keyword">import</a> <a id="3196" href="category-theory.categories.html" class="Module">category-theory.categories</a>
<a id="3223" class="Keyword">open</a> <a id="3228" class="Keyword">import</a> <a id="3235" href="category-theory.epimorphisms-large-precategories.html" class="Module">category-theory.epimorphisms-large-precategories</a>
<a id="3284" class="Keyword">open</a> <a id="3289" class="Keyword">import</a> <a id="3296" href="category-theory.equivalences-categories.html" class="Module">category-theory.equivalences-categories</a>
<a id="3336" class="Keyword">open</a> <a id="3341" class="Keyword">import</a> <a id="3348" href="category-theory.equivalences-large-precategories.html" class="Module">category-theory.equivalences-large-precategories</a>
<a id="3397" class="Keyword">open</a> <a id="3402" class="Keyword">import</a> <a id="3409" href="category-theory.equivalences-precategories.html" class="Module">category-theory.equivalences-precategories</a>
<a id="3452" class="Keyword">open</a> <a id="3457" class="Keyword">import</a> <a id="3464" href="category-theory.functors-categories.html" class="Module">category-theory.functors-categories</a>
<a id="3500" class="Keyword">open</a> <a id="3505" class="Keyword">import</a> <a id="3512" href="category-theory.functors-large-precategories.html" class="Module">category-theory.functors-large-precategories</a>
<a id="3557" class="Keyword">open</a> <a id="3562" class="Keyword">import</a> <a id="3569" href="category-theory.functors-precategories.html" class="Module">category-theory.functors-precategories</a>
<a id="3608" class="Keyword">open</a> <a id="3613" class="Keyword">import</a> <a id="3620" href="category-theory.homotopies-natural-transformations-large-precategories.html" class="Module">category-theory.homotopies-natural-transformations-large-precategories</a>
<a id="3691" class="Keyword">open</a> <a id="3696" class="Keyword">import</a> <a id="3703" href="category-theory.initial-objects-precategories.html" class="Module">category-theory.initial-objects-precategories</a>
<a id="3749" class="Keyword">open</a> <a id="3754" class="Keyword">import</a> <a id="3761" href="category-theory.isomorphisms-categories.html" class="Module">category-theory.isomorphisms-categories</a>
<a id="3801" class="Keyword">open</a> <a id="3806" class="Keyword">import</a> <a id="3813" href="category-theory.isomorphisms-large-precategories.html" class="Module">category-theory.isomorphisms-large-precategories</a>
<a id="3862" class="Keyword">open</a> <a id="3867" class="Keyword">import</a> <a id="3874" href="category-theory.isomorphisms-precategories.html" class="Module">category-theory.isomorphisms-precategories</a>
<a id="3917" class="Keyword">open</a> <a id="3922" class="Keyword">import</a> <a id="3929" href="category-theory.large-categories.html" class="Module">category-theory.large-categories</a>
<a id="3962" class="Keyword">open</a> <a id="3967" class="Keyword">import</a> <a id="3974" href="category-theory.large-precategories.html" class="Module">category-theory.large-precategories</a>
<a id="4010" class="Keyword">open</a> <a id="4015" class="Keyword">import</a> <a id="4022" href="category-theory.monomorphisms-large-precategories.html" class="Module">category-theory.monomorphisms-large-precategories</a>
<a id="4072" class="Keyword">open</a> <a id="4077" class="Keyword">import</a> <a id="4084" href="category-theory.natural-isomorphisms-categories.html" class="Module">category-theory.natural-isomorphisms-categories</a>
<a id="4132" class="Keyword">open</a> <a id="4137" class="Keyword">import</a> <a id="4144" href="category-theory.natural-isomorphisms-large-precategories.html" class="Module">category-theory.natural-isomorphisms-large-precategories</a>
<a id="4201" class="Keyword">open</a> <a id="4206" class="Keyword">import</a> <a id="4213" href="category-theory.natural-isomorphisms-precategories.html" class="Module">category-theory.natural-isomorphisms-precategories</a>
<a id="4264" class="Keyword">open</a> <a id="4269" class="Keyword">import</a> <a id="4276" href="category-theory.natural-transformations-categories.html" class="Module">category-theory.natural-transformations-categories</a>
<a id="4327" class="Keyword">open</a> <a id="4332" class="Keyword">import</a> <a id="4339" href="category-theory.natural-transformations-large-precategories.html" class="Module">category-theory.natural-transformations-large-precategories</a>
<a id="4399" class="Keyword">open</a> <a id="4404" class="Keyword">import</a> <a id="4411" href="category-theory.natural-transformations-precategories.html" class="Module">category-theory.natural-transformations-precategories</a>
<a id="4465" class="Keyword">open</a> <a id="4470" class="Keyword">import</a> <a id="4477" href="category-theory.precategories.html" class="Module">category-theory.precategories</a>
<a id="4507" class="Keyword">open</a> <a id="4512" class="Keyword">import</a> <a id="4519" href="category-theory.slice-precategories.html" class="Module">category-theory.slice-precategories</a>
<a id="4555" class="Keyword">open</a> <a id="4560" class="Keyword">import</a> <a id="4567" href="category-theory.terminal-objects-precategories.html" class="Module">category-theory.terminal-objects-precategories</a>
</pre>
## Commutative algebra

<pre class="Agda"><a id="4651" class="Keyword">open</a> <a id="4656" class="Keyword">import</a> <a id="4663" href="commutative-algebra.html" class="Module">commutative-algebra</a>
<a id="4683" class="Keyword">open</a> <a id="4688" class="Keyword">import</a> <a id="4695" href="commutative-algebra.commutative-rings.html" class="Module">commutative-algebra.commutative-rings</a>
<a id="4733" class="Keyword">open</a> <a id="4738" class="Keyword">import</a> <a id="4745" href="commutative-algebra.discrete-fields.html" class="Module">commutative-algebra.discrete-fields</a>
<a id="4781" class="Keyword">open</a> <a id="4786" class="Keyword">import</a> <a id="4793" href="commutative-algebra.eisenstein-integers.html" class="Module">commutative-algebra.eisenstein-integers</a>
<a id="4833" class="Keyword">open</a> <a id="4838" class="Keyword">import</a> <a id="4845" href="commutative-algebra.gaussian-integers.html" class="Module">commutative-algebra.gaussian-integers</a>
<a id="4883" class="Keyword">open</a> <a id="4888" class="Keyword">import</a> <a id="4895" href="commutative-algebra.homomorphisms-commutative-rings.html" class="Module">commutative-algebra.homomorphisms-commutative-rings</a>
<a id="4947" class="Keyword">open</a> <a id="4952" class="Keyword">import</a> <a id="4959" href="commutative-algebra.ideals-commutative-rings.html" class="Module">commutative-algebra.ideals-commutative-rings</a>
<a id="5004" class="Keyword">open</a> <a id="5009" class="Keyword">import</a> <a id="5016" href="commutative-algebra.isomorphisms-commutative-rings.html" class="Module">commutative-algebra.isomorphisms-commutative-rings</a>
</pre>
## Elementary number theory

<pre class="Agda"><a id="5109" class="Keyword">open</a> <a id="5114" class="Keyword">import</a> <a id="5121" href="elementary-number-theory.html" class="Module">elementary-number-theory</a>
<a id="5146" class="Keyword">open</a> <a id="5151" class="Keyword">import</a> <a id="5158" href="elementary-number-theory.absolute-value-integers.html" class="Module">elementary-number-theory.absolute-value-integers</a>
<a id="5207" class="Keyword">open</a> <a id="5212" class="Keyword">import</a> <a id="5219" href="elementary-number-theory.addition-integers.html" class="Module">elementary-number-theory.addition-integers</a>
<a id="5262" class="Keyword">open</a> <a id="5267" class="Keyword">import</a> <a id="5274" href="elementary-number-theory.addition-natural-numbers.html" class="Module">elementary-number-theory.addition-natural-numbers</a>
<a id="5324" class="Keyword">open</a> <a id="5329" class="Keyword">import</a> <a id="5336" href="elementary-number-theory.arithmetic-functions.html" class="Module">elementary-number-theory.arithmetic-functions</a>
<a id="5382" class="Keyword">open</a> <a id="5387" class="Keyword">import</a> <a id="5394" href="elementary-number-theory.binomial-coefficients.html" class="Module">elementary-number-theory.binomial-coefficients</a>
<a id="5441" class="Keyword">open</a> <a id="5446" class="Keyword">import</a> <a id="5453" href="elementary-number-theory.bounded-sums-arithmetic-functions.html" class="Module">elementary-number-theory.bounded-sums-arithmetic-functions</a>
<a id="5512" class="Keyword">open</a> <a id="5517" class="Keyword">import</a> <a id="5524" href="elementary-number-theory.catalan-numbers.html" class="Module">elementary-number-theory.catalan-numbers</a>
<a id="5565" class="Keyword">open</a> <a id="5570" class="Keyword">import</a> <a id="5577" href="elementary-number-theory.collatz-bijection.html" class="Module">elementary-number-theory.collatz-bijection</a>
<a id="5620" class="Keyword">open</a> <a id="5625" class="Keyword">import</a> <a id="5632" href="elementary-number-theory.collatz-conjecture.html" class="Module">elementary-number-theory.collatz-conjecture</a>
<a id="5676" class="Keyword">open</a> <a id="5681" class="Keyword">import</a> <a id="5688" href="elementary-number-theory.congruence-integers.html" class="Module">elementary-number-theory.congruence-integers</a>
<a id="5733" class="Keyword">open</a> <a id="5738" class="Keyword">import</a> <a id="5745" href="elementary-number-theory.congruence-natural-numbers.html" class="Module">elementary-number-theory.congruence-natural-numbers</a>
<a id="5797" class="Keyword">open</a> <a id="5802" class="Keyword">import</a> <a id="5809" href="elementary-number-theory.decidable-dependent-function-types.html" class="Module">elementary-number-theory.decidable-dependent-function-types</a>
<a id="5869" class="Keyword">open</a> <a id="5874" class="Keyword">import</a> <a id="5881" href="elementary-number-theory.decidable-types.html" class="Module">elementary-number-theory.decidable-types</a>
<a id="5922" class="Keyword">open</a> <a id="5927" class="Keyword">import</a> <a id="5934" href="elementary-number-theory.difference-integers.html" class="Module">elementary-number-theory.difference-integers</a>
<a id="5979" class="Keyword">open</a> <a id="5984" class="Keyword">import</a> <a id="5991" href="elementary-number-theory.dirichlet-convolution.html" class="Module">elementary-number-theory.dirichlet-convolution</a>
<a id="6038" class="Keyword">open</a> <a id="6043" class="Keyword">import</a> <a id="6050" href="elementary-number-theory.distance-integers.html" class="Module">elementary-number-theory.distance-integers</a>
<a id="6093" class="Keyword">open</a> <a id="6098" class="Keyword">import</a> <a id="6105" href="elementary-number-theory.distance-natural-numbers.html" class="Module">elementary-number-theory.distance-natural-numbers</a>
<a id="6155" class="Keyword">open</a> <a id="6160" class="Keyword">import</a> <a id="6167" href="elementary-number-theory.divisibility-integers.html" class="Module">elementary-number-theory.divisibility-integers</a>
<a id="6214" class="Keyword">open</a> <a id="6219" class="Keyword">import</a> <a id="6226" href="elementary-number-theory.divisibility-modular-arithmetic.html" class="Module">elementary-number-theory.divisibility-modular-arithmetic</a>
<a id="6283" class="Keyword">open</a> <a id="6288" class="Keyword">import</a> <a id="6295" href="elementary-number-theory.divisibility-natural-numbers.html" class="Module">elementary-number-theory.divisibility-natural-numbers</a>
<a id="6349" class="Keyword">open</a> <a id="6354" class="Keyword">import</a> <a id="6361" href="elementary-number-theory.divisibility-standard-finite-types.html" class="Module">elementary-number-theory.divisibility-standard-finite-types</a>
<a id="6421" class="Keyword">open</a> <a id="6426" class="Keyword">import</a> <a id="6433" href="elementary-number-theory.equality-integers.html" class="Module">elementary-number-theory.equality-integers</a>
<a id="6476" class="Keyword">open</a> <a id="6481" class="Keyword">import</a> <a id="6488" href="elementary-number-theory.equality-natural-numbers.html" class="Module">elementary-number-theory.equality-natural-numbers</a>
<a id="6538" class="Keyword">open</a> <a id="6543" class="Keyword">import</a> <a id="6550" href="elementary-number-theory.euclidean-division-natural-numbers.html" class="Module">elementary-number-theory.euclidean-division-natural-numbers</a>
<a id="6610" class="Keyword">open</a> <a id="6615" class="Keyword">import</a> <a id="6622" href="elementary-number-theory.eulers-totient-function.html" class="Module">elementary-number-theory.eulers-totient-function</a>
<a id="6671" class="Keyword">open</a> <a id="6676" class="Keyword">import</a> <a id="6683" href="elementary-number-theory.exponentiation-natural-numbers.html" class="Module">elementary-number-theory.exponentiation-natural-numbers</a>
<a id="6739" class="Keyword">open</a> <a id="6744" class="Keyword">import</a> <a id="6751" href="elementary-number-theory.factorials.html" class="Module">elementary-number-theory.factorials</a>
<a id="6787" class="Keyword">open</a> <a id="6792" class="Keyword">import</a> <a id="6799" href="elementary-number-theory.falling-factorials.html" class="Module">elementary-number-theory.falling-factorials</a>
<a id="6843" class="Keyword">open</a> <a id="6848" class="Keyword">import</a> <a id="6855" href="elementary-number-theory.fibonacci-sequence.html" class="Module">elementary-number-theory.fibonacci-sequence</a>
<a id="6899" class="Keyword">open</a> <a id="6904" class="Keyword">import</a> <a id="6911" href="elementary-number-theory.finitary-natural-numbers.html" class="Module">elementary-number-theory.finitary-natural-numbers</a>
<a id="6961" class="Keyword">open</a> <a id="6966" class="Keyword">import</a> <a id="6973" href="elementary-number-theory.finitely-cyclic-maps.html" class="Module">elementary-number-theory.finitely-cyclic-maps</a>
<a id="7019" class="Keyword">open</a> <a id="7024" class="Keyword">import</a> <a id="7031" href="elementary-number-theory.fractions.html" class="Module">elementary-number-theory.fractions</a>
<a id="7066" class="Keyword">open</a> <a id="7071" class="Keyword">import</a> <a id="7078" href="elementary-number-theory.goldbach-conjecture.html" class="Module">elementary-number-theory.goldbach-conjecture</a>
<a id="7123" class="Keyword">open</a> <a id="7128" class="Keyword">import</a> <a id="7135" href="elementary-number-theory.greatest-common-divisor-integers.html" class="Module">elementary-number-theory.greatest-common-divisor-integers</a>
<a id="7193" class="Keyword">open</a> <a id="7198" class="Keyword">import</a> <a id="7205" href="elementary-number-theory.greatest-common-divisor-natural-numbers.html" class="Module">elementary-number-theory.greatest-common-divisor-natural-numbers</a>
<a id="7270" class="Keyword">open</a> <a id="7275" class="Keyword">import</a> <a id="7282" href="elementary-number-theory.group-of-integers.html" class="Module">elementary-number-theory.group-of-integers</a>
<a id="7325" class="Keyword">open</a> <a id="7330" class="Keyword">import</a> <a id="7337" href="elementary-number-theory.groups-of-modular-arithmetic.html" class="Module">elementary-number-theory.groups-of-modular-arithmetic</a>
<a id="7391" class="Keyword">open</a> <a id="7396" class="Keyword">import</a> <a id="7403" href="elementary-number-theory.inequality-integers.html" class="Module">elementary-number-theory.inequality-integers</a>
<a id="7448" class="Keyword">open</a> <a id="7453" class="Keyword">import</a> <a id="7460" href="elementary-number-theory.inequality-natural-numbers.html" class="Module">elementary-number-theory.inequality-natural-numbers</a>
<a id="7512" class="Keyword">open</a> <a id="7517" class="Keyword">import</a> <a id="7524" href="elementary-number-theory.inequality-standard-finite-types.html" class="Module">elementary-number-theory.inequality-standard-finite-types</a>
<a id="7582" class="Keyword">open</a> <a id="7587" class="Keyword">import</a> <a id="7594" href="elementary-number-theory.infinitude-of-primes.html" class="Module">elementary-number-theory.infinitude-of-primes</a>
<a id="7640" class="Keyword">open</a> <a id="7645" class="Keyword">import</a> <a id="7652" href="elementary-number-theory.integer-partitions.html" class="Module">elementary-number-theory.integer-partitions</a>
<a id="7696" class="Keyword">open</a> <a id="7701" class="Keyword">import</a> <a id="7708" href="elementary-number-theory.integers.html" class="Module">elementary-number-theory.integers</a>
<a id="7742" class="Keyword">open</a> <a id="7747" class="Keyword">import</a> <a id="7754" href="elementary-number-theory.iterating-functions.html" class="Module">elementary-number-theory.iterating-functions</a>
<a id="7799" class="Keyword">open</a> <a id="7804" class="Keyword">import</a> <a id="7811" href="elementary-number-theory.lower-bounds-natural-numbers.html" class="Module">elementary-number-theory.lower-bounds-natural-numbers</a>
<a id="7865" class="Keyword">open</a> <a id="7870" class="Keyword">import</a> <a id="7877" href="elementary-number-theory.maximum-natural-numbers.html" class="Module">elementary-number-theory.maximum-natural-numbers</a>
<a id="7926" class="Keyword">open</a> <a id="7931" class="Keyword">import</a> <a id="7938" href="elementary-number-theory.mersenne-primes.html" class="Module">elementary-number-theory.mersenne-primes</a>
<a id="7979" class="Keyword">open</a> <a id="7984" class="Keyword">import</a> <a id="7991" href="elementary-number-theory.minimum-natural-numbers.html" class="Module">elementary-number-theory.minimum-natural-numbers</a>
<a id="8040" class="Keyword">open</a> <a id="8045" class="Keyword">import</a> <a id="8052" href="elementary-number-theory.modular-arithmetic-standard-finite-types.html" class="Module">elementary-number-theory.modular-arithmetic-standard-finite-types</a>
<a id="8118" class="Keyword">open</a> <a id="8123" class="Keyword">import</a> <a id="8130" href="elementary-number-theory.modular-arithmetic.html" class="Module">elementary-number-theory.modular-arithmetic</a>
<a id="8174" class="Keyword">open</a> <a id="8179" class="Keyword">import</a> <a id="8186" href="elementary-number-theory.multiplication-integers.html" class="Module">elementary-number-theory.multiplication-integers</a>
<a id="8235" class="Keyword">open</a> <a id="8240" class="Keyword">import</a> <a id="8247" href="elementary-number-theory.multiplication-natural-numbers.html" class="Module">elementary-number-theory.multiplication-natural-numbers</a>
<a id="8303" class="Keyword">open</a> <a id="8308" class="Keyword">import</a> <a id="8315" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a>
<a id="8356" class="Keyword">open</a> <a id="8361" class="Keyword">import</a> <a id="8368" href="elementary-number-theory.nonzero-natural-numbers.html" class="Module">elementary-number-theory.nonzero-natural-numbers</a>
<a id="8417" class="Keyword">open</a> <a id="8422" class="Keyword">import</a> <a id="8429" href="elementary-number-theory.ordinal-induction-natural-numbers.html" class="Module">elementary-number-theory.ordinal-induction-natural-numbers</a>
<a id="8488" class="Keyword">open</a> <a id="8493" class="Keyword">import</a> <a id="8500" href="elementary-number-theory.prime-numbers.html" class="Module">elementary-number-theory.prime-numbers</a>
<a id="8539" class="Keyword">open</a> <a id="8544" class="Keyword">import</a> <a id="8551" href="elementary-number-theory.products-of-natural-numbers.html" class="Module">elementary-number-theory.products-of-natural-numbers</a>
<a id="8604" class="Keyword">open</a> <a id="8609" class="Keyword">import</a> <a id="8616" href="elementary-number-theory.proper-divisors-natural-numbers.html" class="Module">elementary-number-theory.proper-divisors-natural-numbers</a>
<a id="8673" class="Keyword">open</a> <a id="8678" class="Keyword">import</a> <a id="8685" href="elementary-number-theory.rational-numbers.html" class="Module">elementary-number-theory.rational-numbers</a>
<a id="8727" class="Keyword">open</a> <a id="8732" class="Keyword">import</a> <a id="8739" href="elementary-number-theory.relatively-prime-integers.html" class="Module">elementary-number-theory.relatively-prime-integers</a>
<a id="8790" class="Keyword">open</a> <a id="8795" class="Keyword">import</a> <a id="8802" href="elementary-number-theory.relatively-prime-natural-numbers.html" class="Module">elementary-number-theory.relatively-prime-natural-numbers</a>
<a id="8860" class="Keyword">open</a> <a id="8865" class="Keyword">import</a> <a id="8872" href="elementary-number-theory.repeating-element-standard-finite-type.html" class="Module">elementary-number-theory.repeating-element-standard-finite-type</a>
<a id="8936" class="Keyword">open</a> <a id="8941" class="Keyword">import</a> <a id="8948" href="elementary-number-theory.retracts-of-natural-numbers.html" class="Module">elementary-number-theory.retracts-of-natural-numbers</a>
<a id="9001" class="Keyword">open</a> <a id="9006" class="Keyword">import</a> <a id="9013" href="elementary-number-theory.square-free-natural-numbers.html" class="Module">elementary-number-theory.square-free-natural-numbers</a>
<a id="9066" class="Keyword">open</a> <a id="9071" class="Keyword">import</a> <a id="9078" href="elementary-number-theory.stirling-numbers-of-the-second-kind.html" class="Module">elementary-number-theory.stirling-numbers-of-the-second-kind</a>
<a id="9139" class="Keyword">open</a> <a id="9144" class="Keyword">import</a> <a id="9151" href="elementary-number-theory.strong-induction-natural-numbers.html" class="Module">elementary-number-theory.strong-induction-natural-numbers</a>
<a id="9209" class="Keyword">open</a> <a id="9214" class="Keyword">import</a> <a id="9221" href="elementary-number-theory.sums-of-natural-numbers.html" class="Module">elementary-number-theory.sums-of-natural-numbers</a>
<a id="9270" class="Keyword">open</a> <a id="9275" class="Keyword">import</a> <a id="9282" href="elementary-number-theory.telephone-numbers.html" class="Module">elementary-number-theory.telephone-numbers</a>
<a id="9325" class="Keyword">open</a> <a id="9330" class="Keyword">import</a> <a id="9337" href="elementary-number-theory.triangular-numbers.html" class="Module">elementary-number-theory.triangular-numbers</a>
<a id="9381" class="Keyword">open</a> <a id="9386" class="Keyword">import</a> <a id="9393" href="elementary-number-theory.twin-prime-conjecture.html" class="Module">elementary-number-theory.twin-prime-conjecture</a>
<a id="9440" class="Keyword">open</a> <a id="9445" class="Keyword">import</a> <a id="9452" href="elementary-number-theory.unit-elements-standard-finite-types.html" class="Module">elementary-number-theory.unit-elements-standard-finite-types</a>
<a id="9513" class="Keyword">open</a> <a id="9518" class="Keyword">import</a> <a id="9525" href="elementary-number-theory.unit-similarity-standard-finite-types.html" class="Module">elementary-number-theory.unit-similarity-standard-finite-types</a>
<a id="9588" class="Keyword">open</a> <a id="9593" class="Keyword">import</a> <a id="9600" href="elementary-number-theory.universal-property-natural-numbers.html" class="Module">elementary-number-theory.universal-property-natural-numbers</a>
<a id="9660" class="Keyword">open</a> <a id="9665" class="Keyword">import</a> <a id="9672" href="elementary-number-theory.upper-bounds-natural-numbers.html" class="Module">elementary-number-theory.upper-bounds-natural-numbers</a>
<a id="9726" class="Keyword">open</a> <a id="9731" class="Keyword">import</a> <a id="9738" href="elementary-number-theory.well-ordering-principle-natural-numbers.html" class="Module">elementary-number-theory.well-ordering-principle-natural-numbers</a>
<a id="9803" class="Keyword">open</a> <a id="9808" class="Keyword">import</a> <a id="9815" href="elementary-number-theory.well-ordering-principle-standard-finite-types.html" class="Module">elementary-number-theory.well-ordering-principle-standard-finite-types</a>
</pre>
## Finite group theory

<pre class="Agda"><a id="9923" class="Keyword">open</a> <a id="9928" class="Keyword">import</a> <a id="9935" href="finite-group-theory.html" class="Module">finite-group-theory</a>
<a id="9955" class="Keyword">open</a> <a id="9960" class="Keyword">import</a> <a id="9967" href="finite-group-theory.abstract-quaternion-group.html" class="Module">finite-group-theory.abstract-quaternion-group</a>
<a id="10013" class="Keyword">open</a> <a id="10018" class="Keyword">import</a> <a id="10025" href="finite-group-theory.concrete-quaternion-group.html" class="Module">finite-group-theory.concrete-quaternion-group</a>
<a id="10071" class="Keyword">open</a> <a id="10076" class="Keyword">import</a> <a id="10083" href="finite-group-theory.finite-groups.html" class="Module">finite-group-theory.finite-groups</a>
<a id="10117" class="Keyword">open</a> <a id="10122" class="Keyword">import</a> <a id="10129" href="finite-group-theory.finite-monoids.html" class="Module">finite-group-theory.finite-monoids</a>
<a id="10164" class="Keyword">open</a> <a id="10169" class="Keyword">import</a> <a id="10176" href="finite-group-theory.finite-semigroups.html" class="Module">finite-group-theory.finite-semigroups</a>
<a id="10214" class="Keyword">open</a> <a id="10219" class="Keyword">import</a> <a id="10226" href="finite-group-theory.groups-of-order-2.html" class="Module">finite-group-theory.groups-of-order-2</a>
<a id="10264" class="Keyword">open</a> <a id="10269" class="Keyword">import</a> <a id="10276" href="finite-group-theory.orbits-permutations.html" class="Module">finite-group-theory.orbits-permutations</a>
<a id="10316" class="Keyword">open</a> <a id="10321" class="Keyword">import</a> <a id="10328" href="finite-group-theory.permutations.html" class="Module">finite-group-theory.permutations</a>
<a id="10361" class="Keyword">open</a> <a id="10366" class="Keyword">import</a> <a id="10373" href="finite-group-theory.sign-homomorphism.html" class="Module">finite-group-theory.sign-homomorphism</a>
<a id="10411" class="Keyword">open</a> <a id="10416" class="Keyword">import</a> <a id="10423" href="finite-group-theory.transpositions.html" class="Module">finite-group-theory.transpositions</a>
</pre>
## Foundation

<pre class="Agda"><a id="10486" class="Keyword">open</a> <a id="10491" class="Keyword">import</a> <a id="10498" href="foundation.html" class="Module">foundation</a>
<a id="10509" class="Keyword">open</a> <a id="10514" class="Keyword">import</a> <a id="10521" href="foundation.0-maps.html" class="Module">foundation.0-maps</a>
<a id="10539" class="Keyword">open</a> <a id="10544" class="Keyword">import</a> <a id="10551" href="foundation.1-types.html" class="Module">foundation.1-types</a>
<a id="10570" class="Keyword">open</a> <a id="10575" class="Keyword">import</a> <a id="10582" href="foundation.2-types.html" class="Module">foundation.2-types</a>
<a id="10601" class="Keyword">open</a> <a id="10606" class="Keyword">import</a> <a id="10613" href="foundation.algebras-polynomial-endofunctors.html" class="Module">foundation.algebras-polynomial-endofunctors</a>
<a id="10657" class="Keyword">open</a> <a id="10662" class="Keyword">import</a> <a id="10669" href="foundation.automorphisms.html" class="Module">foundation.automorphisms</a>
<a id="10694" class="Keyword">open</a> <a id="10699" class="Keyword">import</a> <a id="10706" href="foundation.axiom-of-choice.html" class="Module">foundation.axiom-of-choice</a>
<a id="10733" class="Keyword">open</a> <a id="10738" class="Keyword">import</a> <a id="10745" href="foundation.binary-embeddings.html" class="Module">foundation.binary-embeddings</a>
<a id="10774" class="Keyword">open</a> <a id="10779" class="Keyword">import</a> <a id="10786" href="foundation.binary-equivalences.html" class="Module">foundation.binary-equivalences</a>
<a id="10817" class="Keyword">open</a> <a id="10822" class="Keyword">import</a> <a id="10829" href="foundation.binary-equivalences-unordered-pairs-of-types.html" class="Module">foundation.binary-equivalences-unordered-pairs-of-types</a>
<a id="10885" class="Keyword">open</a> <a id="10890" class="Keyword">import</a> <a id="10897" href="foundation.binary-operations-unordered-pairs-of-types.html" class="Module">foundation.binary-operations-unordered-pairs-of-types</a>
<a id="10951" class="Keyword">open</a> <a id="10956" class="Keyword">import</a> <a id="10963" href="foundation.binary-relations.html" class="Module">foundation.binary-relations</a>
<a id="10991" class="Keyword">open</a> <a id="10996" class="Keyword">import</a> <a id="11003" href="foundation.boolean-reflection.html" class="Module">foundation.boolean-reflection</a>
<a id="11033" class="Keyword">open</a> <a id="11038" class="Keyword">import</a> <a id="11045" href="foundation.booleans.html" class="Module">foundation.booleans</a>
<a id="11065" class="Keyword">open</a> <a id="11070" class="Keyword">import</a> <a id="11077" href="foundation.cantors-diagonal-argument.html" class="Module">foundation.cantors-diagonal-argument</a>
<a id="11114" class="Keyword">open</a> <a id="11119" class="Keyword">import</a> <a id="11126" href="foundation.cartesian-product-types.html" class="Module">foundation.cartesian-product-types</a>
<a id="11161" class="Keyword">open</a> <a id="11166" class="Keyword">import</a> <a id="11173" href="foundation.choice-of-representatives-equivalence-relation.html" class="Module">foundation.choice-of-representatives-equivalence-relation</a>
<a id="11231" class="Keyword">open</a> <a id="11236" class="Keyword">import</a> <a id="11243" href="foundation.coherently-invertible-maps.html" class="Module">foundation.coherently-invertible-maps</a>
<a id="11281" class="Keyword">open</a> <a id="11286" class="Keyword">import</a> <a id="11293" href="foundation.commutative-operations.html" class="Module">foundation.commutative-operations</a>
<a id="11327" class="Keyword">open</a> <a id="11332" class="Keyword">import</a> <a id="11339" href="foundation.commuting-squares.html" class="Module">foundation.commuting-squares</a>
<a id="11368" class="Keyword">open</a> <a id="11373" class="Keyword">import</a> <a id="11380" href="foundation.complements.html" class="Module">foundation.complements</a>
<a id="11403" class="Keyword">open</a> <a id="11408" class="Keyword">import</a> <a id="11415" href="foundation.conjunction.html" class="Module">foundation.conjunction</a>
<a id="11438" class="Keyword">open</a> <a id="11443" class="Keyword">import</a> <a id="11450" href="foundation.connected-components-universes.html" class="Module">foundation.connected-components-universes</a>
<a id="11492" class="Keyword">open</a> <a id="11497" class="Keyword">import</a> <a id="11504" href="foundation.connected-components.html" class="Module">foundation.connected-components</a>
<a id="11536" class="Keyword">open</a> <a id="11541" class="Keyword">import</a> <a id="11548" href="foundation.connected-types.html" class="Module">foundation.connected-types</a>
<a id="11575" class="Keyword">open</a> <a id="11580" class="Keyword">import</a> <a id="11587" href="foundation.constant-maps.html" class="Module">foundation.constant-maps</a>
<a id="11612" class="Keyword">open</a> <a id="11617" class="Keyword">import</a> <a id="11624" href="foundation.contractible-maps.html" class="Module">foundation.contractible-maps</a>
<a id="11653" class="Keyword">open</a> <a id="11658" class="Keyword">import</a> <a id="11665" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a>
<a id="11695" class="Keyword">open</a> <a id="11700" class="Keyword">import</a> <a id="11707" href="foundation.coproduct-types.html" class="Module">foundation.coproduct-types</a>
<a id="11734" class="Keyword">open</a> <a id="11739" class="Keyword">import</a> <a id="11746" href="foundation.coslice.html" class="Module">foundation.coslice</a>
<a id="11765" class="Keyword">open</a> <a id="11770" class="Keyword">import</a> <a id="11777" href="foundation.decidable-dependent-function-types.html" class="Module">foundation.decidable-dependent-function-types</a>
<a id="11823" class="Keyword">open</a> <a id="11828" class="Keyword">import</a> <a id="11835" href="foundation.decidable-dependent-pair-types.html" class="Module">foundation.decidable-dependent-pair-types</a>
<a id="11877" class="Keyword">open</a> <a id="11882" class="Keyword">import</a> <a id="11889" href="foundation.decidable-embeddings.html" class="Module">foundation.decidable-embeddings</a>
<a id="11921" class="Keyword">open</a> <a id="11926" class="Keyword">import</a> <a id="11933" href="foundation.decidable-equality.html" class="Module">foundation.decidable-equality</a>
<a id="11963" class="Keyword">open</a> <a id="11968" class="Keyword">import</a> <a id="11975" href="foundation.decidable-maps.html" class="Module">foundation.decidable-maps</a>
<a id="12001" class="Keyword">open</a> <a id="12006" class="Keyword">import</a> <a id="12013" href="foundation.decidable-propositions.html" class="Module">foundation.decidable-propositions</a>
<a id="12047" class="Keyword">open</a> <a id="12052" class="Keyword">import</a> <a id="12059" href="foundation.decidable-subtypes.html" class="Module">foundation.decidable-subtypes</a>
<a id="12089" class="Keyword">open</a> <a id="12094" class="Keyword">import</a> <a id="12101" href="foundation.decidable-types.html" class="Module">foundation.decidable-types</a>
<a id="12128" class="Keyword">open</a> <a id="12133" class="Keyword">import</a> <a id="12140" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a>
<a id="12172" class="Keyword">open</a> <a id="12177" class="Keyword">import</a> <a id="12184" href="foundation.diagonal-maps-of-types.html" class="Module">foundation.diagonal-maps-of-types</a>
<a id="12218" class="Keyword">open</a> <a id="12223" class="Keyword">import</a> <a id="12230" href="foundation.disjunction.html" class="Module">foundation.disjunction</a>
<a id="12253" class="Keyword">open</a> <a id="12258" class="Keyword">import</a> <a id="12265" href="foundation.distributivity-of-dependent-functions-over-coproduct-types.html" class="Module">foundation.distributivity-of-dependent-functions-over-coproduct-types</a>
<a id="12335" class="Keyword">open</a> <a id="12340" class="Keyword">import</a> <a id="12347" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html" class="Module">foundation.distributivity-of-dependent-functions-over-dependent-pairs</a>
<a id="12417" class="Keyword">open</a> <a id="12422" class="Keyword">import</a> <a id="12429" href="foundation.double-negation.html" class="Module">foundation.double-negation</a>
<a id="12456" class="Keyword">open</a> <a id="12461" class="Keyword">import</a> <a id="12468" href="foundation.double-powersets.html" class="Module">foundation.double-powersets</a>
<a id="12496" class="Keyword">open</a> <a id="12501" class="Keyword">import</a> <a id="12508" href="foundation.dubuc-penon-compact-types.html" class="Module">foundation.dubuc-penon-compact-types</a>
<a id="12545" class="Keyword">open</a> <a id="12550" class="Keyword">import</a> <a id="12557" href="foundation.effective-maps-equivalence-relations.html" class="Module">foundation.effective-maps-equivalence-relations</a>
<a id="12605" class="Keyword">open</a> <a id="12610" class="Keyword">import</a> <a id="12617" href="foundation.elementhood-relation-w-types.html" class="Module">foundation.elementhood-relation-w-types</a>
<a id="12657" class="Keyword">open</a> <a id="12662" class="Keyword">import</a> <a id="12669" href="foundation.embeddings.html" class="Module">foundation.embeddings</a>
<a id="12691" class="Keyword">open</a> <a id="12696" class="Keyword">import</a> <a id="12703" href="foundation.empty-types.html" class="Module">foundation.empty-types</a>
<a id="12726" class="Keyword">open</a> <a id="12731" class="Keyword">import</a> <a id="12738" href="foundation.epimorphisms-with-respect-to-sets.html" class="Module">foundation.epimorphisms-with-respect-to-sets</a>
<a id="12783" class="Keyword">open</a> <a id="12788" class="Keyword">import</a> <a id="12795" href="foundation.equality-cartesian-product-types.html" class="Module">foundation.equality-cartesian-product-types</a>
<a id="12839" class="Keyword">open</a> <a id="12844" class="Keyword">import</a> <a id="12851" href="foundation.equality-coproduct-types.html" class="Module">foundation.equality-coproduct-types</a>
<a id="12887" class="Keyword">open</a> <a id="12892" class="Keyword">import</a> <a id="12899" href="foundation.equality-dependent-function-types.html" class="Module">foundation.equality-dependent-function-types</a>
<a id="12944" class="Keyword">open</a> <a id="12949" class="Keyword">import</a> <a id="12956" href="foundation.equality-dependent-pair-types.html" class="Module">foundation.equality-dependent-pair-types</a>
<a id="12997" class="Keyword">open</a> <a id="13002" class="Keyword">import</a> <a id="13009" href="foundation.equality-fibers-of-maps.html" class="Module">foundation.equality-fibers-of-maps</a>
<a id="13044" class="Keyword">open</a> <a id="13049" class="Keyword">import</a> <a id="13056" href="foundation.equivalence-classes.html" class="Module">foundation.equivalence-classes</a>
<a id="13087" class="Keyword">open</a> <a id="13092" class="Keyword">import</a> <a id="13099" href="foundation.equivalence-induction.html" class="Module">foundation.equivalence-induction</a>
<a id="13132" class="Keyword">open</a> <a id="13137" class="Keyword">import</a> <a id="13144" href="foundation.equivalence-relations.html" class="Module">foundation.equivalence-relations</a>
<a id="13177" class="Keyword">open</a> <a id="13182" class="Keyword">import</a> <a id="13189" href="foundation.equivalences-maybe.html" class="Module">foundation.equivalences-maybe</a>
<a id="13219" class="Keyword">open</a> <a id="13224" class="Keyword">import</a> <a id="13231" href="foundation.equivalences.html" class="Module">foundation.equivalences</a>
<a id="13255" class="Keyword">open</a> <a id="13260" class="Keyword">import</a> <a id="13267" href="foundation.existential-quantification.html" class="Module">foundation.existential-quantification</a>
<a id="13305" class="Keyword">open</a> <a id="13310" class="Keyword">import</a> <a id="13317" href="foundation.extensional-w-types.html" class="Module">foundation.extensional-w-types</a>
<a id="13348" class="Keyword">open</a> <a id="13353" class="Keyword">import</a> <a id="13360" href="foundation.faithful-maps.html" class="Module">foundation.faithful-maps</a>
<a id="13385" class="Keyword">open</a> <a id="13390" class="Keyword">import</a> <a id="13397" href="foundation.fiber-inclusions.html" class="Module">foundation.fiber-inclusions</a>
<a id="13425" class="Keyword">open</a> <a id="13430" class="Keyword">import</a> <a id="13437" href="foundation.fibered-maps.html" class="Module">foundation.fibered-maps</a>
<a id="13461" class="Keyword">open</a> <a id="13466" class="Keyword">import</a> <a id="13473" href="foundation.fibers-of-maps.html" class="Module">foundation.fibers-of-maps</a>
<a id="13499" class="Keyword">open</a> <a id="13504" class="Keyword">import</a> <a id="13511" href="foundation.function-extensionality.html" class="Module">foundation.function-extensionality</a>
<a id="13546" class="Keyword">open</a> <a id="13551" class="Keyword">import</a> <a id="13558" href="foundation.functions.html" class="Module">foundation.functions</a>
<a id="13579" class="Keyword">open</a> <a id="13584" class="Keyword">import</a> <a id="13591" href="foundation.functoriality-cartesian-product-types.html" class="Module">foundation.functoriality-cartesian-product-types</a>
<a id="13640" class="Keyword">open</a> <a id="13645" class="Keyword">import</a> <a id="13652" href="foundation.functoriality-coproduct-types.html" class="Module">foundation.functoriality-coproduct-types</a>
<a id="13693" class="Keyword">open</a> <a id="13698" class="Keyword">import</a> <a id="13705" href="foundation.functoriality-dependent-function-types.html" class="Module">foundation.functoriality-dependent-function-types</a>
<a id="13755" class="Keyword">open</a> <a id="13760" class="Keyword">import</a> <a id="13767" href="foundation.functoriality-dependent-pair-types.html" class="Module">foundation.functoriality-dependent-pair-types</a>
<a id="13813" class="Keyword">open</a> <a id="13818" class="Keyword">import</a> <a id="13825" href="foundation.functoriality-function-types.html" class="Module">foundation.functoriality-function-types</a>
<a id="13865" class="Keyword">open</a> <a id="13870" class="Keyword">import</a> <a id="13877" href="foundation.functoriality-propositional-truncation.html" class="Module">foundation.functoriality-propositional-truncation</a>
<a id="13927" class="Keyword">open</a> <a id="13932" class="Keyword">import</a> <a id="13939" href="foundation.functoriality-set-quotients.html" class="Module">foundation.functoriality-set-quotients</a>
<a id="13978" class="Keyword">open</a> <a id="13983" class="Keyword">import</a> <a id="13990" href="foundation.functoriality-set-truncation.html" class="Module">foundation.functoriality-set-truncation</a>
<a id="14030" class="Keyword">open</a> <a id="14035" class="Keyword">import</a> <a id="14042" href="foundation.functoriality-w-types.html" class="Module">foundation.functoriality-w-types</a>
<a id="14075" class="Keyword">open</a> <a id="14080" class="Keyword">import</a> <a id="14087" href="foundation.fundamental-theorem-of-identity-types.html" class="Module">foundation.fundamental-theorem-of-identity-types</a>
<a id="14136" class="Keyword">open</a> <a id="14141" class="Keyword">import</a> <a id="14148" href="foundation.global-choice.html" class="Module">foundation.global-choice</a>
<a id="14173" class="Keyword">open</a> <a id="14178" class="Keyword">import</a> <a id="14185" href="foundation.hilberts-epsilon-operators.html" class="Module">foundation.hilberts-epsilon-operators</a>
<a id="14223" class="Keyword">open</a> <a id="14228" class="Keyword">import</a> <a id="14235" href="foundation.homotopies.html" class="Module">foundation.homotopies</a>
<a id="14257" class="Keyword">open</a> <a id="14262" class="Keyword">import</a> <a id="14269" href="foundation.identity-systems.html" class="Module">foundation.identity-systems</a>
<a id="14297" class="Keyword">open</a> <a id="14302" class="Keyword">import</a> <a id="14309" href="foundation.identity-types.html" class="Module">foundation.identity-types</a>
<a id="14335" class="Keyword">open</a> <a id="14340" class="Keyword">import</a> <a id="14347" href="foundation.images.html" class="Module">foundation.images</a>
<a id="14365" class="Keyword">open</a> <a id="14370" class="Keyword">import</a> <a id="14377" href="foundation.impredicative-encodings.html" class="Module">foundation.impredicative-encodings</a>
<a id="14412" class="Keyword">open</a> <a id="14417" class="Keyword">import</a> <a id="14424" href="foundation.indexed-w-types.html" class="Module">foundation.indexed-w-types</a>
<a id="14451" class="Keyword">open</a> <a id="14456" class="Keyword">import</a> <a id="14463" href="foundation.induction-principle-propositional-truncation.html" class="Module">foundation.induction-principle-propositional-truncation</a>
<a id="14519" class="Keyword">open</a> <a id="14524" class="Keyword">import</a> <a id="14531" href="foundation.induction-w-types.html" class="Module">foundation.induction-w-types</a>
<a id="14560" class="Keyword">open</a> <a id="14565" class="Keyword">import</a> <a id="14572" href="foundation.inequality-w-types.html" class="Module">foundation.inequality-w-types</a>
<a id="14602" class="Keyword">open</a> <a id="14607" class="Keyword">import</a> <a id="14614" href="foundation.inhabited-types.html" class="Module">foundation.inhabited-types</a>
<a id="14641" class="Keyword">open</a> <a id="14646" class="Keyword">import</a> <a id="14653" href="foundation.injective-maps.html" class="Module">foundation.injective-maps</a>
<a id="14679" class="Keyword">open</a> <a id="14684" class="Keyword">import</a> <a id="14691" href="foundation.interchange-law.html" class="Module">foundation.interchange-law</a>
<a id="14718" class="Keyword">open</a> <a id="14723" class="Keyword">import</a> <a id="14730" href="foundation.intersection.html" class="Module">foundation.intersection</a>
<a id="14754" class="Keyword">open</a> <a id="14759" class="Keyword">import</a> <a id="14766" href="foundation.involutions.html" class="Module">foundation.involutions</a>
<a id="14789" class="Keyword">open</a> <a id="14794" class="Keyword">import</a> <a id="14801" href="foundation.isolated-points.html" class="Module">foundation.isolated-points</a>
<a id="14828" class="Keyword">open</a> <a id="14833" class="Keyword">import</a> <a id="14840" href="foundation.isomorphisms-of-sets.html" class="Module">foundation.isomorphisms-of-sets</a>
<a id="14872" class="Keyword">open</a> <a id="14877" class="Keyword">import</a> <a id="14884" href="foundation.law-of-excluded-middle.html" class="Module">foundation.law-of-excluded-middle</a>
<a id="14918" class="Keyword">open</a> <a id="14923" class="Keyword">import</a> <a id="14930" href="foundation.lawveres-fixed-point-theorem.html" class="Module">foundation.lawveres-fixed-point-theorem</a>
<a id="14970" class="Keyword">open</a> <a id="14975" class="Keyword">import</a> <a id="14982" href="foundation.locally-small-types.html" class="Module">foundation.locally-small-types</a>
<a id="15013" class="Keyword">open</a> <a id="15018" class="Keyword">import</a> <a id="15025" href="foundation.logical-equivalences.html" class="Module">foundation.logical-equivalences</a>
<a id="15057" class="Keyword">open</a> <a id="15062" class="Keyword">import</a> <a id="15069" href="foundation.lower-types-w-types.html" class="Module">foundation.lower-types-w-types</a>
<a id="15100" class="Keyword">open</a> <a id="15105" class="Keyword">import</a> <a id="15112" href="foundation.maybe.html" class="Module">foundation.maybe</a>
<a id="15129" class="Keyword">open</a> <a id="15134" class="Keyword">import</a> <a id="15141" href="foundation.mere-equality.html" class="Module">foundation.mere-equality</a>
<a id="15166" class="Keyword">open</a> <a id="15171" class="Keyword">import</a> <a id="15178" href="foundation.mere-equivalences.html" class="Module">foundation.mere-equivalences</a>
<a id="15207" class="Keyword">open</a> <a id="15212" class="Keyword">import</a> <a id="15219" href="foundation.monomorphisms.html" class="Module">foundation.monomorphisms</a>
<a id="15244" class="Keyword">open</a> <a id="15249" class="Keyword">import</a> <a id="15256" href="foundation.multisets.html" class="Module">foundation.multisets</a>
<a id="15277" class="Keyword">open</a> <a id="15282" class="Keyword">import</a> <a id="15289" href="foundation.multisubsets.html" class="Module">foundation.multisubsets</a>
<a id="15313" class="Keyword">open</a> <a id="15318" class="Keyword">import</a> <a id="15325" href="foundation.negation.html" class="Module">foundation.negation</a>
<a id="15345" class="Keyword">open</a> <a id="15350" class="Keyword">import</a> <a id="15357" href="foundation.non-contractible-types.html" class="Module">foundation.non-contractible-types</a>
<a id="15391" class="Keyword">open</a> <a id="15396" class="Keyword">import</a> <a id="15403" href="foundation.pairs-of-distinct-elements.html" class="Module">foundation.pairs-of-distinct-elements</a>
<a id="15441" class="Keyword">open</a> <a id="15446" class="Keyword">import</a> <a id="15453" href="foundation.path-algebra.html" class="Module">foundation.path-algebra</a>
<a id="15477" class="Keyword">open</a> <a id="15482" class="Keyword">import</a> <a id="15489" href="foundation.path-split-maps.html" class="Module">foundation.path-split-maps</a>
<a id="15516" class="Keyword">open</a> <a id="15521" class="Keyword">import</a> <a id="15528" href="foundation.polynomial-endofunctors.html" class="Module">foundation.polynomial-endofunctors</a>
<a id="15563" class="Keyword">open</a> <a id="15568" class="Keyword">import</a> <a id="15575" href="foundation.powersets.html" class="Module">foundation.powersets</a>
<a id="15596" class="Keyword">open</a> <a id="15601" class="Keyword">import</a> <a id="15608" href="foundation.principle-of-omniscience.html" class="Module">foundation.principle-of-omniscience</a>
<a id="15644" class="Keyword">open</a> <a id="15649" class="Keyword">import</a> <a id="15656" href="foundation.products-unordered-pairs-of-types.html" class="Module">foundation.products-unordered-pairs-of-types</a>
<a id="15701" class="Keyword">open</a> <a id="15706" class="Keyword">import</a> <a id="15713" href="foundation.products-unordered-tuples-of-types.html" class="Module">foundation.products-unordered-tuples-of-types</a>
<a id="15759" class="Keyword">open</a> <a id="15764" class="Keyword">import</a> <a id="15771" href="foundation.propositional-extensionality.html" class="Module">foundation.propositional-extensionality</a>
<a id="15811" class="Keyword">open</a> <a id="15816" class="Keyword">import</a> <a id="15823" href="foundation.propositional-maps.html" class="Module">foundation.propositional-maps</a>
<a id="15853" class="Keyword">open</a> <a id="15858" class="Keyword">import</a> <a id="15865" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a>
<a id="15902" class="Keyword">open</a> <a id="15907" class="Keyword">import</a> <a id="15914" href="foundation.propositions.html" class="Module">foundation.propositions</a>
<a id="15938" class="Keyword">open</a> <a id="15943" class="Keyword">import</a> <a id="15950" href="foundation.pullbacks.html" class="Module">foundation.pullbacks</a>
<a id="15971" class="Keyword">open</a> <a id="15976" class="Keyword">import</a> <a id="15983" href="foundation.raising-universe-levels.html" class="Module">foundation.raising-universe-levels</a>
<a id="16018" class="Keyword">open</a> <a id="16023" class="Keyword">import</a> <a id="16030" href="foundation.ranks-of-elements-w-types.html" class="Module">foundation.ranks-of-elements-w-types</a>
<a id="16067" class="Keyword">open</a> <a id="16072" class="Keyword">import</a> <a id="16079" href="foundation.reflecting-maps-equivalence-relations.html" class="Module">foundation.reflecting-maps-equivalence-relations</a>
<a id="16128" class="Keyword">open</a> <a id="16133" class="Keyword">import</a> <a id="16140" href="foundation.replacement.html" class="Module">foundation.replacement</a>
<a id="16163" class="Keyword">open</a> <a id="16168" class="Keyword">import</a> <a id="16175" href="foundation.retractions.html" class="Module">foundation.retractions</a>
<a id="16198" class="Keyword">open</a> <a id="16203" class="Keyword">import</a> <a id="16210" href="foundation.russells-paradox.html" class="Module">foundation.russells-paradox</a>
<a id="16238" class="Keyword">open</a> <a id="16243" class="Keyword">import</a> <a id="16250" href="foundation.sections.html" class="Module">foundation.sections</a>
<a id="16270" class="Keyword">open</a> <a id="16275" class="Keyword">import</a> <a id="16282" href="foundation.set-presented-types.html" class="Module">foundation.set-presented-types</a>
<a id="16313" class="Keyword">open</a> <a id="16318" class="Keyword">import</a> <a id="16325" href="foundation.set-truncations.html" class="Module">foundation.set-truncations</a>
<a id="16352" class="Keyword">open</a> <a id="16357" class="Keyword">import</a> <a id="16364" href="foundation.sets.html" class="Module">foundation.sets</a>
<a id="16380" class="Keyword">open</a> <a id="16385" class="Keyword">import</a> <a id="16392" href="foundation.singleton-induction.html" class="Module">foundation.singleton-induction</a>
<a id="16423" class="Keyword">open</a> <a id="16428" class="Keyword">import</a> <a id="16435" href="foundation.slice.html" class="Module">foundation.slice</a>
<a id="16452" class="Keyword">open</a> <a id="16457" class="Keyword">import</a> <a id="16464" href="foundation.small-maps.html" class="Module">foundation.small-maps</a>
<a id="16486" class="Keyword">open</a> <a id="16491" class="Keyword">import</a> <a id="16498" href="foundation.small-multisets.html" class="Module">foundation.small-multisets</a>
<a id="16525" class="Keyword">open</a> <a id="16530" class="Keyword">import</a> <a id="16537" href="foundation.small-types.html" class="Module">foundation.small-types</a>
<a id="16560" class="Keyword">open</a> <a id="16565" class="Keyword">import</a> <a id="16572" href="foundation.small-universes.html" class="Module">foundation.small-universes</a>
<a id="16599" class="Keyword">open</a> <a id="16604" class="Keyword">import</a> <a id="16611" href="foundation.split-surjective-maps.html" class="Module">foundation.split-surjective-maps</a>
<a id="16644" class="Keyword">open</a> <a id="16649" class="Keyword">import</a> <a id="16656" href="foundation.structure-identity-principle.html" class="Module">foundation.structure-identity-principle</a>
<a id="16696" class="Keyword">open</a> <a id="16701" class="Keyword">import</a> <a id="16708" href="foundation.structure.html" class="Module">foundation.structure</a>
<a id="16729" class="Keyword">open</a> <a id="16734" class="Keyword">import</a> <a id="16741" href="foundation.subterminal-types.html" class="Module">foundation.subterminal-types</a>
<a id="16770" class="Keyword">open</a> <a id="16775" class="Keyword">import</a> <a id="16782" href="foundation.subtype-identity-principle.html" class="Module">foundation.subtype-identity-principle</a>
<a id="16820" class="Keyword">open</a> <a id="16825" class="Keyword">import</a> <a id="16832" href="foundation.subtypes.html" class="Module">foundation.subtypes</a>
<a id="16852" class="Keyword">open</a> <a id="16857" class="Keyword">import</a> <a id="16864" href="foundation.subuniverses.html" class="Module">foundation.subuniverses</a>
<a id="16888" class="Keyword">open</a> <a id="16893" class="Keyword">import</a> <a id="16900" href="foundation.surjective-maps.html" class="Module">foundation.surjective-maps</a>
<a id="16927" class="Keyword">open</a> <a id="16932" class="Keyword">import</a> <a id="16939" href="foundation.symmetric-difference.html" class="Module">foundation.symmetric-difference</a>
<a id="16971" class="Keyword">open</a> <a id="16976" class="Keyword">import</a> <a id="16983" href="foundation.truncated-equality.html" class="Module">foundation.truncated-equality</a>
<a id="17013" class="Keyword">open</a> <a id="17018" class="Keyword">import</a> <a id="17025" href="foundation.truncated-maps.html" class="Module">foundation.truncated-maps</a>
<a id="17051" class="Keyword">open</a> <a id="17056" class="Keyword">import</a> <a id="17063" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a>
<a id="17090" class="Keyword">open</a> <a id="17095" class="Keyword">import</a> <a id="17102" href="foundation.truncation-levels.html" class="Module">foundation.truncation-levels</a>
<a id="17131" class="Keyword">open</a> <a id="17136" class="Keyword">import</a> <a id="17143" href="foundation.truncations.html" class="Module">foundation.truncations</a>
<a id="17166" class="Keyword">open</a> <a id="17171" class="Keyword">import</a> <a id="17178" href="foundation.type-arithmetic-cartesian-product-types.html" class="Module">foundation.type-arithmetic-cartesian-product-types</a>
<a id="17229" class="Keyword">open</a> <a id="17234" class="Keyword">import</a> <a id="17241" href="foundation.type-arithmetic-coproduct-types.html" class="Module">foundation.type-arithmetic-coproduct-types</a>
<a id="17284" class="Keyword">open</a> <a id="17289" class="Keyword">import</a> <a id="17296" href="foundation.type-arithmetic-dependent-pair-types.html" class="Module">foundation.type-arithmetic-dependent-pair-types</a>
<a id="17344" class="Keyword">open</a> <a id="17349" class="Keyword">import</a> <a id="17356" href="foundation.type-arithmetic-empty-type.html" class="Module">foundation.type-arithmetic-empty-type</a>
<a id="17394" class="Keyword">open</a> <a id="17399" class="Keyword">import</a> <a id="17406" href="foundation.type-arithmetic-unit-type.html" class="Module">foundation.type-arithmetic-unit-type</a>
<a id="17443" class="Keyword">open</a> <a id="17448" class="Keyword">import</a> <a id="17455" href="foundation.union.html" class="Module">foundation.union</a>
<a id="17472" class="Keyword">open</a> <a id="17477" class="Keyword">import</a> <a id="17484" href="foundation.uniqueness-image.html" class="Module">foundation.uniqueness-image</a>
<a id="17512" class="Keyword">open</a> <a id="17517" class="Keyword">import</a> <a id="17524" href="foundation.uniqueness-set-quotients.html" class="Module">foundation.uniqueness-set-quotients</a>
<a id="17560" class="Keyword">open</a> <a id="17565" class="Keyword">import</a> <a id="17572" href="foundation.uniqueness-set-truncations.html" class="Module">foundation.uniqueness-set-truncations</a>
<a id="17610" class="Keyword">open</a> <a id="17615" class="Keyword">import</a> <a id="17622" href="foundation.uniqueness-truncation.html" class="Module">foundation.uniqueness-truncation</a>
<a id="17655" class="Keyword">open</a> <a id="17660" class="Keyword">import</a> <a id="17667" href="foundation.unit-type.html" class="Module">foundation.unit-type</a>
<a id="17688" class="Keyword">open</a> <a id="17693" class="Keyword">import</a> <a id="17700" href="foundation.univalence-implies-function-extensionality.html" class="Module">foundation.univalence-implies-function-extensionality</a>
<a id="17754" class="Keyword">open</a> <a id="17759" class="Keyword">import</a> <a id="17766" href="foundation.univalence.html" class="Module">foundation.univalence</a>
<a id="17788" class="Keyword">open</a> <a id="17793" class="Keyword">import</a> <a id="17800" href="foundation.univalent-type-families.html" class="Module">foundation.univalent-type-families</a>
<a id="17835" class="Keyword">open</a> <a id="17840" class="Keyword">import</a> <a id="17847" href="foundation.universal-multiset.html" class="Module">foundation.universal-multiset</a>
<a id="17877" class="Keyword">open</a> <a id="17882" class="Keyword">import</a> <a id="17889" href="foundation.universal-property-booleans.html" class="Module">foundation.universal-property-booleans</a>
<a id="17928" class="Keyword">open</a> <a id="17933" class="Keyword">import</a> <a id="17940" href="foundation.universal-property-cartesian-product-types.html" class="Module">foundation.universal-property-cartesian-product-types</a>
<a id="17994" class="Keyword">open</a> <a id="17999" class="Keyword">import</a> <a id="18006" href="foundation.universal-property-coproduct-types.html" class="Module">foundation.universal-property-coproduct-types</a>
<a id="18052" class="Keyword">open</a> <a id="18057" class="Keyword">import</a> <a id="18064" href="foundation.universal-property-dependent-pair-types.html" class="Module">foundation.universal-property-dependent-pair-types</a>
<a id="18115" class="Keyword">open</a> <a id="18120" class="Keyword">import</a> <a id="18127" href="foundation.universal-property-empty-type.html" class="Module">foundation.universal-property-empty-type</a>
<a id="18168" class="Keyword">open</a> <a id="18173" class="Keyword">import</a> <a id="18180" href="foundation.universal-property-fiber-products.html" class="Module">foundation.universal-property-fiber-products</a>
<a id="18225" class="Keyword">open</a> <a id="18230" class="Keyword">import</a> <a id="18237" href="foundation.universal-property-identity-types.html" class="Module">foundation.universal-property-identity-types</a>
<a id="18282" class="Keyword">open</a> <a id="18287" class="Keyword">import</a> <a id="18294" href="foundation.universal-property-image.html" class="Module">foundation.universal-property-image</a>
<a id="18330" class="Keyword">open</a> <a id="18335" class="Keyword">import</a> <a id="18342" href="foundation.universal-property-maybe.html" class="Module">foundation.universal-property-maybe</a>
<a id="18378" class="Keyword">open</a> <a id="18383" class="Keyword">import</a> <a id="18390" href="foundation.universal-property-propositional-truncation-into-sets.html" class="Module">foundation.universal-property-propositional-truncation-into-sets</a>
<a id="18455" class="Keyword">open</a> <a id="18460" class="Keyword">import</a> <a id="18467" href="foundation.universal-property-propositional-truncation.html" class="Module">foundation.universal-property-propositional-truncation</a>
<a id="18522" class="Keyword">open</a> <a id="18527" class="Keyword">import</a> <a id="18534" href="foundation.universal-property-pullbacks.html" class="Module">foundation.universal-property-pullbacks</a>
<a id="18574" class="Keyword">open</a> <a id="18579" class="Keyword">import</a> <a id="18586" href="foundation.universal-property-set-quotients.html" class="Module">foundation.universal-property-set-quotients</a>
<a id="18630" class="Keyword">open</a> <a id="18635" class="Keyword">import</a> <a id="18642" href="foundation.universal-property-set-truncation.html" class="Module">foundation.universal-property-set-truncation</a>
<a id="18687" class="Keyword">open</a> <a id="18692" class="Keyword">import</a> <a id="18699" href="foundation.universal-property-truncation.html" class="Module">foundation.universal-property-truncation</a>
<a id="18740" class="Keyword">open</a> <a id="18745" class="Keyword">import</a> <a id="18752" href="foundation.universal-property-unit-type.html" class="Module">foundation.universal-property-unit-type</a>
<a id="18792" class="Keyword">open</a> <a id="18797" class="Keyword">import</a> <a id="18804" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a>
<a id="18831" class="Keyword">open</a> <a id="18836" class="Keyword">import</a> <a id="18843" href="foundation.unordered-pairs.html" class="Module">foundation.unordered-pairs</a>
<a id="18870" class="Keyword">open</a> <a id="18875" class="Keyword">import</a> <a id="18882" href="foundation.unordered-pairs-of-types.html" class="Module">foundation.unordered-pairs-of-types</a>
<a id="18918" class="Keyword">open</a> <a id="18923" class="Keyword">import</a> <a id="18930" href="foundation.unordered-tuples.html" class="Module">foundation.unordered-tuples</a>
<a id="18958" class="Keyword">open</a> <a id="18963" class="Keyword">import</a> <a id="18970" href="foundation.unordered-tuples-of-types.html" class="Module">foundation.unordered-tuples-of-types</a>
<a id="19007" class="Keyword">open</a> <a id="19012" class="Keyword">import</a> <a id="19019" href="foundation.w-types.html" class="Module">foundation.w-types</a>
<a id="19038" class="Keyword">open</a> <a id="19043" class="Keyword">import</a> <a id="19050" href="foundation.weak-function-extensionality.html" class="Module">foundation.weak-function-extensionality</a>
<a id="19090" class="Keyword">open</a> <a id="19095" class="Keyword">import</a> <a id="19102" href="foundation.weakly-constant-maps.html" class="Module">foundation.weakly-constant-maps</a>
<a id="19134" class="Keyword">open</a> <a id="19139" class="Keyword">import</a> <a id="19146" href="foundation.xor.html" class="Module">foundation.xor</a>
</pre>
## Foundation Core

<pre class="Agda"><a id="19194" class="Keyword">open</a> <a id="19199" class="Keyword">import</a> <a id="19206" href="foundation-core.0-maps.html" class="Module">foundation-core.0-maps</a>
<a id="19229" class="Keyword">open</a> <a id="19234" class="Keyword">import</a> <a id="19241" href="foundation-core.1-types.html" class="Module">foundation-core.1-types</a>
<a id="19265" class="Keyword">open</a> <a id="19270" class="Keyword">import</a> <a id="19277" href="foundation-core.cartesian-product-types.html" class="Module">foundation-core.cartesian-product-types</a>
<a id="19317" class="Keyword">open</a> <a id="19322" class="Keyword">import</a> <a id="19329" href="foundation-core.coherently-invertible-maps.html" class="Module">foundation-core.coherently-invertible-maps</a>
<a id="19372" class="Keyword">open</a> <a id="19377" class="Keyword">import</a> <a id="19384" href="foundation-core.commuting-squares.html" class="Module">foundation-core.commuting-squares</a>
<a id="19418" class="Keyword">open</a> <a id="19423" class="Keyword">import</a> <a id="19430" href="foundation-core.constant-maps.html" class="Module">foundation-core.constant-maps</a>
<a id="19460" class="Keyword">open</a> <a id="19465" class="Keyword">import</a> <a id="19472" href="foundation-core.contractible-maps.html" class="Module">foundation-core.contractible-maps</a>
<a id="19506" class="Keyword">open</a> <a id="19511" class="Keyword">import</a> <a id="19518" href="foundation-core.contractible-types.html" class="Module">foundation-core.contractible-types</a>
<a id="19553" class="Keyword">open</a> <a id="19558" class="Keyword">import</a> <a id="19565" href="foundation-core.dependent-pair-types.html" class="Module">foundation-core.dependent-pair-types</a>
<a id="19602" class="Keyword">open</a> <a id="19607" class="Keyword">import</a> <a id="19614" href="foundation-core.embeddings.html" class="Module">foundation-core.embeddings</a>
<a id="19641" class="Keyword">open</a> <a id="19646" class="Keyword">import</a> <a id="19653" href="foundation-core.empty-types.html" class="Module">foundation-core.empty-types</a>
<a id="19681" class="Keyword">open</a> <a id="19686" class="Keyword">import</a> <a id="19693" href="foundation-core.equality-cartesian-product-types.html" class="Module">foundation-core.equality-cartesian-product-types</a>
<a id="19742" class="Keyword">open</a> <a id="19747" class="Keyword">import</a> <a id="19754" href="foundation-core.equality-dependent-pair-types.html" class="Module">foundation-core.equality-dependent-pair-types</a>
<a id="19800" class="Keyword">open</a> <a id="19805" class="Keyword">import</a> <a id="19812" href="foundation-core.equality-fibers-of-maps.html" class="Module">foundation-core.equality-fibers-of-maps</a>
<a id="19852" class="Keyword">open</a> <a id="19857" class="Keyword">import</a> <a id="19864" href="foundation-core.equivalence-induction.html" class="Module">foundation-core.equivalence-induction</a>
<a id="19902" class="Keyword">open</a> <a id="19907" class="Keyword">import</a> <a id="19914" href="foundation-core.equivalences.html" class="Module">foundation-core.equivalences</a>
<a id="19943" class="Keyword">open</a> <a id="19948" class="Keyword">import</a> <a id="19955" href="foundation-core.faithful-maps.html" class="Module">foundation-core.faithful-maps</a>
<a id="19985" class="Keyword">open</a> <a id="19990" class="Keyword">import</a> <a id="19997" href="foundation-core.fibers-of-maps.html" class="Module">foundation-core.fibers-of-maps</a>
<a id="20028" class="Keyword">open</a> <a id="20033" class="Keyword">import</a> <a id="20040" href="foundation-core.functions.html" class="Module">foundation-core.functions</a>
<a id="20066" class="Keyword">open</a> <a id="20071" class="Keyword">import</a> <a id="20078" href="foundation-core.functoriality-dependent-pair-types.html" class="Module">foundation-core.functoriality-dependent-pair-types</a>
<a id="20129" class="Keyword">open</a> <a id="20134" class="Keyword">import</a> <a id="20141" href="foundation-core.fundamental-theorem-of-identity-types.html" class="Module">foundation-core.fundamental-theorem-of-identity-types</a>
<a id="20195" class="Keyword">open</a> <a id="20200" class="Keyword">import</a> <a id="20207" href="foundation-core.homotopies.html" class="Module">foundation-core.homotopies</a>
<a id="20234" class="Keyword">open</a> <a id="20239" class="Keyword">import</a> <a id="20246" href="foundation-core.identity-systems.html" class="Module">foundation-core.identity-systems</a>
<a id="20279" class="Keyword">open</a> <a id="20284" class="Keyword">import</a> <a id="20291" href="foundation-core.identity-types.html" class="Module">foundation-core.identity-types</a>
<a id="20322" class="Keyword">open</a> <a id="20327" class="Keyword">import</a> <a id="20334" href="foundation-core.logical-equivalences.html" class="Module">foundation-core.logical-equivalences</a>
<a id="20371" class="Keyword">open</a> <a id="20376" class="Keyword">import</a> <a id="20383" href="foundation-core.negation.html" class="Module">foundation-core.negation</a>
<a id="20408" class="Keyword">open</a> <a id="20413" class="Keyword">import</a> <a id="20420" href="foundation-core.path-split-maps.html" class="Module">foundation-core.path-split-maps</a>
<a id="20452" class="Keyword">open</a> <a id="20457" class="Keyword">import</a> <a id="20464" href="foundation-core.propositional-maps.html" class="Module">foundation-core.propositional-maps</a>
<a id="20499" class="Keyword">open</a> <a id="20504" class="Keyword">import</a> <a id="20511" href="foundation-core.propositions.html" class="Module">foundation-core.propositions</a>
<a id="20540" class="Keyword">open</a> <a id="20545" class="Keyword">import</a> <a id="20552" href="foundation-core.retractions.html" class="Module">foundation-core.retractions</a>
<a id="20580" class="Keyword">open</a> <a id="20585" class="Keyword">import</a> <a id="20592" href="foundation-core.sections.html" class="Module">foundation-core.sections</a>
<a id="20617" class="Keyword">open</a> <a id="20622" class="Keyword">import</a> <a id="20629" href="foundation-core.sets.html" class="Module">foundation-core.sets</a>
<a id="20650" class="Keyword">open</a> <a id="20655" class="Keyword">import</a> <a id="20662" href="foundation-core.singleton-induction.html" class="Module">foundation-core.singleton-induction</a>
<a id="20698" class="Keyword">open</a> <a id="20703" class="Keyword">import</a> <a id="20710" href="foundation-core.subtype-identity-principle.html" class="Module">foundation-core.subtype-identity-principle</a>
<a id="20753" class="Keyword">open</a> <a id="20758" class="Keyword">import</a> <a id="20765" href="foundation-core.subtypes.html" class="Module">foundation-core.subtypes</a>
<a id="20790" class="Keyword">open</a> <a id="20795" class="Keyword">import</a> <a id="20802" href="foundation-core.truncated-maps.html" class="Module">foundation-core.truncated-maps</a>
<a id="20833" class="Keyword">open</a> <a id="20838" class="Keyword">import</a> <a id="20845" href="foundation-core.truncated-types.html" class="Module">foundation-core.truncated-types</a>
<a id="20877" class="Keyword">open</a> <a id="20882" class="Keyword">import</a> <a id="20889" href="foundation-core.truncation-levels.html" class="Module">foundation-core.truncation-levels</a>
<a id="20923" class="Keyword">open</a> <a id="20928" class="Keyword">import</a> <a id="20935" href="foundation-core.type-arithmetic-cartesian-product-types.html" class="Module">foundation-core.type-arithmetic-cartesian-product-types</a>
<a id="20991" class="Keyword">open</a> <a id="20996" class="Keyword">import</a> <a id="21003" href="foundation-core.type-arithmetic-dependent-pair-types.html" class="Module">foundation-core.type-arithmetic-dependent-pair-types</a>
<a id="21056" class="Keyword">open</a> <a id="21061" class="Keyword">import</a> <a id="21068" href="foundation-core.univalence.html" class="Module">foundation-core.univalence</a>
<a id="21095" class="Keyword">open</a> <a id="21100" class="Keyword">import</a> <a id="21107" href="foundation-core.universe-levels.html" class="Module">foundation-core.universe-levels</a>
</pre>
## Graph theory

<pre class="Agda"><a id="21169" class="Keyword">open</a> <a id="21174" class="Keyword">import</a> <a id="21181" href="graph-theory.html" class="Module">graph-theory</a>
<a id="21194" class="Keyword">open</a> <a id="21199" class="Keyword">import</a> <a id="21206" href="graph-theory.connected-undirected-graphs.html" class="Module">graph-theory.connected-undirected-graphs</a>
<a id="21247" class="Keyword">open</a> <a id="21252" class="Keyword">import</a> <a id="21259" href="graph-theory.directed-graphs.html" class="Module">graph-theory.directed-graphs</a>
<a id="21288" class="Keyword">open</a> <a id="21293" class="Keyword">import</a> <a id="21300" href="graph-theory.edge-coloured-undirected-graphs.html" class="Module">graph-theory.edge-coloured-undirected-graphs</a>
<a id="21345" class="Keyword">open</a> <a id="21350" class="Keyword">import</a> <a id="21357" href="graph-theory.equivalences-undirected-graphs.html" class="Module">graph-theory.equivalences-undirected-graphs</a>
<a id="21401" class="Keyword">open</a> <a id="21406" class="Keyword">import</a> <a id="21413" href="graph-theory.finite-graphs.html" class="Module">graph-theory.finite-graphs</a>
<a id="21440" class="Keyword">open</a> <a id="21445" class="Keyword">import</a> <a id="21452" href="graph-theory.incidence-undirected-graphs.html" class="Module">graph-theory.incidence-undirected-graphs</a>
<a id="21493" class="Keyword">open</a> <a id="21498" class="Keyword">import</a> <a id="21505" href="graph-theory.matchings.html" class="Module">graph-theory.matchings</a>
<a id="21528" class="Keyword">open</a> <a id="21533" class="Keyword">import</a> <a id="21540" href="graph-theory.mere-equivalences-undirected-graphs.html" class="Module">graph-theory.mere-equivalences-undirected-graphs</a>
<a id="21589" class="Keyword">open</a> <a id="21594" class="Keyword">import</a> <a id="21601" href="graph-theory.morphisms-directed-graphs.html" class="Module">graph-theory.morphisms-directed-graphs</a>
<a id="21640" class="Keyword">open</a> <a id="21645" class="Keyword">import</a> <a id="21652" href="graph-theory.morphisms-undirected-graphs.html" class="Module">graph-theory.morphisms-undirected-graphs</a>
<a id="21693" class="Keyword">open</a> <a id="21698" class="Keyword">import</a> <a id="21705" href="graph-theory.orientations-undirected-graphs.html" class="Module">graph-theory.orientations-undirected-graphs</a>
<a id="21749" class="Keyword">open</a> <a id="21754" class="Keyword">import</a> <a id="21761" href="graph-theory.paths-undirected-graphs.html" class="Module">graph-theory.paths-undirected-graphs</a>
<a id="21798" class="Keyword">open</a> <a id="21803" class="Keyword">import</a> <a id="21810" href="graph-theory.polygons.html" class="Module">graph-theory.polygons</a>
<a id="21832" class="Keyword">open</a> <a id="21837" class="Keyword">import</a> <a id="21844" href="graph-theory.reflexive-graphs.html" class="Module">graph-theory.reflexive-graphs</a>
<a id="21874" class="Keyword">open</a> <a id="21879" class="Keyword">import</a> <a id="21886" href="graph-theory.regular-undirected-graphs.html" class="Module">graph-theory.regular-undirected-graphs</a>
<a id="21925" class="Keyword">open</a> <a id="21930" class="Keyword">import</a> <a id="21937" href="graph-theory.simple-undirected-graphs.html" class="Module">graph-theory.simple-undirected-graphs</a>
<a id="21975" class="Keyword">open</a> <a id="21980" class="Keyword">import</a> <a id="21987" href="graph-theory.undirected-graphs.html" class="Module">graph-theory.undirected-graphs</a>
<a id="22018" class="Keyword">open</a> <a id="22023" class="Keyword">import</a> <a id="22030" href="graph-theory.vertex-covers.html" class="Module">graph-theory.vertex-covers</a>
<a id="22057" class="Keyword">open</a> <a id="22062" class="Keyword">import</a> <a id="22069" href="graph-theory.voltage-graphs.html" class="Module">graph-theory.voltage-graphs</a>
</pre>
## Group theory

<pre class="Agda"><a id="22127" class="Keyword">open</a> <a id="22132" class="Keyword">import</a> <a id="22139" href="group-theory.html" class="Module">group-theory</a>
<a id="22152" class="Keyword">open</a> <a id="22157" class="Keyword">import</a> <a id="22164" href="group-theory.abelian-groups.html" class="Module">group-theory.abelian-groups</a>
<a id="22192" class="Keyword">open</a> <a id="22197" class="Keyword">import</a> <a id="22204" href="group-theory.abelian-subgroups.html" class="Module">group-theory.abelian-subgroups</a>
<a id="22235" class="Keyword">open</a> <a id="22240" class="Keyword">import</a> <a id="22247" href="group-theory.abstract-group-torsors.html" class="Module">group-theory.abstract-group-torsors</a>
<a id="22283" class="Keyword">open</a> <a id="22288" class="Keyword">import</a> <a id="22295" href="group-theory.addition-homomorphisms-abelian-groups.html" class="Module">group-theory.addition-homomorphisms-abelian-groups</a>
<a id="22346" class="Keyword">open</a> <a id="22351" class="Keyword">import</a> <a id="22358" href="group-theory.automorphism-groups.html" class="Module">group-theory.automorphism-groups</a>
<a id="22391" class="Keyword">open</a> <a id="22396" class="Keyword">import</a> <a id="22403" href="group-theory.category-of-groups.html" class="Module">group-theory.category-of-groups</a>
<a id="22435" class="Keyword">open</a> <a id="22440" class="Keyword">import</a> <a id="22447" href="group-theory.category-of-semigroups.html" class="Module">group-theory.category-of-semigroups</a>
<a id="22483" class="Keyword">open</a> <a id="22488" class="Keyword">import</a> <a id="22495" href="group-theory.cayleys-theorem.html" class="Module">group-theory.cayleys-theorem</a>
<a id="22524" class="Keyword">open</a> <a id="22529" class="Keyword">import</a> <a id="22536" href="group-theory.concrete-group-actions.html" class="Module">group-theory.concrete-group-actions</a>
<a id="22572" class="Keyword">open</a> <a id="22577" class="Keyword">import</a> <a id="22584" href="group-theory.concrete-groups.html" class="Module">group-theory.concrete-groups</a>
<a id="22613" class="Keyword">open</a> <a id="22618" class="Keyword">import</a> <a id="22625" href="group-theory.concrete-subgroups.html" class="Module">group-theory.concrete-subgroups</a>
<a id="22657" class="Keyword">open</a> <a id="22662" class="Keyword">import</a> <a id="22669" href="group-theory.conjugation.html" class="Module">group-theory.conjugation</a>
<a id="22694" class="Keyword">open</a> <a id="22699" class="Keyword">import</a> <a id="22706" href="group-theory.embeddings-groups.html" class="Module">group-theory.embeddings-groups</a>
<a id="22737" class="Keyword">open</a> <a id="22742" class="Keyword">import</a> <a id="22749" href="group-theory.endomorphism-rings-abelian-groups.html" class="Module">group-theory.endomorphism-rings-abelian-groups</a>
<a id="22796" class="Keyword">open</a> <a id="22801" class="Keyword">import</a> <a id="22808" href="group-theory.epimorphisms-groups.html" class="Module">group-theory.epimorphisms-groups</a>
<a id="22841" class="Keyword">open</a> <a id="22846" class="Keyword">import</a> <a id="22853" href="group-theory.equivalences-group-actions.html" class="Module">group-theory.equivalences-group-actions</a>
<a id="22893" class="Keyword">open</a> <a id="22898" class="Keyword">import</a> <a id="22905" href="group-theory.equivalences-semigroups.html" class="Module">group-theory.equivalences-semigroups</a>
<a id="22942" class="Keyword">open</a> <a id="22947" class="Keyword">import</a> <a id="22954" href="group-theory.examples-higher-groups.html" class="Module">group-theory.examples-higher-groups</a>
<a id="22990" class="Keyword">open</a> <a id="22995" class="Keyword">import</a> <a id="23002" href="group-theory.furstenberg-groups.html" class="Module">group-theory.furstenberg-groups</a>
<a id="23034" class="Keyword">open</a> <a id="23039" class="Keyword">import</a> <a id="23046" href="group-theory.group-actions.html" class="Module">group-theory.group-actions</a>
<a id="23073" class="Keyword">open</a> <a id="23078" class="Keyword">import</a> <a id="23085" href="group-theory.groups.html" class="Module">group-theory.groups</a>
<a id="23105" class="Keyword">open</a> <a id="23110" class="Keyword">import</a> <a id="23117" href="group-theory.higher-groups.html" class="Module">group-theory.higher-groups</a>
<a id="23144" class="Keyword">open</a> <a id="23149" class="Keyword">import</a> <a id="23156" href="group-theory.homomorphisms-abelian-groups.html" class="Module">group-theory.homomorphisms-abelian-groups</a>
<a id="23198" class="Keyword">open</a> <a id="23203" class="Keyword">import</a> <a id="23210" href="group-theory.homomorphisms-generated-subgroups.html" class="Module">group-theory.homomorphisms-generated-subgroups</a>
<a id="23257" class="Keyword">open</a> <a id="23262" class="Keyword">import</a> <a id="23269" href="group-theory.homomorphisms-group-actions.html" class="Module">group-theory.homomorphisms-group-actions</a>
<a id="23310" class="Keyword">open</a> <a id="23315" class="Keyword">import</a> <a id="23322" href="group-theory.homomorphisms-groups.html" class="Module">group-theory.homomorphisms-groups</a>
<a id="23356" class="Keyword">open</a> <a id="23361" class="Keyword">import</a> <a id="23368" href="group-theory.homomorphisms-monoids.html" class="Module">group-theory.homomorphisms-monoids</a>
<a id="23403" class="Keyword">open</a> <a id="23408" class="Keyword">import</a> <a id="23415" href="group-theory.homomorphisms-semigroups.html" class="Module">group-theory.homomorphisms-semigroups</a>
<a id="23453" class="Keyword">open</a> <a id="23458" class="Keyword">import</a> <a id="23465" href="group-theory.inverse-semigroups.html" class="Module">group-theory.inverse-semigroups</a>
<a id="23497" class="Keyword">open</a> <a id="23502" class="Keyword">import</a> <a id="23509" href="group-theory.invertible-elements-monoids.html" class="Module">group-theory.invertible-elements-monoids</a>
<a id="23550" class="Keyword">open</a> <a id="23555" class="Keyword">import</a> <a id="23562" href="group-theory.isomorphisms-abelian-groups.html" class="Module">group-theory.isomorphisms-abelian-groups</a>
<a id="23603" class="Keyword">open</a> <a id="23608" class="Keyword">import</a> <a id="23615" href="group-theory.isomorphisms-group-actions.html" class="Module">group-theory.isomorphisms-group-actions</a>
<a id="23655" class="Keyword">open</a> <a id="23660" class="Keyword">import</a> <a id="23667" href="group-theory.isomorphisms-groups.html" class="Module">group-theory.isomorphisms-groups</a>
<a id="23700" class="Keyword">open</a> <a id="23705" class="Keyword">import</a> <a id="23712" href="group-theory.isomorphisms-semigroups.html" class="Module">group-theory.isomorphisms-semigroups</a>
<a id="23749" class="Keyword">open</a> <a id="23754" class="Keyword">import</a> <a id="23761" href="group-theory.mere-equivalences-group-actions.html" class="Module">group-theory.mere-equivalences-group-actions</a>
<a id="23806" class="Keyword">open</a> <a id="23811" class="Keyword">import</a> <a id="23818" href="group-theory.monoids.html" class="Module">group-theory.monoids</a>
<a id="23839" class="Keyword">open</a> <a id="23844" class="Keyword">import</a> <a id="23851" href="group-theory.monomorphisms-groups.html" class="Module">group-theory.monomorphisms-groups</a>
<a id="23885" class="Keyword">open</a> <a id="23890" class="Keyword">import</a> <a id="23897" href="group-theory.orbits-group-actions.html" class="Module">group-theory.orbits-group-actions</a>
<a id="23931" class="Keyword">open</a> <a id="23936" class="Keyword">import</a> <a id="23943" href="group-theory.precategory-of-group-actions.html" class="Module">group-theory.precategory-of-group-actions</a>
<a id="23985" class="Keyword">open</a> <a id="23990" class="Keyword">import</a> <a id="23997" href="group-theory.precategory-of-groups.html" class="Module">group-theory.precategory-of-groups</a>
<a id="24032" class="Keyword">open</a> <a id="24037" class="Keyword">import</a> <a id="24044" href="group-theory.precategory-of-semigroups.html" class="Module">group-theory.precategory-of-semigroups</a>
<a id="24083" class="Keyword">open</a> <a id="24088" class="Keyword">import</a> <a id="24095" href="group-theory.principal-group-actions.html" class="Module">group-theory.principal-group-actions</a>
<a id="24132" class="Keyword">open</a> <a id="24137" class="Keyword">import</a> <a id="24144" href="group-theory.semigroups.html" class="Module">group-theory.semigroups</a>
<a id="24168" class="Keyword">open</a> <a id="24173" class="Keyword">import</a> <a id="24180" href="group-theory.sheargroups.html" class="Module">group-theory.sheargroups</a>
<a id="24205" class="Keyword">open</a> <a id="24210" class="Keyword">import</a> <a id="24217" href="group-theory.stabilizer-groups.html" class="Module">group-theory.stabilizer-groups</a>
<a id="24248" class="Keyword">open</a> <a id="24253" class="Keyword">import</a> <a id="24260" href="group-theory.subgroups-generated-by-subsets-groups.html" class="Module">group-theory.subgroups-generated-by-subsets-groups</a>
<a id="24311" class="Keyword">open</a> <a id="24316" class="Keyword">import</a> <a id="24323" href="group-theory.subgroups.html" class="Module">group-theory.subgroups</a>
<a id="24346" class="Keyword">open</a> <a id="24351" class="Keyword">import</a> <a id="24358" href="group-theory.substitution-functor-group-actions.html" class="Module">group-theory.substitution-functor-group-actions</a>
<a id="24406" class="Keyword">open</a> <a id="24411" class="Keyword">import</a> <a id="24418" href="group-theory.symmetric-groups.html" class="Module">group-theory.symmetric-groups</a>
<a id="24448" class="Keyword">open</a> <a id="24453" class="Keyword">import</a> <a id="24460" href="group-theory.transitive-group-actions.html" class="Module">group-theory.transitive-group-actions</a>
</pre>
## Linear algebra

<pre class="Agda"><a id="24530" class="Keyword">open</a> <a id="24535" class="Keyword">import</a> <a id="24542" href="linear-algebra.html" class="Module">linear-algebra</a>
<a id="24557" class="Keyword">open</a> <a id="24562" class="Keyword">import</a> <a id="24569" href="linear-algebra.constant-matrices.html" class="Module">linear-algebra.constant-matrices</a>
<a id="24602" class="Keyword">open</a> <a id="24607" class="Keyword">import</a> <a id="24614" href="linear-algebra.constant-vectors.html" class="Module">linear-algebra.constant-vectors</a>
<a id="24646" class="Keyword">open</a> <a id="24651" class="Keyword">import</a> <a id="24658" href="linear-algebra.diagonal-matrices-on-rings.html" class="Module">linear-algebra.diagonal-matrices-on-rings</a>
<a id="24700" class="Keyword">open</a> <a id="24705" class="Keyword">import</a> <a id="24712" href="linear-algebra.functoriality-matrices.html" class="Module">linear-algebra.functoriality-matrices</a>
<a id="24750" class="Keyword">open</a> <a id="24755" class="Keyword">import</a> <a id="24762" href="linear-algebra.functoriality-vectors.html" class="Module">linear-algebra.functoriality-vectors</a>
<a id="24799" class="Keyword">open</a> <a id="24804" class="Keyword">import</a> <a id="24811" href="linear-algebra.matrices-on-rings.html" class="Module">linear-algebra.matrices-on-rings</a>
<a id="24844" class="Keyword">open</a> <a id="24849" class="Keyword">import</a> <a id="24856" href="linear-algebra.matrices.html" class="Module">linear-algebra.matrices</a>
<a id="24880" class="Keyword">open</a> <a id="24885" class="Keyword">import</a> <a id="24892" href="linear-algebra.multiplication-matrices.html" class="Module">linear-algebra.multiplication-matrices</a>
<a id="24931" class="Keyword">open</a> <a id="24936" class="Keyword">import</a> <a id="24943" href="linear-algebra.scalar-multiplication-matrices.html" class="Module">linear-algebra.scalar-multiplication-matrices</a>
<a id="24989" class="Keyword">open</a> <a id="24994" class="Keyword">import</a> <a id="25001" href="linear-algebra.scalar-multiplication-vectors.html" class="Module">linear-algebra.scalar-multiplication-vectors</a>
<a id="25046" class="Keyword">open</a> <a id="25051" class="Keyword">import</a> <a id="25058" href="linear-algebra.transposition-matrices.html" class="Module">linear-algebra.transposition-matrices</a>
<a id="25096" class="Keyword">open</a> <a id="25101" class="Keyword">import</a> <a id="25108" href="linear-algebra.vectors-on-rings.html" class="Module">linear-algebra.vectors-on-rings</a>
<a id="25140" class="Keyword">open</a> <a id="25145" class="Keyword">import</a> <a id="25152" href="linear-algebra.vectors.html" class="Module">linear-algebra.vectors</a>
</pre>
## Order theory

<pre class="Agda"><a id="25205" class="Keyword">open</a> <a id="25210" class="Keyword">import</a> <a id="25217" href="order-theory.html" class="Module">order-theory</a>
<a id="25230" class="Keyword">open</a> <a id="25235" class="Keyword">import</a> <a id="25242" href="order-theory.chains-posets.html" class="Module">order-theory.chains-posets</a>
<a id="25269" class="Keyword">open</a> <a id="25274" class="Keyword">import</a> <a id="25281" href="order-theory.chains-preorders.html" class="Module">order-theory.chains-preorders</a>
<a id="25311" class="Keyword">open</a> <a id="25316" class="Keyword">import</a> <a id="25323" href="order-theory.decidable-subposets.html" class="Module">order-theory.decidable-subposets</a>
<a id="25356" class="Keyword">open</a> <a id="25361" class="Keyword">import</a> <a id="25368" href="order-theory.decidable-subpreorders.html" class="Module">order-theory.decidable-subpreorders</a>
<a id="25404" class="Keyword">open</a> <a id="25409" class="Keyword">import</a> <a id="25416" href="order-theory.finite-posets.html" class="Module">order-theory.finite-posets</a>
<a id="25443" class="Keyword">open</a> <a id="25448" class="Keyword">import</a> <a id="25455" href="order-theory.finite-preorders.html" class="Module">order-theory.finite-preorders</a>
<a id="25485" class="Keyword">open</a> <a id="25490" class="Keyword">import</a> <a id="25497" href="order-theory.finitely-graded-posets.html" class="Module">order-theory.finitely-graded-posets</a>
<a id="25533" class="Keyword">open</a> <a id="25538" class="Keyword">import</a> <a id="25545" href="order-theory.greatest-lower-bounds-posets.html" class="Module">order-theory.greatest-lower-bounds-posets</a>
<a id="25587" class="Keyword">open</a> <a id="25592" class="Keyword">import</a> <a id="25599" href="order-theory.interval-subposets.html" class="Module">order-theory.interval-subposets</a>
<a id="25631" class="Keyword">open</a> <a id="25636" class="Keyword">import</a> <a id="25643" href="order-theory.join-semilattices.html" class="Module">order-theory.join-semilattices</a>
<a id="25674" class="Keyword">open</a> <a id="25679" class="Keyword">import</a> <a id="25686" href="order-theory.large-posets.html" class="Module">order-theory.large-posets</a>
<a id="25712" class="Keyword">open</a> <a id="25717" class="Keyword">import</a> <a id="25724" href="order-theory.large-preorders.html" class="Module">order-theory.large-preorders</a>
<a id="25753" class="Keyword">open</a> <a id="25758" class="Keyword">import</a> <a id="25765" href="order-theory.largest-elements-posets.html" class="Module">order-theory.largest-elements-posets</a>
<a id="25802" class="Keyword">open</a> <a id="25807" class="Keyword">import</a> <a id="25814" href="order-theory.largest-elements-preorders.html" class="Module">order-theory.largest-elements-preorders</a>
<a id="25854" class="Keyword">open</a> <a id="25859" class="Keyword">import</a> <a id="25866" href="order-theory.least-elements-posets.html" class="Module">order-theory.least-elements-posets</a>
<a id="25901" class="Keyword">open</a> <a id="25906" class="Keyword">import</a> <a id="25913" href="order-theory.least-elements-preorders.html" class="Module">order-theory.least-elements-preorders</a>
<a id="25951" class="Keyword">open</a> <a id="25956" class="Keyword">import</a> <a id="25963" href="order-theory.least-upper-bounds-posets.html" class="Module">order-theory.least-upper-bounds-posets</a>
<a id="26002" class="Keyword">open</a> <a id="26007" class="Keyword">import</a> <a id="26014" href="order-theory.locally-finite-posets.html" class="Module">order-theory.locally-finite-posets</a>
<a id="26049" class="Keyword">open</a> <a id="26054" class="Keyword">import</a> <a id="26061" href="order-theory.maximal-chains-posets.html" class="Module">order-theory.maximal-chains-posets</a>
<a id="26096" class="Keyword">open</a> <a id="26101" class="Keyword">import</a> <a id="26108" href="order-theory.maximal-chains-preorders.html" class="Module">order-theory.maximal-chains-preorders</a>
<a id="26146" class="Keyword">open</a> <a id="26151" class="Keyword">import</a> <a id="26158" href="order-theory.meet-semilattices.html" class="Module">order-theory.meet-semilattices</a>
<a id="26189" class="Keyword">open</a> <a id="26194" class="Keyword">import</a> <a id="26201" href="order-theory.planar-binary-trees.html" class="Module">order-theory.planar-binary-trees</a>
<a id="26234" class="Keyword">open</a> <a id="26239" class="Keyword">import</a> <a id="26246" href="order-theory.posets.html" class="Module">order-theory.posets</a>
<a id="26266" class="Keyword">open</a> <a id="26271" class="Keyword">import</a> <a id="26278" href="order-theory.preorders.html" class="Module">order-theory.preorders</a>
<a id="26301" class="Keyword">open</a> <a id="26306" class="Keyword">import</a> <a id="26313" href="order-theory.subposets.html" class="Module">order-theory.subposets</a>
<a id="26336" class="Keyword">open</a> <a id="26341" class="Keyword">import</a> <a id="26348" href="order-theory.subpreorders.html" class="Module">order-theory.subpreorders</a>
<a id="26374" class="Keyword">open</a> <a id="26379" class="Keyword">import</a> <a id="26386" href="order-theory.total-posets.html" class="Module">order-theory.total-posets</a>
<a id="26412" class="Keyword">open</a> <a id="26417" class="Keyword">import</a> <a id="26424" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a>
</pre>
## Polytopes

<pre class="Agda"><a id="26480" class="Keyword">open</a> <a id="26485" class="Keyword">import</a> <a id="26492" href="polytopes.html" class="Module">polytopes</a>
<a id="26502" class="Keyword">open</a> <a id="26507" class="Keyword">import</a> <a id="26514" href="polytopes.abstract-polytopes.html" class="Module">polytopes.abstract-polytopes</a>
</pre>
## Ring theory

<pre class="Agda"><a id="26572" class="Keyword">open</a> <a id="26577" class="Keyword">import</a> <a id="26584" href="ring-theory.html" class="Module">ring-theory</a>
<a id="26596" class="Keyword">open</a> <a id="26601" class="Keyword">import</a> <a id="26608" href="ring-theory.division-rings.html" class="Module">ring-theory.division-rings</a>
<a id="26635" class="Keyword">open</a> <a id="26640" class="Keyword">import</a> <a id="26647" href="ring-theory.homomorphisms-rings.html" class="Module">ring-theory.homomorphisms-rings</a>
<a id="26679" class="Keyword">open</a> <a id="26684" class="Keyword">import</a> <a id="26691" href="ring-theory.ideals-generated-by-subsets-rings.html" class="Module">ring-theory.ideals-generated-by-subsets-rings</a>
<a id="26737" class="Keyword">open</a> <a id="26742" class="Keyword">import</a> <a id="26749" href="ring-theory.ideals-rings.html" class="Module">ring-theory.ideals-rings</a>
<a id="26774" class="Keyword">open</a> <a id="26779" class="Keyword">import</a> <a id="26786" href="ring-theory.invertible-elements-rings.html" class="Module">ring-theory.invertible-elements-rings</a>
<a id="26824" class="Keyword">open</a> <a id="26829" class="Keyword">import</a> <a id="26836" href="ring-theory.isomorphisms-rings.html" class="Module">ring-theory.isomorphisms-rings</a>
<a id="26867" class="Keyword">open</a> <a id="26872" class="Keyword">import</a> <a id="26879" href="ring-theory.localizations-rings.html" class="Module">ring-theory.localizations-rings</a>
<a id="26911" class="Keyword">open</a> <a id="26916" class="Keyword">import</a> <a id="26923" href="ring-theory.nontrivial-rings.html" class="Module">ring-theory.nontrivial-rings</a>
<a id="26952" class="Keyword">open</a> <a id="26957" class="Keyword">import</a> <a id="26964" href="ring-theory.opposite-rings.html" class="Module">ring-theory.opposite-rings</a>
<a id="26991" class="Keyword">open</a> <a id="26996" class="Keyword">import</a> <a id="27003" href="ring-theory.rings.html" class="Module">ring-theory.rings</a>
<a id="27021" class="Keyword">open</a> <a id="27026" class="Keyword">import</a> <a id="27033" href="ring-theory.subsets-rings.html" class="Module">ring-theory.subsets-rings</a>
</pre>
## Synthetic homotopy theory

<pre class="Agda"><a id="27102" class="Keyword">open</a> <a id="27107" class="Keyword">import</a> <a id="27114" href="synthetic-homotopy-theory.html" class="Module">synthetic-homotopy-theory</a>
<a id="27140" class="Keyword">open</a> <a id="27145" class="Keyword">import</a> <a id="27152" href="synthetic-homotopy-theory.23-pullbacks.html" class="Module">synthetic-homotopy-theory.23-pullbacks</a>
<a id="27191" class="Keyword">open</a> <a id="27196" class="Keyword">import</a> <a id="27203" href="synthetic-homotopy-theory.24-pushouts.html" class="Module">synthetic-homotopy-theory.24-pushouts</a>
<a id="27241" class="Keyword">open</a> <a id="27246" class="Keyword">import</a> <a id="27253" href="synthetic-homotopy-theory.25-cubical-diagrams.html" class="Module">synthetic-homotopy-theory.25-cubical-diagrams</a>
<a id="27299" class="Keyword">open</a> <a id="27304" class="Keyword">import</a> <a id="27311" href="synthetic-homotopy-theory.26-descent.html" class="Module">synthetic-homotopy-theory.26-descent</a>
<a id="27348" class="Keyword">open</a> <a id="27353" class="Keyword">import</a> <a id="27360" href="synthetic-homotopy-theory.26-id-pushout.html" class="Module">synthetic-homotopy-theory.26-id-pushout</a>
<a id="27400" class="Keyword">open</a> <a id="27405" class="Keyword">import</a> <a id="27412" href="synthetic-homotopy-theory.27-sequences.html" class="Module">synthetic-homotopy-theory.27-sequences</a>
<a id="27451" class="Keyword">open</a> <a id="27456" class="Keyword">import</a> <a id="27463" href="synthetic-homotopy-theory.circle.html" class="Module">synthetic-homotopy-theory.circle</a>
<a id="27496" class="Keyword">open</a> <a id="27501" class="Keyword">import</a> <a id="27508" href="synthetic-homotopy-theory.cyclic-types.html" class="Module">synthetic-homotopy-theory.cyclic-types</a>
<a id="27547" class="Keyword">open</a> <a id="27552" class="Keyword">import</a> <a id="27559" href="synthetic-homotopy-theory.double-loop-spaces.html" class="Module">synthetic-homotopy-theory.double-loop-spaces</a>
<a id="27604" class="Keyword">open</a> <a id="27609" class="Keyword">import</a> <a id="27616" href="synthetic-homotopy-theory.functoriality-loop-spaces.html" class="Module">synthetic-homotopy-theory.functoriality-loop-spaces</a>
<a id="27668" class="Keyword">open</a> <a id="27673" class="Keyword">import</a> <a id="27680" href="synthetic-homotopy-theory.groups-of-loops-in-1-types.html" class="Module">synthetic-homotopy-theory.groups-of-loops-in-1-types</a>
<a id="27733" class="Keyword">open</a> <a id="27738" class="Keyword">import</a> <a id="27745" href="synthetic-homotopy-theory.infinite-cyclic-types.html" class="Module">synthetic-homotopy-theory.infinite-cyclic-types</a>
<a id="27793" class="Keyword">open</a> <a id="27798" class="Keyword">import</a> <a id="27805" href="synthetic-homotopy-theory.interval-type.html" class="Module">synthetic-homotopy-theory.interval-type</a>
<a id="27845" class="Keyword">open</a> <a id="27850" class="Keyword">import</a> <a id="27857" href="synthetic-homotopy-theory.iterated-loop-spaces.html" class="Module">synthetic-homotopy-theory.iterated-loop-spaces</a>
<a id="27904" class="Keyword">open</a> <a id="27909" class="Keyword">import</a> <a id="27916" href="synthetic-homotopy-theory.loop-spaces.html" class="Module">synthetic-homotopy-theory.loop-spaces</a>
<a id="27954" class="Keyword">open</a> <a id="27959" class="Keyword">import</a> <a id="27966" href="synthetic-homotopy-theory.pointed-dependent-functions.html" class="Module">synthetic-homotopy-theory.pointed-dependent-functions</a>
<a id="28020" class="Keyword">open</a> <a id="28025" class="Keyword">import</a> <a id="28032" href="synthetic-homotopy-theory.pointed-equivalences.html" class="Module">synthetic-homotopy-theory.pointed-equivalences</a>
<a id="28079" class="Keyword">open</a> <a id="28084" class="Keyword">import</a> <a id="28091" href="synthetic-homotopy-theory.pointed-families-of-types.html" class="Module">synthetic-homotopy-theory.pointed-families-of-types</a>
<a id="28143" class="Keyword">open</a> <a id="28148" class="Keyword">import</a> <a id="28155" href="synthetic-homotopy-theory.pointed-homotopies.html" class="Module">synthetic-homotopy-theory.pointed-homotopies</a>
<a id="28200" class="Keyword">open</a> <a id="28205" class="Keyword">import</a> <a id="28212" href="synthetic-homotopy-theory.pointed-maps.html" class="Module">synthetic-homotopy-theory.pointed-maps</a>
<a id="28251" class="Keyword">open</a> <a id="28256" class="Keyword">import</a> <a id="28263" href="synthetic-homotopy-theory.pointed-types.html" class="Module">synthetic-homotopy-theory.pointed-types</a>
<a id="28303" class="Keyword">open</a> <a id="28308" class="Keyword">import</a> <a id="28315" href="synthetic-homotopy-theory.spaces.html" class="Module">synthetic-homotopy-theory.spaces</a>
<a id="28348" class="Keyword">open</a> <a id="28353" class="Keyword">import</a> <a id="28360" href="synthetic-homotopy-theory.triple-loop-spaces.html" class="Module">synthetic-homotopy-theory.triple-loop-spaces</a>
<a id="28405" class="Keyword">open</a> <a id="28410" class="Keyword">import</a> <a id="28417" href="synthetic-homotopy-theory.universal-cover-circle.html" class="Module">synthetic-homotopy-theory.universal-cover-circle</a>
</pre>
## Tutorials

<pre class="Agda"><a id="28493" class="Keyword">open</a> <a id="28498" class="Keyword">import</a> <a id="28505" href="tutorials.basic-agda.html" class="Module">tutorials.basic-agda</a>
</pre>
## Type theories

<pre class="Agda"><a id="28557" class="Keyword">open</a> <a id="28562" class="Keyword">import</a> <a id="28569" href="type-theories.html" class="Module">type-theories</a>
<a id="28583" class="Keyword">open</a> <a id="28588" class="Keyword">import</a> <a id="28595" href="type-theories.comprehension-type-theories.html" class="Module">type-theories.comprehension-type-theories</a>
<a id="28637" class="Keyword">open</a> <a id="28642" class="Keyword">import</a> <a id="28649" href="type-theories.dependent-type-theories.html" class="Module">type-theories.dependent-type-theories</a>
<a id="28687" class="Keyword">open</a> <a id="28692" class="Keyword">import</a> <a id="28699" href="type-theories.fibered-dependent-type-theories.html" class="Module">type-theories.fibered-dependent-type-theories</a>
<a id="28745" class="Keyword">open</a> <a id="28750" class="Keyword">import</a> <a id="28757" href="type-theories.sections-dependent-type-theories.html" class="Module">type-theories.sections-dependent-type-theories</a>
<a id="28804" class="Keyword">open</a> <a id="28809" class="Keyword">import</a> <a id="28816" href="type-theories.simple-type-theories.html" class="Module">type-theories.simple-type-theories</a>
<a id="28851" class="Keyword">open</a> <a id="28856" class="Keyword">import</a> <a id="28863" href="type-theories.unityped-type-theories.html" class="Module">type-theories.unityped-type-theories</a>
</pre>
## Univalent combinatorics

<pre class="Agda"><a id="28941" class="Keyword">open</a> <a id="28946" class="Keyword">import</a> <a id="28953" href="univalent-combinatorics.html" class="Module">univalent-combinatorics</a>
<a id="28977" class="Keyword">open</a> <a id="28982" class="Keyword">import</a> <a id="28989" href="univalent-combinatorics.2-element-decidable-subtypes.html" class="Module">univalent-combinatorics.2-element-decidable-subtypes</a>
<a id="29042" class="Keyword">open</a> <a id="29047" class="Keyword">import</a> <a id="29054" href="univalent-combinatorics.2-element-subtypes.html" class="Module">univalent-combinatorics.2-element-subtypes</a>
<a id="29097" class="Keyword">open</a> <a id="29102" class="Keyword">import</a> <a id="29109" href="univalent-combinatorics.2-element-types.html" class="Module">univalent-combinatorics.2-element-types</a>
<a id="29149" class="Keyword">open</a> <a id="29154" class="Keyword">import</a> <a id="29161" href="univalent-combinatorics.binomial-types.html" class="Module">univalent-combinatorics.binomial-types</a>
<a id="29200" class="Keyword">open</a> <a id="29205" class="Keyword">import</a> <a id="29212" href="univalent-combinatorics.cartesian-product-types.html" class="Module">univalent-combinatorics.cartesian-product-types</a>
<a id="29260" class="Keyword">open</a> <a id="29265" class="Keyword">import</a> <a id="29272" href="univalent-combinatorics.classical-finite-types.html" class="Module">univalent-combinatorics.classical-finite-types</a>
<a id="29319" class="Keyword">open</a> <a id="29324" class="Keyword">import</a> <a id="29331" href="univalent-combinatorics.complements-isolated-points.html" class="Module">univalent-combinatorics.complements-isolated-points</a>
<a id="29383" class="Keyword">open</a> <a id="29388" class="Keyword">import</a> <a id="29395" href="univalent-combinatorics.coproduct-types.html" class="Module">univalent-combinatorics.coproduct-types</a>
<a id="29435" class="Keyword">open</a> <a id="29440" class="Keyword">import</a> <a id="29447" href="univalent-combinatorics.counting-decidable-subtypes.html" class="Module">univalent-combinatorics.counting-decidable-subtypes</a>
<a id="29499" class="Keyword">open</a> <a id="29504" class="Keyword">import</a> <a id="29511" href="univalent-combinatorics.counting-dependent-pair-types.html" class="Module">univalent-combinatorics.counting-dependent-pair-types</a>
<a id="29565" class="Keyword">open</a> <a id="29570" class="Keyword">import</a> <a id="29577" href="univalent-combinatorics.counting-fibers-of-maps.html" class="Module">univalent-combinatorics.counting-fibers-of-maps</a>
<a id="29625" class="Keyword">open</a> <a id="29630" class="Keyword">import</a> <a id="29637" href="univalent-combinatorics.counting-maybe.html" class="Module">univalent-combinatorics.counting-maybe</a>
<a id="29676" class="Keyword">open</a> <a id="29681" class="Keyword">import</a> <a id="29688" href="univalent-combinatorics.counting.html" class="Module">univalent-combinatorics.counting</a>
<a id="29721" class="Keyword">open</a> <a id="29726" class="Keyword">import</a> <a id="29733" href="univalent-combinatorics.cubes.html" class="Module">univalent-combinatorics.cubes</a>
<a id="29763" class="Keyword">open</a> <a id="29768" class="Keyword">import</a> <a id="29775" href="univalent-combinatorics.decidable-dependent-function-types.html" class="Module">univalent-combinatorics.decidable-dependent-function-types</a>
<a id="29834" class="Keyword">open</a> <a id="29839" class="Keyword">import</a> <a id="29846" href="univalent-combinatorics.decidable-dependent-pair-types.html" class="Module">univalent-combinatorics.decidable-dependent-pair-types</a>
<a id="29901" class="Keyword">open</a> <a id="29906" class="Keyword">import</a> <a id="29913" href="univalent-combinatorics.decidable-propositions.html" class="Module">univalent-combinatorics.decidable-propositions</a>
<a id="29960" class="Keyword">open</a> <a id="29965" class="Keyword">import</a> <a id="29972" href="univalent-combinatorics.decidable-subtypes.html" class="Module">univalent-combinatorics.decidable-subtypes</a>
<a id="30015" class="Keyword">open</a> <a id="30020" class="Keyword">import</a> <a id="30027" href="univalent-combinatorics.dedekind-finite-sets.html" class="Module">univalent-combinatorics.dedekind-finite-sets</a>
<a id="30072" class="Keyword">open</a> <a id="30077" class="Keyword">import</a> <a id="30084" href="univalent-combinatorics.dependent-function-types.html" class="Module">univalent-combinatorics.dependent-function-types</a>
<a id="30133" class="Keyword">open</a> <a id="30138" class="Keyword">import</a> <a id="30145" href="univalent-combinatorics.dependent-sum-finite-types.html" class="Module">univalent-combinatorics.dependent-sum-finite-types</a>
<a id="30196" class="Keyword">open</a> <a id="30201" class="Keyword">import</a> <a id="30208" href="univalent-combinatorics.distributivity-of-set-truncation-over-finite-products.html" class="Module">univalent-combinatorics.distributivity-of-set-truncation-over-finite-products</a>
<a id="30286" class="Keyword">open</a> <a id="30291" class="Keyword">import</a> <a id="30298" href="univalent-combinatorics.double-counting.html" class="Module">univalent-combinatorics.double-counting</a>
<a id="30338" class="Keyword">open</a> <a id="30343" class="Keyword">import</a> <a id="30350" href="univalent-combinatorics.embeddings-standard-finite-types.html" class="Module">univalent-combinatorics.embeddings-standard-finite-types</a>
<a id="30407" class="Keyword">open</a> <a id="30412" class="Keyword">import</a> <a id="30419" href="univalent-combinatorics.embeddings.html" class="Module">univalent-combinatorics.embeddings</a>
<a id="30454" class="Keyword">open</a> <a id="30459" class="Keyword">import</a> <a id="30466" href="univalent-combinatorics.equality-finite-types.html" class="Module">univalent-combinatorics.equality-finite-types</a>
<a id="30512" class="Keyword">open</a> <a id="30517" class="Keyword">import</a> <a id="30524" href="univalent-combinatorics.equality-standard-finite-types.html" class="Module">univalent-combinatorics.equality-standard-finite-types</a>
<a id="30579" class="Keyword">open</a> <a id="30584" class="Keyword">import</a> <a id="30591" href="univalent-combinatorics.equivalences-cubes.html" class="Module">univalent-combinatorics.equivalences-cubes</a>
<a id="30634" class="Keyword">open</a> <a id="30639" class="Keyword">import</a> <a id="30646" href="univalent-combinatorics.equivalences-standard-finite-types.html" class="Module">univalent-combinatorics.equivalences-standard-finite-types</a>
<a id="30705" class="Keyword">open</a> <a id="30710" class="Keyword">import</a> <a id="30717" href="univalent-combinatorics.equivalences.html" class="Module">univalent-combinatorics.equivalences</a>
<a id="30754" class="Keyword">open</a> <a id="30759" class="Keyword">import</a> <a id="30766" href="univalent-combinatorics.ferrers-diagrams.html" class="Module">univalent-combinatorics.ferrers-diagrams</a>
<a id="30807" class="Keyword">open</a> <a id="30812" class="Keyword">import</a> <a id="30819" href="univalent-combinatorics.fibers-of-maps.html" class="Module">univalent-combinatorics.fibers-of-maps</a>
<a id="30858" class="Keyword">open</a> <a id="30863" class="Keyword">import</a> <a id="30870" href="univalent-combinatorics.finite-choice.html" class="Module">univalent-combinatorics.finite-choice</a>
<a id="30908" class="Keyword">open</a> <a id="30913" class="Keyword">import</a> <a id="30920" href="univalent-combinatorics.finite-connected-components.html" class="Module">univalent-combinatorics.finite-connected-components</a>
<a id="30972" class="Keyword">open</a> <a id="30977" class="Keyword">import</a> <a id="30984" href="univalent-combinatorics.finite-presentations.html" class="Module">univalent-combinatorics.finite-presentations</a>
<a id="31029" class="Keyword">open</a> <a id="31034" class="Keyword">import</a> <a id="31041" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a>
<a id="31078" class="Keyword">open</a> <a id="31083" class="Keyword">import</a> <a id="31090" href="univalent-combinatorics.finitely-presented-types.html" class="Module">univalent-combinatorics.finitely-presented-types</a>
<a id="31139" class="Keyword">open</a> <a id="31144" class="Keyword">import</a> <a id="31151" href="univalent-combinatorics.function-types.html" class="Module">univalent-combinatorics.function-types</a>
<a id="31190" class="Keyword">open</a> <a id="31195" class="Keyword">import</a> <a id="31202" href="univalent-combinatorics.image-of-maps.html" class="Module">univalent-combinatorics.image-of-maps</a>
<a id="31240" class="Keyword">open</a> <a id="31245" class="Keyword">import</a> <a id="31252" href="univalent-combinatorics.inequality-types-with-counting.html" class="Module">univalent-combinatorics.inequality-types-with-counting</a>
<a id="31307" class="Keyword">open</a> <a id="31312" class="Keyword">import</a> <a id="31319" href="univalent-combinatorics.injective-maps.html" class="Module">univalent-combinatorics.injective-maps</a>
<a id="31358" class="Keyword">open</a> <a id="31363" class="Keyword">import</a> <a id="31370" href="univalent-combinatorics.isotopies-latin-squares.html" class="Module">univalent-combinatorics.isotopies-latin-squares</a>
<a id="31418" class="Keyword">open</a> <a id="31423" class="Keyword">import</a> <a id="31430" href="univalent-combinatorics.kuratowsky-finite-sets.html" class="Module">univalent-combinatorics.kuratowsky-finite-sets</a>
<a id="31477" class="Keyword">open</a> <a id="31482" class="Keyword">import</a> <a id="31489" href="univalent-combinatorics.latin-squares.html" class="Module">univalent-combinatorics.latin-squares</a>
<a id="31527" class="Keyword">open</a> <a id="31532" class="Keyword">import</a> <a id="31539" href="univalent-combinatorics.lists.html" class="Module">univalent-combinatorics.lists</a>
<a id="31569" class="Keyword">open</a> <a id="31574" class="Keyword">import</a> <a id="31581" href="univalent-combinatorics.main-classes-of-latin-hypercubes.html" class="Module">univalent-combinatorics.main-classes-of-latin-hypercubes</a>
<a id="31638" class="Keyword">open</a> <a id="31643" class="Keyword">import</a> <a id="31650" href="univalent-combinatorics.main-classes-of-latin-squares.html" class="Module">univalent-combinatorics.main-classes-of-latin-squares</a>
<a id="31704" class="Keyword">open</a> <a id="31709" class="Keyword">import</a> <a id="31716" href="univalent-combinatorics.maybe.html" class="Module">univalent-combinatorics.maybe</a>
<a id="31746" class="Keyword">open</a> <a id="31751" class="Keyword">import</a> <a id="31758" href="univalent-combinatorics.orientations-complete-undirected-graph.html" class="Module">univalent-combinatorics.orientations-complete-undirected-graph</a>
<a id="31821" class="Keyword">open</a> <a id="31826" class="Keyword">import</a> <a id="31833" href="univalent-combinatorics.orientations-cubes.html" class="Module">univalent-combinatorics.orientations-cubes</a>
<a id="31876" class="Keyword">open</a> <a id="31881" class="Keyword">import</a> <a id="31888" href="univalent-combinatorics.petri-nets.html" class="Module">univalent-combinatorics.petri-nets</a>
<a id="31923" class="Keyword">open</a> <a id="31928" class="Keyword">import</a> <a id="31935" href="univalent-combinatorics.pi-finite-types.html" class="Module">univalent-combinatorics.pi-finite-types</a>
<a id="31975" class="Keyword">open</a> <a id="31980" class="Keyword">import</a> <a id="31987" href="univalent-combinatorics.pigeonhole-principle.html" class="Module">univalent-combinatorics.pigeonhole-principle</a>
<a id="32032" class="Keyword">open</a> <a id="32037" class="Keyword">import</a> <a id="32044" href="univalent-combinatorics.presented-pi-finite-types.html" class="Module">univalent-combinatorics.presented-pi-finite-types</a>
<a id="32094" class="Keyword">open</a> <a id="32099" class="Keyword">import</a> <a id="32106" href="univalent-combinatorics.ramsey-theory.html" class="Module">univalent-combinatorics.ramsey-theory</a>
<a id="32144" class="Keyword">open</a> <a id="32149" class="Keyword">import</a> <a id="32156" href="univalent-combinatorics.retracts-of-finite-types.html" class="Module">univalent-combinatorics.retracts-of-finite-types</a>
<a id="32205" class="Keyword">open</a> <a id="32210" class="Keyword">import</a> <a id="32217" href="univalent-combinatorics.skipping-element-standard-finite-types.html" class="Module">univalent-combinatorics.skipping-element-standard-finite-types</a>
<a id="32280" class="Keyword">open</a> <a id="32285" class="Keyword">import</a> <a id="32292" href="univalent-combinatorics.species.html" class="Module">univalent-combinatorics.species</a>
<a id="32324" class="Keyword">open</a> <a id="32329" class="Keyword">import</a> <a id="32336" href="univalent-combinatorics.standard-finite-pruned-trees.html" class="Module">univalent-combinatorics.standard-finite-pruned-trees</a>
<a id="32389" class="Keyword">open</a> <a id="32394" class="Keyword">import</a> <a id="32401" href="univalent-combinatorics.standard-finite-trees.html" class="Module">univalent-combinatorics.standard-finite-trees</a>
<a id="32447" class="Keyword">open</a> <a id="32452" class="Keyword">import</a> <a id="32459" href="univalent-combinatorics.standard-finite-types.html" class="Module">univalent-combinatorics.standard-finite-types</a>
<a id="32505" class="Keyword">open</a> <a id="32510" class="Keyword">import</a> <a id="32517" href="univalent-combinatorics.sums-of-natural-numbers.html" class="Module">univalent-combinatorics.sums-of-natural-numbers</a>
<a id="32565" class="Keyword">open</a> <a id="32570" class="Keyword">import</a> <a id="32577" href="univalent-combinatorics.surjective-maps.html" class="Module">univalent-combinatorics.surjective-maps</a>
<a id="32617" class="Keyword">open</a> <a id="32622" class="Keyword">import</a> <a id="32629" href="univalent-combinatorics.symmetric-difference.html" class="Module">univalent-combinatorics.symmetric-difference</a>
<a id="32674" class="Keyword">open</a> <a id="32679" class="Keyword">import</a> <a id="32686" href="univalent-combinatorics.universal-property-standard-finite-types.html" class="Module">univalent-combinatorics.universal-property-standard-finite-types</a>
</pre>
## Wild algebra

<pre class="Agda"><a id="32781" class="Keyword">open</a> <a id="32786" class="Keyword">import</a> <a id="32793" href="wild-algebra.html" class="Module">wild-algebra</a>
<a id="32806" class="Keyword">open</a> <a id="32811" class="Keyword">import</a> <a id="32818" href="wild-algebra.magmas.html" class="Module">wild-algebra.magmas</a>
<a id="32838" class="Keyword">open</a> <a id="32843" class="Keyword">import</a> <a id="32850" href="wild-algebra.morphisms-magmas.html" class="Module">wild-algebra.morphisms-magmas</a>
<a id="32880" class="Keyword">open</a> <a id="32885" class="Keyword">import</a> <a id="32892" href="wild-algebra.morphisms-wild-unital-magmas.html" class="Module">wild-algebra.morphisms-wild-unital-magmas</a>
<a id="32934" class="Keyword">open</a> <a id="32939" class="Keyword">import</a> <a id="32946" href="wild-algebra.universal-property-lists-wild-monoids.html" class="Module">wild-algebra.universal-property-lists-wild-monoids</a>
<a id="32997" class="Keyword">open</a> <a id="33002" class="Keyword">import</a> <a id="33009" href="wild-algebra.wild-groups.html" class="Module">wild-algebra.wild-groups</a>
<a id="33034" class="Keyword">open</a> <a id="33039" class="Keyword">import</a> <a id="33046" href="wild-algebra.wild-loops.html" class="Module">wild-algebra.wild-loops</a>
<a id="33070" class="Keyword">open</a> <a id="33075" class="Keyword">import</a> <a id="33082" href="wild-algebra.wild-monoids.html" class="Module">wild-algebra.wild-monoids</a>
<a id="33108" class="Keyword">open</a> <a id="33113" class="Keyword">import</a> <a id="33120" href="wild-algebra.wild-quasigroups.html" class="Module">wild-algebra.wild-quasigroups</a>
<a id="33150" class="Keyword">open</a> <a id="33155" class="Keyword">import</a> <a id="33162" href="wild-algebra.wild-semigroups.html" class="Module">wild-algebra.wild-semigroups</a>
<a id="33191" class="Keyword">open</a> <a id="33196" class="Keyword">import</a> <a id="33203" href="wild-algebra.wild-unital-magmas.html" class="Module">wild-algebra.wild-unital-magmas</a>
</pre>
## Everything

See the list of all Agda modules [here](everything.html).

