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
<a id="3223" class="Keyword">open</a> <a id="3228" class="Keyword">import</a> <a id="3235" href="category-theory.equivalences-categories.html" class="Module">category-theory.equivalences-categories</a>
<a id="3275" class="Keyword">open</a> <a id="3280" class="Keyword">import</a> <a id="3287" href="category-theory.equivalences-large-precategories.html" class="Module">category-theory.equivalences-large-precategories</a>
<a id="3336" class="Keyword">open</a> <a id="3341" class="Keyword">import</a> <a id="3348" href="category-theory.equivalences-precategories.html" class="Module">category-theory.equivalences-precategories</a>
<a id="3391" class="Keyword">open</a> <a id="3396" class="Keyword">import</a> <a id="3403" href="category-theory.functors-categories.html" class="Module">category-theory.functors-categories</a>
<a id="3439" class="Keyword">open</a> <a id="3444" class="Keyword">import</a> <a id="3451" href="category-theory.functors-large-precategories.html" class="Module">category-theory.functors-large-precategories</a>
<a id="3496" class="Keyword">open</a> <a id="3501" class="Keyword">import</a> <a id="3508" href="category-theory.functors-precategories.html" class="Module">category-theory.functors-precategories</a>
<a id="3547" class="Keyword">open</a> <a id="3552" class="Keyword">import</a> <a id="3559" href="category-theory.homotopies-natural-transformations-large-precategories.html" class="Module">category-theory.homotopies-natural-transformations-large-precategories</a>
<a id="3630" class="Keyword">open</a> <a id="3635" class="Keyword">import</a> <a id="3642" href="category-theory.initial-objects-precategories.html" class="Module">category-theory.initial-objects-precategories</a>
<a id="3688" class="Keyword">open</a> <a id="3693" class="Keyword">import</a> <a id="3700" href="category-theory.isomorphisms-categories.html" class="Module">category-theory.isomorphisms-categories</a>
<a id="3740" class="Keyword">open</a> <a id="3745" class="Keyword">import</a> <a id="3752" href="category-theory.isomorphisms-large-precategories.html" class="Module">category-theory.isomorphisms-large-precategories</a>
<a id="3801" class="Keyword">open</a> <a id="3806" class="Keyword">import</a> <a id="3813" href="category-theory.isomorphisms-precategories.html" class="Module">category-theory.isomorphisms-precategories</a>
<a id="3856" class="Keyword">open</a> <a id="3861" class="Keyword">import</a> <a id="3868" href="category-theory.large-categories.html" class="Module">category-theory.large-categories</a>
<a id="3901" class="Keyword">open</a> <a id="3906" class="Keyword">import</a> <a id="3913" href="category-theory.large-precategories.html" class="Module">category-theory.large-precategories</a>
<a id="3949" class="Keyword">open</a> <a id="3954" class="Keyword">import</a> <a id="3961" href="category-theory.monomorphisms-large-precategories.html" class="Module">category-theory.monomorphisms-large-precategories</a>
<a id="4011" class="Keyword">open</a> <a id="4016" class="Keyword">import</a> <a id="4023" href="category-theory.natural-isomorphisms-categories.html" class="Module">category-theory.natural-isomorphisms-categories</a>
<a id="4071" class="Keyword">open</a> <a id="4076" class="Keyword">import</a> <a id="4083" href="category-theory.natural-isomorphisms-large-precategories.html" class="Module">category-theory.natural-isomorphisms-large-precategories</a>
<a id="4140" class="Keyword">open</a> <a id="4145" class="Keyword">import</a> <a id="4152" href="category-theory.natural-isomorphisms-precategories.html" class="Module">category-theory.natural-isomorphisms-precategories</a>
<a id="4203" class="Keyword">open</a> <a id="4208" class="Keyword">import</a> <a id="4215" href="category-theory.natural-transformations-categories.html" class="Module">category-theory.natural-transformations-categories</a>
<a id="4266" class="Keyword">open</a> <a id="4271" class="Keyword">import</a> <a id="4278" href="category-theory.natural-transformations-large-precategories.html" class="Module">category-theory.natural-transformations-large-precategories</a>
<a id="4338" class="Keyword">open</a> <a id="4343" class="Keyword">import</a> <a id="4350" href="category-theory.natural-transformations-precategories.html" class="Module">category-theory.natural-transformations-precategories</a>
<a id="4404" class="Keyword">open</a> <a id="4409" class="Keyword">import</a> <a id="4416" href="category-theory.precategories.html" class="Module">category-theory.precategories</a>
<a id="4446" class="Keyword">open</a> <a id="4451" class="Keyword">import</a> <a id="4458" href="category-theory.slice-precategories.html" class="Module">category-theory.slice-precategories</a>
<a id="4494" class="Keyword">open</a> <a id="4499" class="Keyword">import</a> <a id="4506" href="category-theory.terminal-objects-precategories.html" class="Module">category-theory.terminal-objects-precategories</a>
</pre>
## Commutative algebra

<pre class="Agda"><a id="4590" class="Keyword">open</a> <a id="4595" class="Keyword">import</a> <a id="4602" href="commutative-algebra.html" class="Module">commutative-algebra</a>
<a id="4622" class="Keyword">open</a> <a id="4627" class="Keyword">import</a> <a id="4634" href="commutative-algebra.commutative-rings.html" class="Module">commutative-algebra.commutative-rings</a>
<a id="4672" class="Keyword">open</a> <a id="4677" class="Keyword">import</a> <a id="4684" href="commutative-algebra.discrete-fields.html" class="Module">commutative-algebra.discrete-fields</a>
<a id="4720" class="Keyword">open</a> <a id="4725" class="Keyword">import</a> <a id="4732" href="commutative-algebra.eisenstein-integers.html" class="Module">commutative-algebra.eisenstein-integers</a>
<a id="4772" class="Keyword">open</a> <a id="4777" class="Keyword">import</a> <a id="4784" href="commutative-algebra.gaussian-integers.html" class="Module">commutative-algebra.gaussian-integers</a>
<a id="4822" class="Keyword">open</a> <a id="4827" class="Keyword">import</a> <a id="4834" href="commutative-algebra.homomorphisms-commutative-rings.html" class="Module">commutative-algebra.homomorphisms-commutative-rings</a>
<a id="4886" class="Keyword">open</a> <a id="4891" class="Keyword">import</a> <a id="4898" href="commutative-algebra.isomorphisms-commutative-rings.html" class="Module">commutative-algebra.isomorphisms-commutative-rings</a>
</pre>
## Elementary number theory

<pre class="Agda"><a id="4991" class="Keyword">open</a> <a id="4996" class="Keyword">import</a> <a id="5003" href="elementary-number-theory.html" class="Module">elementary-number-theory</a>
<a id="5028" class="Keyword">open</a> <a id="5033" class="Keyword">import</a> <a id="5040" href="elementary-number-theory.absolute-value-integers.html" class="Module">elementary-number-theory.absolute-value-integers</a>
<a id="5089" class="Keyword">open</a> <a id="5094" class="Keyword">import</a> <a id="5101" href="elementary-number-theory.addition-integers.html" class="Module">elementary-number-theory.addition-integers</a>
<a id="5144" class="Keyword">open</a> <a id="5149" class="Keyword">import</a> <a id="5156" href="elementary-number-theory.addition-natural-numbers.html" class="Module">elementary-number-theory.addition-natural-numbers</a>
<a id="5206" class="Keyword">open</a> <a id="5211" class="Keyword">import</a> <a id="5218" href="elementary-number-theory.arithmetic-functions.html" class="Module">elementary-number-theory.arithmetic-functions</a>
<a id="5264" class="Keyword">open</a> <a id="5269" class="Keyword">import</a> <a id="5276" href="elementary-number-theory.binomial-coefficients.html" class="Module">elementary-number-theory.binomial-coefficients</a>
<a id="5323" class="Keyword">open</a> <a id="5328" class="Keyword">import</a> <a id="5335" href="elementary-number-theory.bounded-sums-arithmetic-functions.html" class="Module">elementary-number-theory.bounded-sums-arithmetic-functions</a>
<a id="5394" class="Keyword">open</a> <a id="5399" class="Keyword">import</a> <a id="5406" href="elementary-number-theory.catalan-numbers.html" class="Module">elementary-number-theory.catalan-numbers</a>
<a id="5447" class="Keyword">open</a> <a id="5452" class="Keyword">import</a> <a id="5459" href="elementary-number-theory.collatz-bijection.html" class="Module">elementary-number-theory.collatz-bijection</a>
<a id="5502" class="Keyword">open</a> <a id="5507" class="Keyword">import</a> <a id="5514" href="elementary-number-theory.collatz-conjecture.html" class="Module">elementary-number-theory.collatz-conjecture</a>
<a id="5558" class="Keyword">open</a> <a id="5563" class="Keyword">import</a> <a id="5570" href="elementary-number-theory.congruence-integers.html" class="Module">elementary-number-theory.congruence-integers</a>
<a id="5615" class="Keyword">open</a> <a id="5620" class="Keyword">import</a> <a id="5627" href="elementary-number-theory.congruence-natural-numbers.html" class="Module">elementary-number-theory.congruence-natural-numbers</a>
<a id="5679" class="Keyword">open</a> <a id="5684" class="Keyword">import</a> <a id="5691" href="elementary-number-theory.decidable-dependent-function-types.html" class="Module">elementary-number-theory.decidable-dependent-function-types</a>
<a id="5751" class="Keyword">open</a> <a id="5756" class="Keyword">import</a> <a id="5763" href="elementary-number-theory.decidable-types.html" class="Module">elementary-number-theory.decidable-types</a>
<a id="5804" class="Keyword">open</a> <a id="5809" class="Keyword">import</a> <a id="5816" href="elementary-number-theory.difference-integers.html" class="Module">elementary-number-theory.difference-integers</a>
<a id="5861" class="Keyword">open</a> <a id="5866" class="Keyword">import</a> <a id="5873" href="elementary-number-theory.dirichlet-convolution.html" class="Module">elementary-number-theory.dirichlet-convolution</a>
<a id="5920" class="Keyword">open</a> <a id="5925" class="Keyword">import</a> <a id="5932" href="elementary-number-theory.distance-integers.html" class="Module">elementary-number-theory.distance-integers</a>
<a id="5975" class="Keyword">open</a> <a id="5980" class="Keyword">import</a> <a id="5987" href="elementary-number-theory.distance-natural-numbers.html" class="Module">elementary-number-theory.distance-natural-numbers</a>
<a id="6037" class="Keyword">open</a> <a id="6042" class="Keyword">import</a> <a id="6049" href="elementary-number-theory.divisibility-integers.html" class="Module">elementary-number-theory.divisibility-integers</a>
<a id="6096" class="Keyword">open</a> <a id="6101" class="Keyword">import</a> <a id="6108" href="elementary-number-theory.divisibility-modular-arithmetic.html" class="Module">elementary-number-theory.divisibility-modular-arithmetic</a>
<a id="6165" class="Keyword">open</a> <a id="6170" class="Keyword">import</a> <a id="6177" href="elementary-number-theory.divisibility-natural-numbers.html" class="Module">elementary-number-theory.divisibility-natural-numbers</a>
<a id="6231" class="Keyword">open</a> <a id="6236" class="Keyword">import</a> <a id="6243" href="elementary-number-theory.divisibility-standard-finite-types.html" class="Module">elementary-number-theory.divisibility-standard-finite-types</a>
<a id="6303" class="Keyword">open</a> <a id="6308" class="Keyword">import</a> <a id="6315" href="elementary-number-theory.equality-integers.html" class="Module">elementary-number-theory.equality-integers</a>
<a id="6358" class="Keyword">open</a> <a id="6363" class="Keyword">import</a> <a id="6370" href="elementary-number-theory.equality-natural-numbers.html" class="Module">elementary-number-theory.equality-natural-numbers</a>
<a id="6420" class="Keyword">open</a> <a id="6425" class="Keyword">import</a> <a id="6432" href="elementary-number-theory.euclidean-division-natural-numbers.html" class="Module">elementary-number-theory.euclidean-division-natural-numbers</a>
<a id="6492" class="Keyword">open</a> <a id="6497" class="Keyword">import</a> <a id="6504" href="elementary-number-theory.eulers-totient-function.html" class="Module">elementary-number-theory.eulers-totient-function</a>
<a id="6553" class="Keyword">open</a> <a id="6558" class="Keyword">import</a> <a id="6565" href="elementary-number-theory.exponentiation-natural-numbers.html" class="Module">elementary-number-theory.exponentiation-natural-numbers</a>
<a id="6621" class="Keyword">open</a> <a id="6626" class="Keyword">import</a> <a id="6633" href="elementary-number-theory.factorials.html" class="Module">elementary-number-theory.factorials</a>
<a id="6669" class="Keyword">open</a> <a id="6674" class="Keyword">import</a> <a id="6681" href="elementary-number-theory.falling-factorials.html" class="Module">elementary-number-theory.falling-factorials</a>
<a id="6725" class="Keyword">open</a> <a id="6730" class="Keyword">import</a> <a id="6737" href="elementary-number-theory.fibonacci-sequence.html" class="Module">elementary-number-theory.fibonacci-sequence</a>
<a id="6781" class="Keyword">open</a> <a id="6786" class="Keyword">import</a> <a id="6793" href="elementary-number-theory.finitary-natural-numbers.html" class="Module">elementary-number-theory.finitary-natural-numbers</a>
<a id="6843" class="Keyword">open</a> <a id="6848" class="Keyword">import</a> <a id="6855" href="elementary-number-theory.finitely-cyclic-maps.html" class="Module">elementary-number-theory.finitely-cyclic-maps</a>
<a id="6901" class="Keyword">open</a> <a id="6906" class="Keyword">import</a> <a id="6913" href="elementary-number-theory.fractions.html" class="Module">elementary-number-theory.fractions</a>
<a id="6948" class="Keyword">open</a> <a id="6953" class="Keyword">import</a> <a id="6960" href="elementary-number-theory.goldbach-conjecture.html" class="Module">elementary-number-theory.goldbach-conjecture</a>
<a id="7005" class="Keyword">open</a> <a id="7010" class="Keyword">import</a> <a id="7017" href="elementary-number-theory.greatest-common-divisor-integers.html" class="Module">elementary-number-theory.greatest-common-divisor-integers</a>
<a id="7075" class="Keyword">open</a> <a id="7080" class="Keyword">import</a> <a id="7087" href="elementary-number-theory.greatest-common-divisor-natural-numbers.html" class="Module">elementary-number-theory.greatest-common-divisor-natural-numbers</a>
<a id="7152" class="Keyword">open</a> <a id="7157" class="Keyword">import</a> <a id="7164" href="elementary-number-theory.group-of-integers.html" class="Module">elementary-number-theory.group-of-integers</a>
<a id="7207" class="Keyword">open</a> <a id="7212" class="Keyword">import</a> <a id="7219" href="elementary-number-theory.groups-of-modular-arithmetic.html" class="Module">elementary-number-theory.groups-of-modular-arithmetic</a>
<a id="7273" class="Keyword">open</a> <a id="7278" class="Keyword">import</a> <a id="7285" href="elementary-number-theory.inequality-integers.html" class="Module">elementary-number-theory.inequality-integers</a>
<a id="7330" class="Keyword">open</a> <a id="7335" class="Keyword">import</a> <a id="7342" href="elementary-number-theory.inequality-natural-numbers.html" class="Module">elementary-number-theory.inequality-natural-numbers</a>
<a id="7394" class="Keyword">open</a> <a id="7399" class="Keyword">import</a> <a id="7406" href="elementary-number-theory.inequality-standard-finite-types.html" class="Module">elementary-number-theory.inequality-standard-finite-types</a>
<a id="7464" class="Keyword">open</a> <a id="7469" class="Keyword">import</a> <a id="7476" href="elementary-number-theory.infinitude-of-primes.html" class="Module">elementary-number-theory.infinitude-of-primes</a>
<a id="7522" class="Keyword">open</a> <a id="7527" class="Keyword">import</a> <a id="7534" href="elementary-number-theory.integers.html" class="Module">elementary-number-theory.integers</a>
<a id="7568" class="Keyword">open</a> <a id="7573" class="Keyword">import</a> <a id="7580" href="elementary-number-theory.iterating-functions.html" class="Module">elementary-number-theory.iterating-functions</a>
<a id="7625" class="Keyword">open</a> <a id="7630" class="Keyword">import</a> <a id="7637" href="elementary-number-theory.lower-bounds-natural-numbers.html" class="Module">elementary-number-theory.lower-bounds-natural-numbers</a>
<a id="7691" class="Keyword">open</a> <a id="7696" class="Keyword">import</a> <a id="7703" href="elementary-number-theory.maximum-natural-numbers.html" class="Module">elementary-number-theory.maximum-natural-numbers</a>
<a id="7752" class="Keyword">open</a> <a id="7757" class="Keyword">import</a> <a id="7764" href="elementary-number-theory.mersenne-primes.html" class="Module">elementary-number-theory.mersenne-primes</a>
<a id="7805" class="Keyword">open</a> <a id="7810" class="Keyword">import</a> <a id="7817" href="elementary-number-theory.minimum-natural-numbers.html" class="Module">elementary-number-theory.minimum-natural-numbers</a>
<a id="7866" class="Keyword">open</a> <a id="7871" class="Keyword">import</a> <a id="7878" href="elementary-number-theory.modular-arithmetic-standard-finite-types.html" class="Module">elementary-number-theory.modular-arithmetic-standard-finite-types</a>
<a id="7944" class="Keyword">open</a> <a id="7949" class="Keyword">import</a> <a id="7956" href="elementary-number-theory.modular-arithmetic.html" class="Module">elementary-number-theory.modular-arithmetic</a>
<a id="8000" class="Keyword">open</a> <a id="8005" class="Keyword">import</a> <a id="8012" href="elementary-number-theory.multiplication-integers.html" class="Module">elementary-number-theory.multiplication-integers</a>
<a id="8061" class="Keyword">open</a> <a id="8066" class="Keyword">import</a> <a id="8073" href="elementary-number-theory.multiplication-natural-numbers.html" class="Module">elementary-number-theory.multiplication-natural-numbers</a>
<a id="8129" class="Keyword">open</a> <a id="8134" class="Keyword">import</a> <a id="8141" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a>
<a id="8182" class="Keyword">open</a> <a id="8187" class="Keyword">import</a> <a id="8194" href="elementary-number-theory.nonzero-natural-numbers.html" class="Module">elementary-number-theory.nonzero-natural-numbers</a>
<a id="8243" class="Keyword">open</a> <a id="8248" class="Keyword">import</a> <a id="8255" href="elementary-number-theory.ordinal-induction-natural-numbers.html" class="Module">elementary-number-theory.ordinal-induction-natural-numbers</a>
<a id="8314" class="Keyword">open</a> <a id="8319" class="Keyword">import</a> <a id="8326" href="elementary-number-theory.prime-numbers.html" class="Module">elementary-number-theory.prime-numbers</a>
<a id="8365" class="Keyword">open</a> <a id="8370" class="Keyword">import</a> <a id="8377" href="elementary-number-theory.products-of-natural-numbers.html" class="Module">elementary-number-theory.products-of-natural-numbers</a>
<a id="8430" class="Keyword">open</a> <a id="8435" class="Keyword">import</a> <a id="8442" href="elementary-number-theory.proper-divisors-natural-numbers.html" class="Module">elementary-number-theory.proper-divisors-natural-numbers</a>
<a id="8499" class="Keyword">open</a> <a id="8504" class="Keyword">import</a> <a id="8511" href="elementary-number-theory.rational-numbers.html" class="Module">elementary-number-theory.rational-numbers</a>
<a id="8553" class="Keyword">open</a> <a id="8558" class="Keyword">import</a> <a id="8565" href="elementary-number-theory.relatively-prime-integers.html" class="Module">elementary-number-theory.relatively-prime-integers</a>
<a id="8616" class="Keyword">open</a> <a id="8621" class="Keyword">import</a> <a id="8628" href="elementary-number-theory.relatively-prime-natural-numbers.html" class="Module">elementary-number-theory.relatively-prime-natural-numbers</a>
<a id="8686" class="Keyword">open</a> <a id="8691" class="Keyword">import</a> <a id="8698" href="elementary-number-theory.repeating-element-standard-finite-type.html" class="Module">elementary-number-theory.repeating-element-standard-finite-type</a>
<a id="8762" class="Keyword">open</a> <a id="8767" class="Keyword">import</a> <a id="8774" href="elementary-number-theory.retracts-of-natural-numbers.html" class="Module">elementary-number-theory.retracts-of-natural-numbers</a>
<a id="8827" class="Keyword">open</a> <a id="8832" class="Keyword">import</a> <a id="8839" href="elementary-number-theory.square-free-natural-numbers.html" class="Module">elementary-number-theory.square-free-natural-numbers</a>
<a id="8892" class="Keyword">open</a> <a id="8897" class="Keyword">import</a> <a id="8904" href="elementary-number-theory.stirling-numbers-of-the-second-kind.html" class="Module">elementary-number-theory.stirling-numbers-of-the-second-kind</a>
<a id="8965" class="Keyword">open</a> <a id="8970" class="Keyword">import</a> <a id="8977" href="elementary-number-theory.strong-induction-natural-numbers.html" class="Module">elementary-number-theory.strong-induction-natural-numbers</a>
<a id="9035" class="Keyword">open</a> <a id="9040" class="Keyword">import</a> <a id="9047" href="elementary-number-theory.sums-of-natural-numbers.html" class="Module">elementary-number-theory.sums-of-natural-numbers</a>
<a id="9096" class="Keyword">open</a> <a id="9101" class="Keyword">import</a> <a id="9108" href="elementary-number-theory.triangular-numbers.html" class="Module">elementary-number-theory.triangular-numbers</a>
<a id="9152" class="Keyword">open</a> <a id="9157" class="Keyword">import</a> <a id="9164" href="elementary-number-theory.telephone-numbers.html" class="Module">elementary-number-theory.telephone-numbers</a>
<a id="9207" class="Keyword">open</a> <a id="9212" class="Keyword">import</a> <a id="9219" href="elementary-number-theory.twin-prime-conjecture.html" class="Module">elementary-number-theory.twin-prime-conjecture</a>
<a id="9266" class="Keyword">open</a> <a id="9271" class="Keyword">import</a> <a id="9278" href="elementary-number-theory.unit-elements-standard-finite-types.html" class="Module">elementary-number-theory.unit-elements-standard-finite-types</a>
<a id="9339" class="Keyword">open</a> <a id="9344" class="Keyword">import</a> <a id="9351" href="elementary-number-theory.unit-similarity-standard-finite-types.html" class="Module">elementary-number-theory.unit-similarity-standard-finite-types</a>
<a id="9414" class="Keyword">open</a> <a id="9419" class="Keyword">import</a> <a id="9426" href="elementary-number-theory.universal-property-natural-numbers.html" class="Module">elementary-number-theory.universal-property-natural-numbers</a>
<a id="9486" class="Keyword">open</a> <a id="9491" class="Keyword">import</a> <a id="9498" href="elementary-number-theory.upper-bounds-natural-numbers.html" class="Module">elementary-number-theory.upper-bounds-natural-numbers</a>
<a id="9552" class="Keyword">open</a> <a id="9557" class="Keyword">import</a> <a id="9564" href="elementary-number-theory.well-ordering-principle-natural-numbers.html" class="Module">elementary-number-theory.well-ordering-principle-natural-numbers</a>
<a id="9629" class="Keyword">open</a> <a id="9634" class="Keyword">import</a> <a id="9641" href="elementary-number-theory.well-ordering-principle-standard-finite-types.html" class="Module">elementary-number-theory.well-ordering-principle-standard-finite-types</a>
</pre>
## Finite group theory

<pre class="Agda"><a id="9749" class="Keyword">open</a> <a id="9754" class="Keyword">import</a> <a id="9761" href="finite-group-theory.html" class="Module">finite-group-theory</a>
<a id="9781" class="Keyword">open</a> <a id="9786" class="Keyword">import</a> <a id="9793" href="finite-group-theory.abstract-quaternion-group.html" class="Module">finite-group-theory.abstract-quaternion-group</a>
<a id="9839" class="Keyword">open</a> <a id="9844" class="Keyword">import</a> <a id="9851" href="finite-group-theory.concrete-quaternion-group.html" class="Module">finite-group-theory.concrete-quaternion-group</a>
<a id="9897" class="Keyword">open</a> <a id="9902" class="Keyword">import</a> <a id="9909" href="finite-group-theory.finite-groups.html" class="Module">finite-group-theory.finite-groups</a>
<a id="9943" class="Keyword">open</a> <a id="9948" class="Keyword">import</a> <a id="9955" href="finite-group-theory.finite-monoids.html" class="Module">finite-group-theory.finite-monoids</a>
<a id="9990" class="Keyword">open</a> <a id="9995" class="Keyword">import</a> <a id="10002" href="finite-group-theory.finite-semigroups.html" class="Module">finite-group-theory.finite-semigroups</a>
<a id="10040" class="Keyword">open</a> <a id="10045" class="Keyword">import</a> <a id="10052" href="finite-group-theory.groups-of-order-2.html" class="Module">finite-group-theory.groups-of-order-2</a>
<a id="10090" class="Keyword">open</a> <a id="10095" class="Keyword">import</a> <a id="10102" href="finite-group-theory.orbits-permutations.html" class="Module">finite-group-theory.orbits-permutations</a>
<a id="10142" class="Keyword">open</a> <a id="10147" class="Keyword">import</a> <a id="10154" href="finite-group-theory.permutations.html" class="Module">finite-group-theory.permutations</a>
<a id="10187" class="Keyword">open</a> <a id="10192" class="Keyword">import</a> <a id="10199" href="finite-group-theory.sign-homomorphism.html" class="Module">finite-group-theory.sign-homomorphism</a>
<a id="10237" class="Keyword">open</a> <a id="10242" class="Keyword">import</a> <a id="10249" href="finite-group-theory.transpositions.html" class="Module">finite-group-theory.transpositions</a>
</pre>
## Foundation

<pre class="Agda"><a id="10312" class="Keyword">open</a> <a id="10317" class="Keyword">import</a> <a id="10324" href="foundation.html" class="Module">foundation</a>
<a id="10335" class="Keyword">open</a> <a id="10340" class="Keyword">import</a> <a id="10347" href="foundation.0-maps.html" class="Module">foundation.0-maps</a>
<a id="10365" class="Keyword">open</a> <a id="10370" class="Keyword">import</a> <a id="10377" href="foundation.1-types.html" class="Module">foundation.1-types</a>
<a id="10396" class="Keyword">open</a> <a id="10401" class="Keyword">import</a> <a id="10408" href="foundation.2-types.html" class="Module">foundation.2-types</a>
<a id="10427" class="Keyword">open</a> <a id="10432" class="Keyword">import</a> <a id="10439" href="foundation.algebras-polynomial-endofunctors.html" class="Module">foundation.algebras-polynomial-endofunctors</a>
<a id="10483" class="Keyword">open</a> <a id="10488" class="Keyword">import</a> <a id="10495" href="foundation.automorphisms.html" class="Module">foundation.automorphisms</a>
<a id="10520" class="Keyword">open</a> <a id="10525" class="Keyword">import</a> <a id="10532" href="foundation.axiom-of-choice.html" class="Module">foundation.axiom-of-choice</a>
<a id="10559" class="Keyword">open</a> <a id="10564" class="Keyword">import</a> <a id="10571" href="foundation.binary-embeddings.html" class="Module">foundation.binary-embeddings</a>
<a id="10600" class="Keyword">open</a> <a id="10605" class="Keyword">import</a> <a id="10612" href="foundation.binary-equivalences.html" class="Module">foundation.binary-equivalences</a>
<a id="10643" class="Keyword">open</a> <a id="10648" class="Keyword">import</a> <a id="10655" href="foundation.binary-relations.html" class="Module">foundation.binary-relations</a>
<a id="10683" class="Keyword">open</a> <a id="10688" class="Keyword">import</a> <a id="10695" href="foundation.boolean-reflection.html" class="Module">foundation.boolean-reflection</a>
<a id="10725" class="Keyword">open</a> <a id="10730" class="Keyword">import</a> <a id="10737" href="foundation.booleans.html" class="Module">foundation.booleans</a>
<a id="10757" class="Keyword">open</a> <a id="10762" class="Keyword">import</a> <a id="10769" href="foundation.cantors-diagonal-argument.html" class="Module">foundation.cantors-diagonal-argument</a>
<a id="10806" class="Keyword">open</a> <a id="10811" class="Keyword">import</a> <a id="10818" href="foundation.cartesian-product-types.html" class="Module">foundation.cartesian-product-types</a>
<a id="10853" class="Keyword">open</a> <a id="10858" class="Keyword">import</a> <a id="10865" href="foundation.choice-of-representatives-equivalence-relation.html" class="Module">foundation.choice-of-representatives-equivalence-relation</a>
<a id="10923" class="Keyword">open</a> <a id="10928" class="Keyword">import</a> <a id="10935" href="foundation.coherently-invertible-maps.html" class="Module">foundation.coherently-invertible-maps</a>
<a id="10973" class="Keyword">open</a> <a id="10978" class="Keyword">import</a> <a id="10985" href="foundation.commuting-squares.html" class="Module">foundation.commuting-squares</a>
<a id="11014" class="Keyword">open</a> <a id="11019" class="Keyword">import</a> <a id="11026" href="foundation.complements.html" class="Module">foundation.complements</a>
<a id="11049" class="Keyword">open</a> <a id="11054" class="Keyword">import</a> <a id="11061" href="foundation.conjunction.html" class="Module">foundation.conjunction</a>
<a id="11084" class="Keyword">open</a> <a id="11089" class="Keyword">import</a> <a id="11096" href="foundation.connected-components-universes.html" class="Module">foundation.connected-components-universes</a>
<a id="11138" class="Keyword">open</a> <a id="11143" class="Keyword">import</a> <a id="11150" href="foundation.connected-components.html" class="Module">foundation.connected-components</a>
<a id="11182" class="Keyword">open</a> <a id="11187" class="Keyword">import</a> <a id="11194" href="foundation.connected-types.html" class="Module">foundation.connected-types</a>
<a id="11221" class="Keyword">open</a> <a id="11226" class="Keyword">import</a> <a id="11233" href="foundation.constant-maps.html" class="Module">foundation.constant-maps</a>
<a id="11258" class="Keyword">open</a> <a id="11263" class="Keyword">import</a> <a id="11270" href="foundation.contractible-maps.html" class="Module">foundation.contractible-maps</a>
<a id="11299" class="Keyword">open</a> <a id="11304" class="Keyword">import</a> <a id="11311" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a>
<a id="11341" class="Keyword">open</a> <a id="11346" class="Keyword">import</a> <a id="11353" href="foundation.coproduct-types.html" class="Module">foundation.coproduct-types</a>
<a id="11380" class="Keyword">open</a> <a id="11385" class="Keyword">import</a> <a id="11392" href="foundation.coslice.html" class="Module">foundation.coslice</a>
<a id="11411" class="Keyword">open</a> <a id="11416" class="Keyword">import</a> <a id="11423" href="foundation.decidable-dependent-function-types.html" class="Module">foundation.decidable-dependent-function-types</a>
<a id="11469" class="Keyword">open</a> <a id="11474" class="Keyword">import</a> <a id="11481" href="foundation.decidable-dependent-pair-types.html" class="Module">foundation.decidable-dependent-pair-types</a>
<a id="11523" class="Keyword">open</a> <a id="11528" class="Keyword">import</a> <a id="11535" href="foundation.decidable-embeddings.html" class="Module">foundation.decidable-embeddings</a>
<a id="11567" class="Keyword">open</a> <a id="11572" class="Keyword">import</a> <a id="11579" href="foundation.decidable-equality.html" class="Module">foundation.decidable-equality</a>
<a id="11609" class="Keyword">open</a> <a id="11614" class="Keyword">import</a> <a id="11621" href="foundation.decidable-maps.html" class="Module">foundation.decidable-maps</a>
<a id="11647" class="Keyword">open</a> <a id="11652" class="Keyword">import</a> <a id="11659" href="foundation.decidable-propositions.html" class="Module">foundation.decidable-propositions</a>
<a id="11693" class="Keyword">open</a> <a id="11698" class="Keyword">import</a> <a id="11705" href="foundation.decidable-subtypes.html" class="Module">foundation.decidable-subtypes</a>
<a id="11735" class="Keyword">open</a> <a id="11740" class="Keyword">import</a> <a id="11747" href="foundation.decidable-types.html" class="Module">foundation.decidable-types</a>
<a id="11774" class="Keyword">open</a> <a id="11779" class="Keyword">import</a> <a id="11786" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a>
<a id="11818" class="Keyword">open</a> <a id="11823" class="Keyword">import</a> <a id="11830" href="foundation.diagonal-maps-of-types.html" class="Module">foundation.diagonal-maps-of-types</a>
<a id="11864" class="Keyword">open</a> <a id="11869" class="Keyword">import</a> <a id="11876" href="foundation.disjunction.html" class="Module">foundation.disjunction</a>
<a id="11899" class="Keyword">open</a> <a id="11904" class="Keyword">import</a> <a id="11911" href="foundation.distributivity-of-dependent-functions-over-coproduct-types.html" class="Module">foundation.distributivity-of-dependent-functions-over-coproduct-types</a>
<a id="11981" class="Keyword">open</a> <a id="11986" class="Keyword">import</a> <a id="11993" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html" class="Module">foundation.distributivity-of-dependent-functions-over-dependent-pairs</a>
<a id="12063" class="Keyword">open</a> <a id="12068" class="Keyword">import</a> <a id="12075" href="foundation.double-negation.html" class="Module">foundation.double-negation</a>
<a id="12102" class="Keyword">open</a> <a id="12107" class="Keyword">import</a> <a id="12114" href="foundation.double-powersets.html" class="Module">foundation.double-powersets</a>
<a id="12142" class="Keyword">open</a> <a id="12147" class="Keyword">import</a> <a id="12154" href="foundation.dubuc-penon-compact-types.html" class="Module">foundation.dubuc-penon-compact-types</a>
<a id="12191" class="Keyword">open</a> <a id="12196" class="Keyword">import</a> <a id="12203" href="foundation.effective-maps-equivalence-relations.html" class="Module">foundation.effective-maps-equivalence-relations</a>
<a id="12251" class="Keyword">open</a> <a id="12256" class="Keyword">import</a> <a id="12263" href="foundation.elementhood-relation-w-types.html" class="Module">foundation.elementhood-relation-w-types</a>
<a id="12303" class="Keyword">open</a> <a id="12308" class="Keyword">import</a> <a id="12315" href="foundation.embeddings.html" class="Module">foundation.embeddings</a>
<a id="12337" class="Keyword">open</a> <a id="12342" class="Keyword">import</a> <a id="12349" href="foundation.empty-types.html" class="Module">foundation.empty-types</a>
<a id="12372" class="Keyword">open</a> <a id="12377" class="Keyword">import</a> <a id="12384" href="foundation.epimorphisms-with-respect-to-sets.html" class="Module">foundation.epimorphisms-with-respect-to-sets</a>
<a id="12429" class="Keyword">open</a> <a id="12434" class="Keyword">import</a> <a id="12441" href="foundation.equality-cartesian-product-types.html" class="Module">foundation.equality-cartesian-product-types</a>
<a id="12485" class="Keyword">open</a> <a id="12490" class="Keyword">import</a> <a id="12497" href="foundation.equality-coproduct-types.html" class="Module">foundation.equality-coproduct-types</a>
<a id="12533" class="Keyword">open</a> <a id="12538" class="Keyword">import</a> <a id="12545" href="foundation.equality-dependent-function-types.html" class="Module">foundation.equality-dependent-function-types</a>
<a id="12590" class="Keyword">open</a> <a id="12595" class="Keyword">import</a> <a id="12602" href="foundation.equality-dependent-pair-types.html" class="Module">foundation.equality-dependent-pair-types</a>
<a id="12643" class="Keyword">open</a> <a id="12648" class="Keyword">import</a> <a id="12655" href="foundation.equality-fibers-of-maps.html" class="Module">foundation.equality-fibers-of-maps</a>
<a id="12690" class="Keyword">open</a> <a id="12695" class="Keyword">import</a> <a id="12702" href="foundation.equivalence-classes.html" class="Module">foundation.equivalence-classes</a>
<a id="12733" class="Keyword">open</a> <a id="12738" class="Keyword">import</a> <a id="12745" href="foundation.equivalence-induction.html" class="Module">foundation.equivalence-induction</a>
<a id="12778" class="Keyword">open</a> <a id="12783" class="Keyword">import</a> <a id="12790" href="foundation.equivalence-relations.html" class="Module">foundation.equivalence-relations</a>
<a id="12823" class="Keyword">open</a> <a id="12828" class="Keyword">import</a> <a id="12835" href="foundation.equivalences-maybe.html" class="Module">foundation.equivalences-maybe</a>
<a id="12865" class="Keyword">open</a> <a id="12870" class="Keyword">import</a> <a id="12877" href="foundation.equivalences.html" class="Module">foundation.equivalences</a>
<a id="12901" class="Keyword">open</a> <a id="12906" class="Keyword">import</a> <a id="12913" href="foundation.existential-quantification.html" class="Module">foundation.existential-quantification</a>
<a id="12951" class="Keyword">open</a> <a id="12956" class="Keyword">import</a> <a id="12963" href="foundation.extensional-w-types.html" class="Module">foundation.extensional-w-types</a>
<a id="12994" class="Keyword">open</a> <a id="12999" class="Keyword">import</a> <a id="13006" href="foundation.faithful-maps.html" class="Module">foundation.faithful-maps</a>
<a id="13031" class="Keyword">open</a> <a id="13036" class="Keyword">import</a> <a id="13043" href="foundation.fiber-inclusions.html" class="Module">foundation.fiber-inclusions</a>
<a id="13071" class="Keyword">open</a> <a id="13076" class="Keyword">import</a> <a id="13083" href="foundation.fibered-maps.html" class="Module">foundation.fibered-maps</a>
<a id="13107" class="Keyword">open</a> <a id="13112" class="Keyword">import</a> <a id="13119" href="foundation.fibers-of-maps.html" class="Module">foundation.fibers-of-maps</a>
<a id="13145" class="Keyword">open</a> <a id="13150" class="Keyword">import</a> <a id="13157" href="foundation.function-extensionality.html" class="Module">foundation.function-extensionality</a>
<a id="13192" class="Keyword">open</a> <a id="13197" class="Keyword">import</a> <a id="13204" href="foundation.functions.html" class="Module">foundation.functions</a>
<a id="13225" class="Keyword">open</a> <a id="13230" class="Keyword">import</a> <a id="13237" href="foundation.functoriality-cartesian-product-types.html" class="Module">foundation.functoriality-cartesian-product-types</a>
<a id="13286" class="Keyword">open</a> <a id="13291" class="Keyword">import</a> <a id="13298" href="foundation.functoriality-coproduct-types.html" class="Module">foundation.functoriality-coproduct-types</a>
<a id="13339" class="Keyword">open</a> <a id="13344" class="Keyword">import</a> <a id="13351" href="foundation.functoriality-dependent-function-types.html" class="Module">foundation.functoriality-dependent-function-types</a>
<a id="13401" class="Keyword">open</a> <a id="13406" class="Keyword">import</a> <a id="13413" href="foundation.functoriality-dependent-pair-types.html" class="Module">foundation.functoriality-dependent-pair-types</a>
<a id="13459" class="Keyword">open</a> <a id="13464" class="Keyword">import</a> <a id="13471" href="foundation.functoriality-function-types.html" class="Module">foundation.functoriality-function-types</a>
<a id="13511" class="Keyword">open</a> <a id="13516" class="Keyword">import</a> <a id="13523" href="foundation.functoriality-propositional-truncation.html" class="Module">foundation.functoriality-propositional-truncation</a>
<a id="13573" class="Keyword">open</a> <a id="13578" class="Keyword">import</a> <a id="13585" href="foundation.functoriality-set-quotients.html" class="Module">foundation.functoriality-set-quotients</a>
<a id="13624" class="Keyword">open</a> <a id="13629" class="Keyword">import</a> <a id="13636" href="foundation.functoriality-set-truncation.html" class="Module">foundation.functoriality-set-truncation</a>
<a id="13676" class="Keyword">open</a> <a id="13681" class="Keyword">import</a> <a id="13688" href="foundation.functoriality-w-types.html" class="Module">foundation.functoriality-w-types</a>
<a id="13721" class="Keyword">open</a> <a id="13726" class="Keyword">import</a> <a id="13733" href="foundation.fundamental-theorem-of-identity-types.html" class="Module">foundation.fundamental-theorem-of-identity-types</a>
<a id="13782" class="Keyword">open</a> <a id="13787" class="Keyword">import</a> <a id="13794" href="foundation.global-choice.html" class="Module">foundation.global-choice</a>
<a id="13819" class="Keyword">open</a> <a id="13824" class="Keyword">import</a> <a id="13831" href="foundation.hilberts-epsilon-operators.html" class="Module">foundation.hilberts-epsilon-operators</a>
<a id="13869" class="Keyword">open</a> <a id="13874" class="Keyword">import</a> <a id="13881" href="foundation.homotopies.html" class="Module">foundation.homotopies</a>
<a id="13903" class="Keyword">open</a> <a id="13908" class="Keyword">import</a> <a id="13915" href="foundation.identity-systems.html" class="Module">foundation.identity-systems</a>
<a id="13943" class="Keyword">open</a> <a id="13948" class="Keyword">import</a> <a id="13955" href="foundation.identity-types.html" class="Module">foundation.identity-types</a>
<a id="13981" class="Keyword">open</a> <a id="13986" class="Keyword">import</a> <a id="13993" href="foundation.images.html" class="Module">foundation.images</a>
<a id="14011" class="Keyword">open</a> <a id="14016" class="Keyword">import</a> <a id="14023" href="foundation.impredicative-encodings.html" class="Module">foundation.impredicative-encodings</a>
<a id="14058" class="Keyword">open</a> <a id="14063" class="Keyword">import</a> <a id="14070" href="foundation.indexed-w-types.html" class="Module">foundation.indexed-w-types</a>
<a id="14097" class="Keyword">open</a> <a id="14102" class="Keyword">import</a> <a id="14109" href="foundation.induction-principle-propositional-truncation.html" class="Module">foundation.induction-principle-propositional-truncation</a>
<a id="14165" class="Keyword">open</a> <a id="14170" class="Keyword">import</a> <a id="14177" href="foundation.induction-w-types.html" class="Module">foundation.induction-w-types</a>
<a id="14206" class="Keyword">open</a> <a id="14211" class="Keyword">import</a> <a id="14218" href="foundation.inequality-w-types.html" class="Module">foundation.inequality-w-types</a>
<a id="14248" class="Keyword">open</a> <a id="14253" class="Keyword">import</a> <a id="14260" href="foundation.injective-maps.html" class="Module">foundation.injective-maps</a>
<a id="14286" class="Keyword">open</a> <a id="14291" class="Keyword">import</a> <a id="14298" href="foundation.interchange-law.html" class="Module">foundation.interchange-law</a>
<a id="14325" class="Keyword">open</a> <a id="14330" class="Keyword">import</a> <a id="14337" href="foundation.intersection.html" class="Module">foundation.intersection</a>
<a id="14361" class="Keyword">open</a> <a id="14366" class="Keyword">import</a> <a id="14373" href="foundation.involutions.html" class="Module">foundation.involutions</a>
<a id="14396" class="Keyword">open</a> <a id="14401" class="Keyword">import</a> <a id="14408" href="foundation.isolated-points.html" class="Module">foundation.isolated-points</a>
<a id="14435" class="Keyword">open</a> <a id="14440" class="Keyword">import</a> <a id="14447" href="foundation.isomorphisms-of-sets.html" class="Module">foundation.isomorphisms-of-sets</a>
<a id="14479" class="Keyword">open</a> <a id="14484" class="Keyword">import</a> <a id="14491" href="foundation.law-of-excluded-middle.html" class="Module">foundation.law-of-excluded-middle</a>
<a id="14525" class="Keyword">open</a> <a id="14530" class="Keyword">import</a> <a id="14537" href="foundation.lawveres-fixed-point-theorem.html" class="Module">foundation.lawveres-fixed-point-theorem</a>
<a id="14577" class="Keyword">open</a> <a id="14582" class="Keyword">import</a> <a id="14589" href="foundation.locally-small-types.html" class="Module">foundation.locally-small-types</a>
<a id="14620" class="Keyword">open</a> <a id="14625" class="Keyword">import</a> <a id="14632" href="foundation.logical-equivalences.html" class="Module">foundation.logical-equivalences</a>
<a id="14664" class="Keyword">open</a> <a id="14669" class="Keyword">import</a> <a id="14676" href="foundation.lower-types-w-types.html" class="Module">foundation.lower-types-w-types</a>
<a id="14707" class="Keyword">open</a> <a id="14712" class="Keyword">import</a> <a id="14719" href="foundation.maybe.html" class="Module">foundation.maybe</a>
<a id="14736" class="Keyword">open</a> <a id="14741" class="Keyword">import</a> <a id="14748" href="foundation.mere-equality.html" class="Module">foundation.mere-equality</a>
<a id="14773" class="Keyword">open</a> <a id="14778" class="Keyword">import</a> <a id="14785" href="foundation.mere-equivalences.html" class="Module">foundation.mere-equivalences</a>
<a id="14814" class="Keyword">open</a> <a id="14819" class="Keyword">import</a> <a id="14826" href="foundation.monomorphisms.html" class="Module">foundation.monomorphisms</a>
<a id="14851" class="Keyword">open</a> <a id="14856" class="Keyword">import</a> <a id="14863" href="foundation.multisets.html" class="Module">foundation.multisets</a>
<a id="14884" class="Keyword">open</a> <a id="14889" class="Keyword">import</a> <a id="14896" href="foundation.negation.html" class="Module">foundation.negation</a>
<a id="14916" class="Keyword">open</a> <a id="14921" class="Keyword">import</a> <a id="14928" href="foundation.non-contractible-types.html" class="Module">foundation.non-contractible-types</a>
<a id="14962" class="Keyword">open</a> <a id="14967" class="Keyword">import</a> <a id="14974" href="foundation.pairs-of-distinct-elements.html" class="Module">foundation.pairs-of-distinct-elements</a>
<a id="15012" class="Keyword">open</a> <a id="15017" class="Keyword">import</a> <a id="15024" href="foundation.path-algebra.html" class="Module">foundation.path-algebra</a>
<a id="15048" class="Keyword">open</a> <a id="15053" class="Keyword">import</a> <a id="15060" href="foundation.path-split-maps.html" class="Module">foundation.path-split-maps</a>
<a id="15087" class="Keyword">open</a> <a id="15092" class="Keyword">import</a> <a id="15099" href="foundation.polynomial-endofunctors.html" class="Module">foundation.polynomial-endofunctors</a>
<a id="15134" class="Keyword">open</a> <a id="15139" class="Keyword">import</a> <a id="15146" href="foundation.powersets.html" class="Module">foundation.powersets</a>
<a id="15167" class="Keyword">open</a> <a id="15172" class="Keyword">import</a> <a id="15179" href="foundation.principle-of-omniscience.html" class="Module">foundation.principle-of-omniscience</a>
<a id="15215" class="Keyword">open</a> <a id="15220" class="Keyword">import</a> <a id="15227" href="foundation.propositional-extensionality.html" class="Module">foundation.propositional-extensionality</a>
<a id="15267" class="Keyword">open</a> <a id="15272" class="Keyword">import</a> <a id="15279" href="foundation.propositional-maps.html" class="Module">foundation.propositional-maps</a>
<a id="15309" class="Keyword">open</a> <a id="15314" class="Keyword">import</a> <a id="15321" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a>
<a id="15358" class="Keyword">open</a> <a id="15363" class="Keyword">import</a> <a id="15370" href="foundation.propositions.html" class="Module">foundation.propositions</a>
<a id="15394" class="Keyword">open</a> <a id="15399" class="Keyword">import</a> <a id="15406" href="foundation.pullbacks.html" class="Module">foundation.pullbacks</a>
<a id="15427" class="Keyword">open</a> <a id="15432" class="Keyword">import</a> <a id="15439" href="foundation.raising-universe-levels.html" class="Module">foundation.raising-universe-levels</a>
<a id="15474" class="Keyword">open</a> <a id="15479" class="Keyword">import</a> <a id="15486" href="foundation.ranks-of-elements-w-types.html" class="Module">foundation.ranks-of-elements-w-types</a>
<a id="15523" class="Keyword">open</a> <a id="15528" class="Keyword">import</a> <a id="15535" href="foundation.reflecting-maps-equivalence-relations.html" class="Module">foundation.reflecting-maps-equivalence-relations</a>
<a id="15584" class="Keyword">open</a> <a id="15589" class="Keyword">import</a> <a id="15596" href="foundation.replacement.html" class="Module">foundation.replacement</a>
<a id="15619" class="Keyword">open</a> <a id="15624" class="Keyword">import</a> <a id="15631" href="foundation.retractions.html" class="Module">foundation.retractions</a>
<a id="15654" class="Keyword">open</a> <a id="15659" class="Keyword">import</a> <a id="15666" href="foundation.russells-paradox.html" class="Module">foundation.russells-paradox</a>
<a id="15694" class="Keyword">open</a> <a id="15699" class="Keyword">import</a> <a id="15706" href="foundation.sections.html" class="Module">foundation.sections</a>
<a id="15726" class="Keyword">open</a> <a id="15731" class="Keyword">import</a> <a id="15738" href="foundation.set-presented-types.html" class="Module">foundation.set-presented-types</a>
<a id="15769" class="Keyword">open</a> <a id="15774" class="Keyword">import</a> <a id="15781" href="foundation.set-truncations.html" class="Module">foundation.set-truncations</a>
<a id="15808" class="Keyword">open</a> <a id="15813" class="Keyword">import</a> <a id="15820" href="foundation.sets.html" class="Module">foundation.sets</a>
<a id="15836" class="Keyword">open</a> <a id="15841" class="Keyword">import</a> <a id="15848" href="foundation.singleton-induction.html" class="Module">foundation.singleton-induction</a>
<a id="15879" class="Keyword">open</a> <a id="15884" class="Keyword">import</a> <a id="15891" href="foundation.slice.html" class="Module">foundation.slice</a>
<a id="15908" class="Keyword">open</a> <a id="15913" class="Keyword">import</a> <a id="15920" href="foundation.small-maps.html" class="Module">foundation.small-maps</a>
<a id="15942" class="Keyword">open</a> <a id="15947" class="Keyword">import</a> <a id="15954" href="foundation.small-multisets.html" class="Module">foundation.small-multisets</a>
<a id="15981" class="Keyword">open</a> <a id="15986" class="Keyword">import</a> <a id="15993" href="foundation.small-types.html" class="Module">foundation.small-types</a>
<a id="16016" class="Keyword">open</a> <a id="16021" class="Keyword">import</a> <a id="16028" href="foundation.small-universes.html" class="Module">foundation.small-universes</a>
<a id="16055" class="Keyword">open</a> <a id="16060" class="Keyword">import</a> <a id="16067" href="foundation.split-surjective-maps.html" class="Module">foundation.split-surjective-maps</a>
<a id="16100" class="Keyword">open</a> <a id="16105" class="Keyword">import</a> <a id="16112" href="foundation.structure-identity-principle.html" class="Module">foundation.structure-identity-principle</a>
<a id="16152" class="Keyword">open</a> <a id="16157" class="Keyword">import</a> <a id="16164" href="foundation.structure.html" class="Module">foundation.structure</a>
<a id="16185" class="Keyword">open</a> <a id="16190" class="Keyword">import</a> <a id="16197" href="foundation.subterminal-types.html" class="Module">foundation.subterminal-types</a>
<a id="16226" class="Keyword">open</a> <a id="16231" class="Keyword">import</a> <a id="16238" href="foundation.subtype-identity-principle.html" class="Module">foundation.subtype-identity-principle</a>
<a id="16276" class="Keyword">open</a> <a id="16281" class="Keyword">import</a> <a id="16288" href="foundation.subtypes.html" class="Module">foundation.subtypes</a>
<a id="16308" class="Keyword">open</a> <a id="16313" class="Keyword">import</a> <a id="16320" href="foundation.subuniverses.html" class="Module">foundation.subuniverses</a>
<a id="16344" class="Keyword">open</a> <a id="16349" class="Keyword">import</a> <a id="16356" href="foundation.surjective-maps.html" class="Module">foundation.surjective-maps</a>
<a id="16383" class="Keyword">open</a> <a id="16388" class="Keyword">import</a> <a id="16395" href="foundation.symmetric-difference.html" class="Module">foundation.symmetric-difference</a>
<a id="16427" class="Keyword">open</a> <a id="16432" class="Keyword">import</a> <a id="16439" href="foundation.truncated-equality.html" class="Module">foundation.truncated-equality</a>
<a id="16469" class="Keyword">open</a> <a id="16474" class="Keyword">import</a> <a id="16481" href="foundation.truncated-maps.html" class="Module">foundation.truncated-maps</a>
<a id="16507" class="Keyword">open</a> <a id="16512" class="Keyword">import</a> <a id="16519" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a>
<a id="16546" class="Keyword">open</a> <a id="16551" class="Keyword">import</a> <a id="16558" href="foundation.truncation-levels.html" class="Module">foundation.truncation-levels</a>
<a id="16587" class="Keyword">open</a> <a id="16592" class="Keyword">import</a> <a id="16599" href="foundation.truncations.html" class="Module">foundation.truncations</a>
<a id="16622" class="Keyword">open</a> <a id="16627" class="Keyword">import</a> <a id="16634" href="foundation.type-arithmetic-cartesian-product-types.html" class="Module">foundation.type-arithmetic-cartesian-product-types</a>
<a id="16685" class="Keyword">open</a> <a id="16690" class="Keyword">import</a> <a id="16697" href="foundation.type-arithmetic-coproduct-types.html" class="Module">foundation.type-arithmetic-coproduct-types</a>
<a id="16740" class="Keyword">open</a> <a id="16745" class="Keyword">import</a> <a id="16752" href="foundation.type-arithmetic-dependent-pair-types.html" class="Module">foundation.type-arithmetic-dependent-pair-types</a>
<a id="16800" class="Keyword">open</a> <a id="16805" class="Keyword">import</a> <a id="16812" href="foundation.type-arithmetic-empty-type.html" class="Module">foundation.type-arithmetic-empty-type</a>
<a id="16850" class="Keyword">open</a> <a id="16855" class="Keyword">import</a> <a id="16862" href="foundation.type-arithmetic-unit-type.html" class="Module">foundation.type-arithmetic-unit-type</a>
<a id="16899" class="Keyword">open</a> <a id="16904" class="Keyword">import</a> <a id="16911" href="foundation.uniqueness-image.html" class="Module">foundation.uniqueness-image</a>
<a id="16939" class="Keyword">open</a> <a id="16944" class="Keyword">import</a> <a id="16951" href="foundation.uniqueness-set-quotients.html" class="Module">foundation.uniqueness-set-quotients</a>
<a id="16987" class="Keyword">open</a> <a id="16992" class="Keyword">import</a> <a id="16999" href="foundation.uniqueness-set-truncations.html" class="Module">foundation.uniqueness-set-truncations</a>
<a id="17037" class="Keyword">open</a> <a id="17042" class="Keyword">import</a> <a id="17049" href="foundation.uniqueness-truncation.html" class="Module">foundation.uniqueness-truncation</a>
<a id="17082" class="Keyword">open</a> <a id="17087" class="Keyword">import</a> <a id="17094" href="foundation.unit-type.html" class="Module">foundation.unit-type</a>
<a id="17115" class="Keyword">open</a> <a id="17120" class="Keyword">import</a> <a id="17127" href="foundation.univalence-implies-function-extensionality.html" class="Module">foundation.univalence-implies-function-extensionality</a>
<a id="17181" class="Keyword">open</a> <a id="17186" class="Keyword">import</a> <a id="17193" href="foundation.univalence.html" class="Module">foundation.univalence</a>
<a id="17215" class="Keyword">open</a> <a id="17220" class="Keyword">import</a> <a id="17227" href="foundation.univalent-type-families.html" class="Module">foundation.univalent-type-families</a>
<a id="17262" class="Keyword">open</a> <a id="17267" class="Keyword">import</a> <a id="17274" href="foundation.universal-multiset.html" class="Module">foundation.universal-multiset</a>
<a id="17304" class="Keyword">open</a> <a id="17309" class="Keyword">import</a> <a id="17316" href="foundation.universal-property-booleans.html" class="Module">foundation.universal-property-booleans</a>
<a id="17355" class="Keyword">open</a> <a id="17360" class="Keyword">import</a> <a id="17367" href="foundation.universal-property-cartesian-product-types.html" class="Module">foundation.universal-property-cartesian-product-types</a>
<a id="17421" class="Keyword">open</a> <a id="17426" class="Keyword">import</a> <a id="17433" href="foundation.universal-property-coproduct-types.html" class="Module">foundation.universal-property-coproduct-types</a>
<a id="17479" class="Keyword">open</a> <a id="17484" class="Keyword">import</a> <a id="17491" href="foundation.universal-property-dependent-pair-types.html" class="Module">foundation.universal-property-dependent-pair-types</a>
<a id="17542" class="Keyword">open</a> <a id="17547" class="Keyword">import</a> <a id="17554" href="foundation.universal-property-empty-type.html" class="Module">foundation.universal-property-empty-type</a>
<a id="17595" class="Keyword">open</a> <a id="17600" class="Keyword">import</a> <a id="17607" href="foundation.universal-property-fiber-products.html" class="Module">foundation.universal-property-fiber-products</a>
<a id="17652" class="Keyword">open</a> <a id="17657" class="Keyword">import</a> <a id="17664" href="foundation.universal-property-identity-types.html" class="Module">foundation.universal-property-identity-types</a>
<a id="17709" class="Keyword">open</a> <a id="17714" class="Keyword">import</a> <a id="17721" href="foundation.universal-property-image.html" class="Module">foundation.universal-property-image</a>
<a id="17757" class="Keyword">open</a> <a id="17762" class="Keyword">import</a> <a id="17769" href="foundation.universal-property-maybe.html" class="Module">foundation.universal-property-maybe</a>
<a id="17805" class="Keyword">open</a> <a id="17810" class="Keyword">import</a> <a id="17817" href="foundation.universal-property-propositional-truncation-into-sets.html" class="Module">foundation.universal-property-propositional-truncation-into-sets</a>
<a id="17882" class="Keyword">open</a> <a id="17887" class="Keyword">import</a> <a id="17894" href="foundation.universal-property-propositional-truncation.html" class="Module">foundation.universal-property-propositional-truncation</a>
<a id="17949" class="Keyword">open</a> <a id="17954" class="Keyword">import</a> <a id="17961" href="foundation.universal-property-pullbacks.html" class="Module">foundation.universal-property-pullbacks</a>
<a id="18001" class="Keyword">open</a> <a id="18006" class="Keyword">import</a> <a id="18013" href="foundation.universal-property-set-quotients.html" class="Module">foundation.universal-property-set-quotients</a>
<a id="18057" class="Keyword">open</a> <a id="18062" class="Keyword">import</a> <a id="18069" href="foundation.universal-property-set-truncation.html" class="Module">foundation.universal-property-set-truncation</a>
<a id="18114" class="Keyword">open</a> <a id="18119" class="Keyword">import</a> <a id="18126" href="foundation.universal-property-truncation.html" class="Module">foundation.universal-property-truncation</a>
<a id="18167" class="Keyword">open</a> <a id="18172" class="Keyword">import</a> <a id="18179" href="foundation.universal-property-unit-type.html" class="Module">foundation.universal-property-unit-type</a>
<a id="18219" class="Keyword">open</a> <a id="18224" class="Keyword">import</a> <a id="18231" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a>
<a id="18258" class="Keyword">open</a> <a id="18263" class="Keyword">import</a> <a id="18270" href="foundation.unordered-pairs.html" class="Module">foundation.unordered-pairs</a>
<a id="18297" class="Keyword">open</a> <a id="18302" class="Keyword">import</a> <a id="18309" href="foundation.w-types.html" class="Module">foundation.w-types</a>
<a id="18328" class="Keyword">open</a> <a id="18333" class="Keyword">import</a> <a id="18340" href="foundation.weak-function-extensionality.html" class="Module">foundation.weak-function-extensionality</a>
<a id="18380" class="Keyword">open</a> <a id="18385" class="Keyword">import</a> <a id="18392" href="foundation.weakly-constant-maps.html" class="Module">foundation.weakly-constant-maps</a>
<a id="18424" class="Keyword">open</a> <a id="18429" class="Keyword">import</a> <a id="18436" href="foundation.xor.html" class="Module">foundation.xor</a>
</pre>
## Foundation Core

<pre class="Agda"><a id="18484" class="Keyword">open</a> <a id="18489" class="Keyword">import</a> <a id="18496" href="foundation-core.0-maps.html" class="Module">foundation-core.0-maps</a>
<a id="18519" class="Keyword">open</a> <a id="18524" class="Keyword">import</a> <a id="18531" href="foundation-core.1-types.html" class="Module">foundation-core.1-types</a>
<a id="18555" class="Keyword">open</a> <a id="18560" class="Keyword">import</a> <a id="18567" href="foundation-core.cartesian-product-types.html" class="Module">foundation-core.cartesian-product-types</a>
<a id="18607" class="Keyword">open</a> <a id="18612" class="Keyword">import</a> <a id="18619" href="foundation-core.coherently-invertible-maps.html" class="Module">foundation-core.coherently-invertible-maps</a>
<a id="18662" class="Keyword">open</a> <a id="18667" class="Keyword">import</a> <a id="18674" href="foundation-core.commuting-squares.html" class="Module">foundation-core.commuting-squares</a>
<a id="18708" class="Keyword">open</a> <a id="18713" class="Keyword">import</a> <a id="18720" href="foundation-core.constant-maps.html" class="Module">foundation-core.constant-maps</a>
<a id="18750" class="Keyword">open</a> <a id="18755" class="Keyword">import</a> <a id="18762" href="foundation-core.contractible-maps.html" class="Module">foundation-core.contractible-maps</a>
<a id="18796" class="Keyword">open</a> <a id="18801" class="Keyword">import</a> <a id="18808" href="foundation-core.contractible-types.html" class="Module">foundation-core.contractible-types</a>
<a id="18843" class="Keyword">open</a> <a id="18848" class="Keyword">import</a> <a id="18855" href="foundation-core.dependent-pair-types.html" class="Module">foundation-core.dependent-pair-types</a>
<a id="18892" class="Keyword">open</a> <a id="18897" class="Keyword">import</a> <a id="18904" href="foundation-core.embeddings.html" class="Module">foundation-core.embeddings</a>
<a id="18931" class="Keyword">open</a> <a id="18936" class="Keyword">import</a> <a id="18943" href="foundation-core.empty-types.html" class="Module">foundation-core.empty-types</a>
<a id="18971" class="Keyword">open</a> <a id="18976" class="Keyword">import</a> <a id="18983" href="foundation-core.equality-cartesian-product-types.html" class="Module">foundation-core.equality-cartesian-product-types</a>
<a id="19032" class="Keyword">open</a> <a id="19037" class="Keyword">import</a> <a id="19044" href="foundation-core.equality-dependent-pair-types.html" class="Module">foundation-core.equality-dependent-pair-types</a>
<a id="19090" class="Keyword">open</a> <a id="19095" class="Keyword">import</a> <a id="19102" href="foundation-core.equality-fibers-of-maps.html" class="Module">foundation-core.equality-fibers-of-maps</a>
<a id="19142" class="Keyword">open</a> <a id="19147" class="Keyword">import</a> <a id="19154" href="foundation-core.equivalence-induction.html" class="Module">foundation-core.equivalence-induction</a>
<a id="19192" class="Keyword">open</a> <a id="19197" class="Keyword">import</a> <a id="19204" href="foundation-core.equivalences.html" class="Module">foundation-core.equivalences</a>
<a id="19233" class="Keyword">open</a> <a id="19238" class="Keyword">import</a> <a id="19245" href="foundation-core.faithful-maps.html" class="Module">foundation-core.faithful-maps</a>
<a id="19275" class="Keyword">open</a> <a id="19280" class="Keyword">import</a> <a id="19287" href="foundation-core.fibers-of-maps.html" class="Module">foundation-core.fibers-of-maps</a>
<a id="19318" class="Keyword">open</a> <a id="19323" class="Keyword">import</a> <a id="19330" href="foundation-core.functions.html" class="Module">foundation-core.functions</a>
<a id="19356" class="Keyword">open</a> <a id="19361" class="Keyword">import</a> <a id="19368" href="foundation-core.functoriality-dependent-pair-types.html" class="Module">foundation-core.functoriality-dependent-pair-types</a>
<a id="19419" class="Keyword">open</a> <a id="19424" class="Keyword">import</a> <a id="19431" href="foundation-core.fundamental-theorem-of-identity-types.html" class="Module">foundation-core.fundamental-theorem-of-identity-types</a>
<a id="19485" class="Keyword">open</a> <a id="19490" class="Keyword">import</a> <a id="19497" href="foundation-core.homotopies.html" class="Module">foundation-core.homotopies</a>
<a id="19524" class="Keyword">open</a> <a id="19529" class="Keyword">import</a> <a id="19536" href="foundation-core.identity-systems.html" class="Module">foundation-core.identity-systems</a>
<a id="19569" class="Keyword">open</a> <a id="19574" class="Keyword">import</a> <a id="19581" href="foundation-core.identity-types.html" class="Module">foundation-core.identity-types</a>
<a id="19612" class="Keyword">open</a> <a id="19617" class="Keyword">import</a> <a id="19624" href="foundation-core.logical-equivalences.html" class="Module">foundation-core.logical-equivalences</a>
<a id="19661" class="Keyword">open</a> <a id="19666" class="Keyword">import</a> <a id="19673" href="foundation-core.negation.html" class="Module">foundation-core.negation</a>
<a id="19698" class="Keyword">open</a> <a id="19703" class="Keyword">import</a> <a id="19710" href="foundation-core.path-split-maps.html" class="Module">foundation-core.path-split-maps</a>
<a id="19742" class="Keyword">open</a> <a id="19747" class="Keyword">import</a> <a id="19754" href="foundation-core.propositional-maps.html" class="Module">foundation-core.propositional-maps</a>
<a id="19789" class="Keyword">open</a> <a id="19794" class="Keyword">import</a> <a id="19801" href="foundation-core.propositions.html" class="Module">foundation-core.propositions</a>
<a id="19830" class="Keyword">open</a> <a id="19835" class="Keyword">import</a> <a id="19842" href="foundation-core.retractions.html" class="Module">foundation-core.retractions</a>
<a id="19870" class="Keyword">open</a> <a id="19875" class="Keyword">import</a> <a id="19882" href="foundation-core.sections.html" class="Module">foundation-core.sections</a>
<a id="19907" class="Keyword">open</a> <a id="19912" class="Keyword">import</a> <a id="19919" href="foundation-core.sets.html" class="Module">foundation-core.sets</a>
<a id="19940" class="Keyword">open</a> <a id="19945" class="Keyword">import</a> <a id="19952" href="foundation-core.singleton-induction.html" class="Module">foundation-core.singleton-induction</a>
<a id="19988" class="Keyword">open</a> <a id="19993" class="Keyword">import</a> <a id="20000" href="foundation-core.subtype-identity-principle.html" class="Module">foundation-core.subtype-identity-principle</a>
<a id="20043" class="Keyword">open</a> <a id="20048" class="Keyword">import</a> <a id="20055" href="foundation-core.subtypes.html" class="Module">foundation-core.subtypes</a>
<a id="20080" class="Keyword">open</a> <a id="20085" class="Keyword">import</a> <a id="20092" href="foundation-core.truncated-maps.html" class="Module">foundation-core.truncated-maps</a>
<a id="20123" class="Keyword">open</a> <a id="20128" class="Keyword">import</a> <a id="20135" href="foundation-core.truncated-types.html" class="Module">foundation-core.truncated-types</a>
<a id="20167" class="Keyword">open</a> <a id="20172" class="Keyword">import</a> <a id="20179" href="foundation-core.truncation-levels.html" class="Module">foundation-core.truncation-levels</a>
<a id="20213" class="Keyword">open</a> <a id="20218" class="Keyword">import</a> <a id="20225" href="foundation-core.type-arithmetic-cartesian-product-types.html" class="Module">foundation-core.type-arithmetic-cartesian-product-types</a>
<a id="20281" class="Keyword">open</a> <a id="20286" class="Keyword">import</a> <a id="20293" href="foundation-core.type-arithmetic-dependent-pair-types.html" class="Module">foundation-core.type-arithmetic-dependent-pair-types</a>
<a id="20346" class="Keyword">open</a> <a id="20351" class="Keyword">import</a> <a id="20358" href="foundation-core.univalence.html" class="Module">foundation-core.univalence</a>
<a id="20385" class="Keyword">open</a> <a id="20390" class="Keyword">import</a> <a id="20397" href="foundation-core.universe-levels.html" class="Module">foundation-core.universe-levels</a>
</pre>
## Graph theory

<pre class="Agda"><a id="20459" class="Keyword">open</a> <a id="20464" class="Keyword">import</a> <a id="20471" href="graph-theory.html" class="Module">graph-theory</a>
<a id="20484" class="Keyword">open</a> <a id="20489" class="Keyword">import</a> <a id="20496" href="graph-theory.connected-undirected-graphs.html" class="Module">graph-theory.connected-undirected-graphs</a>
<a id="20537" class="Keyword">open</a> <a id="20542" class="Keyword">import</a> <a id="20549" href="graph-theory.directed-graphs.html" class="Module">graph-theory.directed-graphs</a>
<a id="20578" class="Keyword">open</a> <a id="20583" class="Keyword">import</a> <a id="20590" href="graph-theory.edge-coloured-undirected-graphs.html" class="Module">graph-theory.edge-coloured-undirected-graphs</a>
<a id="20635" class="Keyword">open</a> <a id="20640" class="Keyword">import</a> <a id="20647" href="graph-theory.equivalences-undirected-graphs.html" class="Module">graph-theory.equivalences-undirected-graphs</a>
<a id="20691" class="Keyword">open</a> <a id="20696" class="Keyword">import</a> <a id="20703" href="graph-theory.finite-graphs.html" class="Module">graph-theory.finite-graphs</a>
<a id="20730" class="Keyword">open</a> <a id="20735" class="Keyword">import</a> <a id="20742" href="graph-theory.incidence-undirected-graphs.html" class="Module">graph-theory.incidence-undirected-graphs</a>
<a id="20783" class="Keyword">open</a> <a id="20788" class="Keyword">import</a> <a id="20795" href="graph-theory.matchings.html" class="Module">graph-theory.matchings</a>
<a id="20818" class="Keyword">open</a> <a id="20823" class="Keyword">import</a> <a id="20830" href="graph-theory.mere-equivalences-undirected-graphs.html" class="Module">graph-theory.mere-equivalences-undirected-graphs</a>
<a id="20879" class="Keyword">open</a> <a id="20884" class="Keyword">import</a> <a id="20891" href="graph-theory.morphisms-directed-graphs.html" class="Module">graph-theory.morphisms-directed-graphs</a>
<a id="20930" class="Keyword">open</a> <a id="20935" class="Keyword">import</a> <a id="20942" href="graph-theory.morphisms-undirected-graphs.html" class="Module">graph-theory.morphisms-undirected-graphs</a>
<a id="20983" class="Keyword">open</a> <a id="20988" class="Keyword">import</a> <a id="20995" href="graph-theory.orientations-undirected-graphs.html" class="Module">graph-theory.orientations-undirected-graphs</a>
<a id="21039" class="Keyword">open</a> <a id="21044" class="Keyword">import</a> <a id="21051" href="graph-theory.paths-undirected-graphs.html" class="Module">graph-theory.paths-undirected-graphs</a>
<a id="21088" class="Keyword">open</a> <a id="21093" class="Keyword">import</a> <a id="21100" href="graph-theory.polygons.html" class="Module">graph-theory.polygons</a>
<a id="21122" class="Keyword">open</a> <a id="21127" class="Keyword">import</a> <a id="21134" href="graph-theory.reflexive-graphs.html" class="Module">graph-theory.reflexive-graphs</a>
<a id="21164" class="Keyword">open</a> <a id="21169" class="Keyword">import</a> <a id="21176" href="graph-theory.regular-undirected-graphs.html" class="Module">graph-theory.regular-undirected-graphs</a>
<a id="21215" class="Keyword">open</a> <a id="21220" class="Keyword">import</a> <a id="21227" href="graph-theory.simple-undirected-graphs.html" class="Module">graph-theory.simple-undirected-graphs</a>
<a id="21265" class="Keyword">open</a> <a id="21270" class="Keyword">import</a> <a id="21277" href="graph-theory.undirected-graphs.html" class="Module">graph-theory.undirected-graphs</a>
<a id="21308" class="Keyword">open</a> <a id="21313" class="Keyword">import</a> <a id="21320" href="graph-theory.voltage-graphs.html" class="Module">graph-theory.voltage-graphs</a>
</pre>
## Group theory

<pre class="Agda"><a id="21378" class="Keyword">open</a> <a id="21383" class="Keyword">import</a> <a id="21390" href="group-theory.html" class="Module">group-theory</a>
<a id="21403" class="Keyword">open</a> <a id="21408" class="Keyword">import</a> <a id="21415" href="group-theory.abelian-groups.html" class="Module">group-theory.abelian-groups</a>
<a id="21443" class="Keyword">open</a> <a id="21448" class="Keyword">import</a> <a id="21455" href="group-theory.abelian-subgroups.html" class="Module">group-theory.abelian-subgroups</a>
<a id="21486" class="Keyword">open</a> <a id="21491" class="Keyword">import</a> <a id="21498" href="group-theory.abstract-group-torsors.html" class="Module">group-theory.abstract-group-torsors</a>
<a id="21534" class="Keyword">open</a> <a id="21539" class="Keyword">import</a> <a id="21546" href="group-theory.addition-homomorphisms-abelian-groups.html" class="Module">group-theory.addition-homomorphisms-abelian-groups</a>
<a id="21597" class="Keyword">open</a> <a id="21602" class="Keyword">import</a> <a id="21609" href="group-theory.automorphism-groups.html" class="Module">group-theory.automorphism-groups</a>
<a id="21642" class="Keyword">open</a> <a id="21647" class="Keyword">import</a> <a id="21654" href="group-theory.category-of-groups.html" class="Module">group-theory.category-of-groups</a>
<a id="21686" class="Keyword">open</a> <a id="21691" class="Keyword">import</a> <a id="21698" href="group-theory.category-of-semigroups.html" class="Module">group-theory.category-of-semigroups</a>
<a id="21734" class="Keyword">open</a> <a id="21739" class="Keyword">import</a> <a id="21746" href="group-theory.cayleys-theorem.html" class="Module">group-theory.cayleys-theorem</a>
<a id="21775" class="Keyword">open</a> <a id="21780" class="Keyword">import</a> <a id="21787" href="group-theory.concrete-group-actions.html" class="Module">group-theory.concrete-group-actions</a>
<a id="21823" class="Keyword">open</a> <a id="21828" class="Keyword">import</a> <a id="21835" href="group-theory.concrete-groups.html" class="Module">group-theory.concrete-groups</a>
<a id="21864" class="Keyword">open</a> <a id="21869" class="Keyword">import</a> <a id="21876" href="group-theory.concrete-subgroups.html" class="Module">group-theory.concrete-subgroups</a>
<a id="21908" class="Keyword">open</a> <a id="21913" class="Keyword">import</a> <a id="21920" href="group-theory.conjugation.html" class="Module">group-theory.conjugation</a>
<a id="21945" class="Keyword">open</a> <a id="21950" class="Keyword">import</a> <a id="21957" href="group-theory.embeddings-groups.html" class="Module">group-theory.embeddings-groups</a>
<a id="21988" class="Keyword">open</a> <a id="21993" class="Keyword">import</a> <a id="22000" href="group-theory.endomorphism-rings-abelian-groups.html" class="Module">group-theory.endomorphism-rings-abelian-groups</a>
<a id="22047" class="Keyword">open</a> <a id="22052" class="Keyword">import</a> <a id="22059" href="group-theory.equivalences-group-actions.html" class="Module">group-theory.equivalences-group-actions</a>
<a id="22099" class="Keyword">open</a> <a id="22104" class="Keyword">import</a> <a id="22111" href="group-theory.equivalences-semigroups.html" class="Module">group-theory.equivalences-semigroups</a>
<a id="22148" class="Keyword">open</a> <a id="22153" class="Keyword">import</a> <a id="22160" href="group-theory.examples-higher-groups.html" class="Module">group-theory.examples-higher-groups</a>
<a id="22196" class="Keyword">open</a> <a id="22201" class="Keyword">import</a> <a id="22208" href="group-theory.furstenberg-groups.html" class="Module">group-theory.furstenberg-groups</a>
<a id="22240" class="Keyword">open</a> <a id="22245" class="Keyword">import</a> <a id="22252" href="group-theory.group-actions.html" class="Module">group-theory.group-actions</a>
<a id="22279" class="Keyword">open</a> <a id="22284" class="Keyword">import</a> <a id="22291" href="group-theory.groups.html" class="Module">group-theory.groups</a>
<a id="22311" class="Keyword">open</a> <a id="22316" class="Keyword">import</a> <a id="22323" href="group-theory.higher-groups.html" class="Module">group-theory.higher-groups</a>
<a id="22350" class="Keyword">open</a> <a id="22355" class="Keyword">import</a> <a id="22362" href="group-theory.homomorphisms-abelian-groups.html" class="Module">group-theory.homomorphisms-abelian-groups</a>
<a id="22404" class="Keyword">open</a> <a id="22409" class="Keyword">import</a> <a id="22416" href="group-theory.homomorphisms-group-actions.html" class="Module">group-theory.homomorphisms-group-actions</a>
<a id="22457" class="Keyword">open</a> <a id="22462" class="Keyword">import</a> <a id="22469" href="group-theory.homomorphisms-groups.html" class="Module">group-theory.homomorphisms-groups</a>
<a id="22503" class="Keyword">open</a> <a id="22508" class="Keyword">import</a> <a id="22515" href="group-theory.homomorphisms-monoids.html" class="Module">group-theory.homomorphisms-monoids</a>
<a id="22550" class="Keyword">open</a> <a id="22555" class="Keyword">import</a> <a id="22562" href="group-theory.homomorphisms-semigroups.html" class="Module">group-theory.homomorphisms-semigroups</a>
<a id="22600" class="Keyword">open</a> <a id="22605" class="Keyword">import</a> <a id="22612" href="group-theory.inverse-semigroups.html" class="Module">group-theory.inverse-semigroups</a>
<a id="22644" class="Keyword">open</a> <a id="22649" class="Keyword">import</a> <a id="22656" href="group-theory.invertible-elements-monoids.html" class="Module">group-theory.invertible-elements-monoids</a>
<a id="22697" class="Keyword">open</a> <a id="22702" class="Keyword">import</a> <a id="22709" href="group-theory.isomorphisms-abelian-groups.html" class="Module">group-theory.isomorphisms-abelian-groups</a>
<a id="22750" class="Keyword">open</a> <a id="22755" class="Keyword">import</a> <a id="22762" href="group-theory.isomorphisms-group-actions.html" class="Module">group-theory.isomorphisms-group-actions</a>
<a id="22802" class="Keyword">open</a> <a id="22807" class="Keyword">import</a> <a id="22814" href="group-theory.isomorphisms-groups.html" class="Module">group-theory.isomorphisms-groups</a>
<a id="22847" class="Keyword">open</a> <a id="22852" class="Keyword">import</a> <a id="22859" href="group-theory.isomorphisms-semigroups.html" class="Module">group-theory.isomorphisms-semigroups</a>
<a id="22896" class="Keyword">open</a> <a id="22901" class="Keyword">import</a> <a id="22908" href="group-theory.mere-equivalences-group-actions.html" class="Module">group-theory.mere-equivalences-group-actions</a>
<a id="22953" class="Keyword">open</a> <a id="22958" class="Keyword">import</a> <a id="22965" href="group-theory.monoids.html" class="Module">group-theory.monoids</a>
<a id="22986" class="Keyword">open</a> <a id="22991" class="Keyword">import</a> <a id="22998" href="group-theory.orbits-group-actions.html" class="Module">group-theory.orbits-group-actions</a>
<a id="23032" class="Keyword">open</a> <a id="23037" class="Keyword">import</a> <a id="23044" href="group-theory.precategory-of-group-actions.html" class="Module">group-theory.precategory-of-group-actions</a>
<a id="23086" class="Keyword">open</a> <a id="23091" class="Keyword">import</a> <a id="23098" href="group-theory.precategory-of-groups.html" class="Module">group-theory.precategory-of-groups</a>
<a id="23133" class="Keyword">open</a> <a id="23138" class="Keyword">import</a> <a id="23145" href="group-theory.precategory-of-semigroups.html" class="Module">group-theory.precategory-of-semigroups</a>
<a id="23184" class="Keyword">open</a> <a id="23189" class="Keyword">import</a> <a id="23196" href="group-theory.principal-group-actions.html" class="Module">group-theory.principal-group-actions</a>
<a id="23233" class="Keyword">open</a> <a id="23238" class="Keyword">import</a> <a id="23245" href="group-theory.semigroups.html" class="Module">group-theory.semigroups</a>
<a id="23269" class="Keyword">open</a> <a id="23274" class="Keyword">import</a> <a id="23281" href="group-theory.sheargroups.html" class="Module">group-theory.sheargroups</a>
<a id="23306" class="Keyword">open</a> <a id="23311" class="Keyword">import</a> <a id="23318" href="group-theory.stabilizer-groups.html" class="Module">group-theory.stabilizer-groups</a>
<a id="23349" class="Keyword">open</a> <a id="23354" class="Keyword">import</a> <a id="23361" href="group-theory.subgroups.html" class="Module">group-theory.subgroups</a>
<a id="23384" class="Keyword">open</a> <a id="23389" class="Keyword">import</a> <a id="23396" href="group-theory.substitution-functor-group-actions.html" class="Module">group-theory.substitution-functor-group-actions</a>
<a id="23444" class="Keyword">open</a> <a id="23449" class="Keyword">import</a> <a id="23456" href="group-theory.symmetric-groups.html" class="Module">group-theory.symmetric-groups</a>
<a id="23486" class="Keyword">open</a> <a id="23491" class="Keyword">import</a> <a id="23498" href="group-theory.transitive-group-actions.html" class="Module">group-theory.transitive-group-actions</a>
</pre>
## Linear algebra

<pre class="Agda"><a id="23568" class="Keyword">open</a> <a id="23573" class="Keyword">import</a> <a id="23580" href="linear-algebra.html" class="Module">linear-algebra</a>
<a id="23595" class="Keyword">open</a> <a id="23600" class="Keyword">import</a> <a id="23607" href="linear-algebra.constant-matrices.html" class="Module">linear-algebra.constant-matrices</a>
<a id="23640" class="Keyword">open</a> <a id="23645" class="Keyword">import</a> <a id="23652" href="linear-algebra.constant-vectors.html" class="Module">linear-algebra.constant-vectors</a>
<a id="23684" class="Keyword">open</a> <a id="23689" class="Keyword">import</a> <a id="23696" href="linear-algebra.diagonal-matrices-on-rings.html" class="Module">linear-algebra.diagonal-matrices-on-rings</a>
<a id="23738" class="Keyword">open</a> <a id="23743" class="Keyword">import</a> <a id="23750" href="linear-algebra.functoriality-matrices.html" class="Module">linear-algebra.functoriality-matrices</a>
<a id="23788" class="Keyword">open</a> <a id="23793" class="Keyword">import</a> <a id="23800" href="linear-algebra.functoriality-vectors.html" class="Module">linear-algebra.functoriality-vectors</a>
<a id="23837" class="Keyword">open</a> <a id="23842" class="Keyword">import</a> <a id="23849" href="linear-algebra.matrices-on-rings.html" class="Module">linear-algebra.matrices-on-rings</a>
<a id="23882" class="Keyword">open</a> <a id="23887" class="Keyword">import</a> <a id="23894" href="linear-algebra.matrices.html" class="Module">linear-algebra.matrices</a>
<a id="23918" class="Keyword">open</a> <a id="23923" class="Keyword">import</a> <a id="23930" href="linear-algebra.multiplication-matrices.html" class="Module">linear-algebra.multiplication-matrices</a>
<a id="23969" class="Keyword">open</a> <a id="23974" class="Keyword">import</a> <a id="23981" href="linear-algebra.scalar-multiplication-matrices.html" class="Module">linear-algebra.scalar-multiplication-matrices</a>
<a id="24027" class="Keyword">open</a> <a id="24032" class="Keyword">import</a> <a id="24039" href="linear-algebra.scalar-multiplication-vectors.html" class="Module">linear-algebra.scalar-multiplication-vectors</a>
<a id="24084" class="Keyword">open</a> <a id="24089" class="Keyword">import</a> <a id="24096" href="linear-algebra.transposition-matrices.html" class="Module">linear-algebra.transposition-matrices</a>
<a id="24134" class="Keyword">open</a> <a id="24139" class="Keyword">import</a> <a id="24146" href="linear-algebra.vectors-on-rings.html" class="Module">linear-algebra.vectors-on-rings</a>
<a id="24178" class="Keyword">open</a> <a id="24183" class="Keyword">import</a> <a id="24190" href="linear-algebra.vectors.html" class="Module">linear-algebra.vectors</a>
</pre>
## Order theory

<pre class="Agda"><a id="24243" class="Keyword">open</a> <a id="24248" class="Keyword">import</a> <a id="24255" href="order-theory.html" class="Module">order-theory</a>
<a id="24268" class="Keyword">open</a> <a id="24273" class="Keyword">import</a> <a id="24280" href="order-theory.chains-posets.html" class="Module">order-theory.chains-posets</a>
<a id="24307" class="Keyword">open</a> <a id="24312" class="Keyword">import</a> <a id="24319" href="order-theory.chains-preorders.html" class="Module">order-theory.chains-preorders</a>
<a id="24349" class="Keyword">open</a> <a id="24354" class="Keyword">import</a> <a id="24361" href="order-theory.decidable-subposets.html" class="Module">order-theory.decidable-subposets</a>
<a id="24394" class="Keyword">open</a> <a id="24399" class="Keyword">import</a> <a id="24406" href="order-theory.decidable-subpreorders.html" class="Module">order-theory.decidable-subpreorders</a>
<a id="24442" class="Keyword">open</a> <a id="24447" class="Keyword">import</a> <a id="24454" href="order-theory.finite-posets.html" class="Module">order-theory.finite-posets</a>
<a id="24481" class="Keyword">open</a> <a id="24486" class="Keyword">import</a> <a id="24493" href="order-theory.finite-preorders.html" class="Module">order-theory.finite-preorders</a>
<a id="24523" class="Keyword">open</a> <a id="24528" class="Keyword">import</a> <a id="24535" href="order-theory.finitely-graded-posets.html" class="Module">order-theory.finitely-graded-posets</a>
<a id="24571" class="Keyword">open</a> <a id="24576" class="Keyword">import</a> <a id="24583" href="order-theory.greatest-lower-bounds-posets.html" class="Module">order-theory.greatest-lower-bounds-posets</a>
<a id="24625" class="Keyword">open</a> <a id="24630" class="Keyword">import</a> <a id="24637" href="order-theory.interval-subposets.html" class="Module">order-theory.interval-subposets</a>
<a id="24669" class="Keyword">open</a> <a id="24674" class="Keyword">import</a> <a id="24681" href="order-theory.large-posets.html" class="Module">order-theory.large-posets</a>
<a id="24707" class="Keyword">open</a> <a id="24712" class="Keyword">import</a> <a id="24719" href="order-theory.large-preorders.html" class="Module">order-theory.large-preorders</a>
<a id="24748" class="Keyword">open</a> <a id="24753" class="Keyword">import</a> <a id="24760" href="order-theory.largest-elements-posets.html" class="Module">order-theory.largest-elements-posets</a>
<a id="24797" class="Keyword">open</a> <a id="24802" class="Keyword">import</a> <a id="24809" href="order-theory.largest-elements-preorders.html" class="Module">order-theory.largest-elements-preorders</a>
<a id="24849" class="Keyword">open</a> <a id="24854" class="Keyword">import</a> <a id="24861" href="order-theory.least-elements-posets.html" class="Module">order-theory.least-elements-posets</a>
<a id="24896" class="Keyword">open</a> <a id="24901" class="Keyword">import</a> <a id="24908" href="order-theory.least-elements-preorders.html" class="Module">order-theory.least-elements-preorders</a>
<a id="24946" class="Keyword">open</a> <a id="24951" class="Keyword">import</a> <a id="24958" href="order-theory.locally-finite-posets.html" class="Module">order-theory.locally-finite-posets</a>
<a id="24993" class="Keyword">open</a> <a id="24998" class="Keyword">import</a> <a id="25005" href="order-theory.maximal-chains-posets.html" class="Module">order-theory.maximal-chains-posets</a>
<a id="25040" class="Keyword">open</a> <a id="25045" class="Keyword">import</a> <a id="25052" href="order-theory.maximal-chains-preorders.html" class="Module">order-theory.maximal-chains-preorders</a>
<a id="25090" class="Keyword">open</a> <a id="25095" class="Keyword">import</a> <a id="25102" href="order-theory.meet-semilattices.html" class="Module">order-theory.meet-semilattices</a>
<a id="25133" class="Keyword">open</a> <a id="25138" class="Keyword">import</a> <a id="25145" href="order-theory.planar-binary-trees.html" class="Module">order-theory.planar-binary-trees</a>
<a id="25178" class="Keyword">open</a> <a id="25183" class="Keyword">import</a> <a id="25190" href="order-theory.posets.html" class="Module">order-theory.posets</a>
<a id="25210" class="Keyword">open</a> <a id="25215" class="Keyword">import</a> <a id="25222" href="order-theory.preorders.html" class="Module">order-theory.preorders</a>
<a id="25245" class="Keyword">open</a> <a id="25250" class="Keyword">import</a> <a id="25257" href="order-theory.subposets.html" class="Module">order-theory.subposets</a>
<a id="25280" class="Keyword">open</a> <a id="25285" class="Keyword">import</a> <a id="25292" href="order-theory.subpreorders.html" class="Module">order-theory.subpreorders</a>
<a id="25318" class="Keyword">open</a> <a id="25323" class="Keyword">import</a> <a id="25330" href="order-theory.total-posets.html" class="Module">order-theory.total-posets</a>
<a id="25356" class="Keyword">open</a> <a id="25361" class="Keyword">import</a> <a id="25368" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a>
</pre>
## Polytopes

<pre class="Agda"><a id="25424" class="Keyword">open</a> <a id="25429" class="Keyword">import</a> <a id="25436" href="polytopes.html" class="Module">polytopes</a>
<a id="25446" class="Keyword">open</a> <a id="25451" class="Keyword">import</a> <a id="25458" href="polytopes.abstract-polytopes.html" class="Module">polytopes.abstract-polytopes</a>
</pre>
## Ring theory

<pre class="Agda"><a id="25516" class="Keyword">open</a> <a id="25521" class="Keyword">import</a> <a id="25528" href="ring-theory.html" class="Module">ring-theory</a>
<a id="25540" class="Keyword">open</a> <a id="25545" class="Keyword">import</a> <a id="25552" href="ring-theory.division-rings.html" class="Module">ring-theory.division-rings</a>
<a id="25579" class="Keyword">open</a> <a id="25584" class="Keyword">import</a> <a id="25591" href="ring-theory.homomorphisms-rings.html" class="Module">ring-theory.homomorphisms-rings</a>
<a id="25623" class="Keyword">open</a> <a id="25628" class="Keyword">import</a> <a id="25635" href="ring-theory.ideals-generated-by-subsets-rings.html" class="Module">ring-theory.ideals-generated-by-subsets-rings</a>
<a id="25681" class="Keyword">open</a> <a id="25686" class="Keyword">import</a> <a id="25693" href="ring-theory.ideals-rings.html" class="Module">ring-theory.ideals-rings</a>
<a id="25718" class="Keyword">open</a> <a id="25723" class="Keyword">import</a> <a id="25730" href="ring-theory.invertible-elements-rings.html" class="Module">ring-theory.invertible-elements-rings</a>
<a id="25768" class="Keyword">open</a> <a id="25773" class="Keyword">import</a> <a id="25780" href="ring-theory.isomorphisms-rings.html" class="Module">ring-theory.isomorphisms-rings</a>
<a id="25811" class="Keyword">open</a> <a id="25816" class="Keyword">import</a> <a id="25823" href="ring-theory.localizations-rings.html" class="Module">ring-theory.localizations-rings</a>
<a id="25855" class="Keyword">open</a> <a id="25860" class="Keyword">import</a> <a id="25867" href="ring-theory.nontrivial-rings.html" class="Module">ring-theory.nontrivial-rings</a>
<a id="25896" class="Keyword">open</a> <a id="25901" class="Keyword">import</a> <a id="25908" href="ring-theory.rings.html" class="Module">ring-theory.rings</a>
</pre>
## Synthetic homotopy theory

<pre class="Agda"><a id="25969" class="Keyword">open</a> <a id="25974" class="Keyword">import</a> <a id="25981" href="synthetic-homotopy-theory.html" class="Module">synthetic-homotopy-theory</a>
<a id="26007" class="Keyword">open</a> <a id="26012" class="Keyword">import</a> <a id="26019" href="synthetic-homotopy-theory.23-pullbacks.html" class="Module">synthetic-homotopy-theory.23-pullbacks</a>
<a id="26058" class="Keyword">open</a> <a id="26063" class="Keyword">import</a> <a id="26070" href="synthetic-homotopy-theory.24-pushouts.html" class="Module">synthetic-homotopy-theory.24-pushouts</a>
<a id="26108" class="Keyword">open</a> <a id="26113" class="Keyword">import</a> <a id="26120" href="synthetic-homotopy-theory.25-cubical-diagrams.html" class="Module">synthetic-homotopy-theory.25-cubical-diagrams</a>
<a id="26166" class="Keyword">open</a> <a id="26171" class="Keyword">import</a> <a id="26178" href="synthetic-homotopy-theory.26-descent.html" class="Module">synthetic-homotopy-theory.26-descent</a>
<a id="26215" class="Keyword">open</a> <a id="26220" class="Keyword">import</a> <a id="26227" href="synthetic-homotopy-theory.26-id-pushout.html" class="Module">synthetic-homotopy-theory.26-id-pushout</a>
<a id="26267" class="Keyword">open</a> <a id="26272" class="Keyword">import</a> <a id="26279" href="synthetic-homotopy-theory.27-sequences.html" class="Module">synthetic-homotopy-theory.27-sequences</a>
<a id="26318" class="Keyword">open</a> <a id="26323" class="Keyword">import</a> <a id="26330" href="synthetic-homotopy-theory.circle.html" class="Module">synthetic-homotopy-theory.circle</a>
<a id="26363" class="Keyword">open</a> <a id="26368" class="Keyword">import</a> <a id="26375" href="synthetic-homotopy-theory.commutative-operations.html" class="Module">synthetic-homotopy-theory.commutative-operations</a>
<a id="26424" class="Keyword">open</a> <a id="26429" class="Keyword">import</a> <a id="26436" href="synthetic-homotopy-theory.cyclic-types.html" class="Module">synthetic-homotopy-theory.cyclic-types</a>
<a id="26475" class="Keyword">open</a> <a id="26480" class="Keyword">import</a> <a id="26487" href="synthetic-homotopy-theory.double-loop-spaces.html" class="Module">synthetic-homotopy-theory.double-loop-spaces</a>
<a id="26532" class="Keyword">open</a> <a id="26537" class="Keyword">import</a> <a id="26544" href="synthetic-homotopy-theory.functoriality-loop-spaces.html" class="Module">synthetic-homotopy-theory.functoriality-loop-spaces</a>
<a id="26596" class="Keyword">open</a> <a id="26601" class="Keyword">import</a> <a id="26608" href="synthetic-homotopy-theory.groups-of-loops-in-1-types.html" class="Module">synthetic-homotopy-theory.groups-of-loops-in-1-types</a>
<a id="26661" class="Keyword">open</a> <a id="26666" class="Keyword">import</a> <a id="26673" href="synthetic-homotopy-theory.infinite-cyclic-types.html" class="Module">synthetic-homotopy-theory.infinite-cyclic-types</a>
<a id="26721" class="Keyword">open</a> <a id="26726" class="Keyword">import</a> <a id="26733" href="synthetic-homotopy-theory.interval-type.html" class="Module">synthetic-homotopy-theory.interval-type</a>
<a id="26773" class="Keyword">open</a> <a id="26778" class="Keyword">import</a> <a id="26785" href="synthetic-homotopy-theory.iterated-loop-spaces.html" class="Module">synthetic-homotopy-theory.iterated-loop-spaces</a>
<a id="26832" class="Keyword">open</a> <a id="26837" class="Keyword">import</a> <a id="26844" href="synthetic-homotopy-theory.loop-spaces.html" class="Module">synthetic-homotopy-theory.loop-spaces</a>
<a id="26882" class="Keyword">open</a> <a id="26887" class="Keyword">import</a> <a id="26894" href="synthetic-homotopy-theory.pointed-dependent-functions.html" class="Module">synthetic-homotopy-theory.pointed-dependent-functions</a>
<a id="26948" class="Keyword">open</a> <a id="26953" class="Keyword">import</a> <a id="26960" href="synthetic-homotopy-theory.pointed-equivalences.html" class="Module">synthetic-homotopy-theory.pointed-equivalences</a>
<a id="27007" class="Keyword">open</a> <a id="27012" class="Keyword">import</a> <a id="27019" href="synthetic-homotopy-theory.pointed-families-of-types.html" class="Module">synthetic-homotopy-theory.pointed-families-of-types</a>
<a id="27071" class="Keyword">open</a> <a id="27076" class="Keyword">import</a> <a id="27083" href="synthetic-homotopy-theory.pointed-homotopies.html" class="Module">synthetic-homotopy-theory.pointed-homotopies</a>
<a id="27128" class="Keyword">open</a> <a id="27133" class="Keyword">import</a> <a id="27140" href="synthetic-homotopy-theory.pointed-maps.html" class="Module">synthetic-homotopy-theory.pointed-maps</a>
<a id="27179" class="Keyword">open</a> <a id="27184" class="Keyword">import</a> <a id="27191" href="synthetic-homotopy-theory.pointed-types.html" class="Module">synthetic-homotopy-theory.pointed-types</a>
<a id="27231" class="Keyword">open</a> <a id="27236" class="Keyword">import</a> <a id="27243" href="synthetic-homotopy-theory.spaces.html" class="Module">synthetic-homotopy-theory.spaces</a>
<a id="27276" class="Keyword">open</a> <a id="27281" class="Keyword">import</a> <a id="27288" href="synthetic-homotopy-theory.triple-loop-spaces.html" class="Module">synthetic-homotopy-theory.triple-loop-spaces</a>
<a id="27333" class="Keyword">open</a> <a id="27338" class="Keyword">import</a> <a id="27345" href="synthetic-homotopy-theory.universal-cover-circle.html" class="Module">synthetic-homotopy-theory.universal-cover-circle</a>
</pre>
## Tutorials

<pre class="Agda"><a id="27421" class="Keyword">open</a> <a id="27426" class="Keyword">import</a> <a id="27433" href="tutorials.basic-agda.html" class="Module">tutorials.basic-agda</a>
</pre>
## Type theories

<pre class="Agda"><a id="27485" class="Keyword">open</a> <a id="27490" class="Keyword">import</a> <a id="27497" href="type-theories.html" class="Module">type-theories</a>
<a id="27511" class="Keyword">open</a> <a id="27516" class="Keyword">import</a> <a id="27523" href="type-theories.comprehension-type-theories.html" class="Module">type-theories.comprehension-type-theories</a>
<a id="27565" class="Keyword">open</a> <a id="27570" class="Keyword">import</a> <a id="27577" href="type-theories.dependent-type-theories.html" class="Module">type-theories.dependent-type-theories</a>
<a id="27615" class="Keyword">open</a> <a id="27620" class="Keyword">import</a> <a id="27627" href="type-theories.fibered-dependent-type-theories.html" class="Module">type-theories.fibered-dependent-type-theories</a>
<a id="27673" class="Keyword">open</a> <a id="27678" class="Keyword">import</a> <a id="27685" href="type-theories.sections-dependent-type-theories.html" class="Module">type-theories.sections-dependent-type-theories</a>
<a id="27732" class="Keyword">open</a> <a id="27737" class="Keyword">import</a> <a id="27744" href="type-theories.simple-type-theories.html" class="Module">type-theories.simple-type-theories</a>
<a id="27779" class="Keyword">open</a> <a id="27784" class="Keyword">import</a> <a id="27791" href="type-theories.unityped-type-theories.html" class="Module">type-theories.unityped-type-theories</a>
</pre>
## Univalent combinatorics

<pre class="Agda"><a id="27869" class="Keyword">open</a> <a id="27874" class="Keyword">import</a> <a id="27881" href="univalent-combinatorics.html" class="Module">univalent-combinatorics</a>
<a id="27905" class="Keyword">open</a> <a id="27910" class="Keyword">import</a> <a id="27917" href="univalent-combinatorics.2-element-decidable-subtypes.html" class="Module">univalent-combinatorics.2-element-decidable-subtypes</a>
<a id="27970" class="Keyword">open</a> <a id="27975" class="Keyword">import</a> <a id="27982" href="univalent-combinatorics.2-element-subtypes.html" class="Module">univalent-combinatorics.2-element-subtypes</a>
<a id="28025" class="Keyword">open</a> <a id="28030" class="Keyword">import</a> <a id="28037" href="univalent-combinatorics.2-element-types.html" class="Module">univalent-combinatorics.2-element-types</a>
<a id="28077" class="Keyword">open</a> <a id="28082" class="Keyword">import</a> <a id="28089" href="univalent-combinatorics.binomial-types.html" class="Module">univalent-combinatorics.binomial-types</a>
<a id="28128" class="Keyword">open</a> <a id="28133" class="Keyword">import</a> <a id="28140" href="univalent-combinatorics.cartesian-product-types.html" class="Module">univalent-combinatorics.cartesian-product-types</a>
<a id="28188" class="Keyword">open</a> <a id="28193" class="Keyword">import</a> <a id="28200" href="univalent-combinatorics.classical-finite-types.html" class="Module">univalent-combinatorics.classical-finite-types</a>
<a id="28247" class="Keyword">open</a> <a id="28252" class="Keyword">import</a> <a id="28259" href="univalent-combinatorics.complements-isolated-points.html" class="Module">univalent-combinatorics.complements-isolated-points</a>
<a id="28311" class="Keyword">open</a> <a id="28316" class="Keyword">import</a> <a id="28323" href="univalent-combinatorics.coproduct-types.html" class="Module">univalent-combinatorics.coproduct-types</a>
<a id="28363" class="Keyword">open</a> <a id="28368" class="Keyword">import</a> <a id="28375" href="univalent-combinatorics.counting-decidable-subtypes.html" class="Module">univalent-combinatorics.counting-decidable-subtypes</a>
<a id="28427" class="Keyword">open</a> <a id="28432" class="Keyword">import</a> <a id="28439" href="univalent-combinatorics.counting-dependent-pair-types.html" class="Module">univalent-combinatorics.counting-dependent-pair-types</a>
<a id="28493" class="Keyword">open</a> <a id="28498" class="Keyword">import</a> <a id="28505" href="univalent-combinatorics.counting-maybe.html" class="Module">univalent-combinatorics.counting-maybe</a>
<a id="28544" class="Keyword">open</a> <a id="28549" class="Keyword">import</a> <a id="28556" href="univalent-combinatorics.counting.html" class="Module">univalent-combinatorics.counting</a>
<a id="28589" class="Keyword">open</a> <a id="28594" class="Keyword">import</a> <a id="28601" href="univalent-combinatorics.cubes.html" class="Module">univalent-combinatorics.cubes</a>
<a id="28631" class="Keyword">open</a> <a id="28636" class="Keyword">import</a> <a id="28643" href="univalent-combinatorics.decidable-dependent-function-types.html" class="Module">univalent-combinatorics.decidable-dependent-function-types</a>
<a id="28702" class="Keyword">open</a> <a id="28707" class="Keyword">import</a> <a id="28714" href="univalent-combinatorics.decidable-dependent-pair-types.html" class="Module">univalent-combinatorics.decidable-dependent-pair-types</a>
<a id="28769" class="Keyword">open</a> <a id="28774" class="Keyword">import</a> <a id="28781" href="univalent-combinatorics.decidable-subtypes.html" class="Module">univalent-combinatorics.decidable-subtypes</a>
<a id="28824" class="Keyword">open</a> <a id="28829" class="Keyword">import</a> <a id="28836" href="univalent-combinatorics.dependent-function-types.html" class="Module">univalent-combinatorics.dependent-function-types</a>
<a id="28885" class="Keyword">open</a> <a id="28890" class="Keyword">import</a> <a id="28897" href="univalent-combinatorics.dedekind-finite-sets.html" class="Module">univalent-combinatorics.dedekind-finite-sets</a>
<a id="28942" class="Keyword">open</a> <a id="28947" class="Keyword">import</a> <a id="28954" href="univalent-combinatorics.dependent-sum-finite-types.html" class="Module">univalent-combinatorics.dependent-sum-finite-types</a>
<a id="29005" class="Keyword">open</a> <a id="29010" class="Keyword">import</a> <a id="29017" href="univalent-combinatorics.distributivity-of-set-truncation-over-finite-products.html" class="Module">univalent-combinatorics.distributivity-of-set-truncation-over-finite-products</a>
<a id="29095" class="Keyword">open</a> <a id="29100" class="Keyword">import</a> <a id="29107" href="univalent-combinatorics.double-counting.html" class="Module">univalent-combinatorics.double-counting</a>
<a id="29147" class="Keyword">open</a> <a id="29152" class="Keyword">import</a> <a id="29159" href="univalent-combinatorics.embeddings-standard-finite-types.html" class="Module">univalent-combinatorics.embeddings-standard-finite-types</a>
<a id="29216" class="Keyword">open</a> <a id="29221" class="Keyword">import</a> <a id="29228" href="univalent-combinatorics.embeddings.html" class="Module">univalent-combinatorics.embeddings</a>
<a id="29263" class="Keyword">open</a> <a id="29268" class="Keyword">import</a> <a id="29275" href="univalent-combinatorics.equality-finite-types.html" class="Module">univalent-combinatorics.equality-finite-types</a>
<a id="29321" class="Keyword">open</a> <a id="29326" class="Keyword">import</a> <a id="29333" href="univalent-combinatorics.equality-standard-finite-types.html" class="Module">univalent-combinatorics.equality-standard-finite-types</a>
<a id="29388" class="Keyword">open</a> <a id="29393" class="Keyword">import</a> <a id="29400" href="univalent-combinatorics.equivalences-cubes.html" class="Module">univalent-combinatorics.equivalences-cubes</a>
<a id="29443" class="Keyword">open</a> <a id="29448" class="Keyword">import</a> <a id="29455" href="univalent-combinatorics.equivalences-standard-finite-types.html" class="Module">univalent-combinatorics.equivalences-standard-finite-types</a>
<a id="29514" class="Keyword">open</a> <a id="29519" class="Keyword">import</a> <a id="29526" href="univalent-combinatorics.equivalences.html" class="Module">univalent-combinatorics.equivalences</a>
<a id="29563" class="Keyword">open</a> <a id="29568" class="Keyword">import</a> <a id="29575" href="univalent-combinatorics.fibers-of-maps.html" class="Module">univalent-combinatorics.fibers-of-maps</a>
<a id="29614" class="Keyword">open</a> <a id="29619" class="Keyword">import</a> <a id="29626" href="univalent-combinatorics.finite-choice.html" class="Module">univalent-combinatorics.finite-choice</a>
<a id="29664" class="Keyword">open</a> <a id="29669" class="Keyword">import</a> <a id="29676" href="univalent-combinatorics.finite-connected-components.html" class="Module">univalent-combinatorics.finite-connected-components</a>
<a id="29728" class="Keyword">open</a> <a id="29733" class="Keyword">import</a> <a id="29740" href="univalent-combinatorics.finite-presentations.html" class="Module">univalent-combinatorics.finite-presentations</a>
<a id="29785" class="Keyword">open</a> <a id="29790" class="Keyword">import</a> <a id="29797" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a>
<a id="29834" class="Keyword">open</a> <a id="29839" class="Keyword">import</a> <a id="29846" href="univalent-combinatorics.finitely-presented-types.html" class="Module">univalent-combinatorics.finitely-presented-types</a>
<a id="29895" class="Keyword">open</a> <a id="29900" class="Keyword">import</a> <a id="29907" href="univalent-combinatorics.function-types.html" class="Module">univalent-combinatorics.function-types</a>
<a id="29946" class="Keyword">open</a> <a id="29951" class="Keyword">import</a> <a id="29958" href="univalent-combinatorics.image-of-maps.html" class="Module">univalent-combinatorics.image-of-maps</a>
<a id="29996" class="Keyword">open</a> <a id="30001" class="Keyword">import</a> <a id="30008" href="univalent-combinatorics.inequality-types-with-counting.html" class="Module">univalent-combinatorics.inequality-types-with-counting</a>
<a id="30063" class="Keyword">open</a> <a id="30068" class="Keyword">import</a> <a id="30075" href="univalent-combinatorics.injective-maps.html" class="Module">univalent-combinatorics.injective-maps</a>
<a id="30114" class="Keyword">open</a> <a id="30119" class="Keyword">import</a> <a id="30126" href="univalent-combinatorics.kuratowsky-finite-sets.html" class="Module">univalent-combinatorics.kuratowsky-finite-sets</a>
<a id="30173" class="Keyword">open</a> <a id="30178" class="Keyword">import</a> <a id="30185" href="univalent-combinatorics.lists.html" class="Module">univalent-combinatorics.lists</a>
<a id="30215" class="Keyword">open</a> <a id="30220" class="Keyword">import</a> <a id="30227" href="univalent-combinatorics.maybe.html" class="Module">univalent-combinatorics.maybe</a>
<a id="30257" class="Keyword">open</a> <a id="30262" class="Keyword">import</a> <a id="30269" href="univalent-combinatorics.orientations-complete-undirected-graph.html" class="Module">univalent-combinatorics.orientations-complete-undirected-graph</a>
<a id="30332" class="Keyword">open</a> <a id="30337" class="Keyword">import</a> <a id="30344" href="univalent-combinatorics.orientations-cubes.html" class="Module">univalent-combinatorics.orientations-cubes</a>
<a id="30387" class="Keyword">open</a> <a id="30392" class="Keyword">import</a> <a id="30399" href="univalent-combinatorics.petri-nets.html" class="Module">univalent-combinatorics.petri-nets</a>
<a id="30434" class="Keyword">open</a> <a id="30439" class="Keyword">import</a> <a id="30446" href="univalent-combinatorics.pi-finite-types.html" class="Module">univalent-combinatorics.pi-finite-types</a>
<a id="30486" class="Keyword">open</a> <a id="30491" class="Keyword">import</a> <a id="30498" href="univalent-combinatorics.pigeonhole-principle.html" class="Module">univalent-combinatorics.pigeonhole-principle</a>
<a id="30543" class="Keyword">open</a> <a id="30548" class="Keyword">import</a> <a id="30555" href="univalent-combinatorics.presented-pi-finite-types.html" class="Module">univalent-combinatorics.presented-pi-finite-types</a>
<a id="30605" class="Keyword">open</a> <a id="30610" class="Keyword">import</a> <a id="30617" href="univalent-combinatorics.ramsey-theory.html" class="Module">univalent-combinatorics.ramsey-theory</a>
<a id="30655" class="Keyword">open</a> <a id="30660" class="Keyword">import</a> <a id="30667" href="univalent-combinatorics.retracts-of-finite-types.html" class="Module">univalent-combinatorics.retracts-of-finite-types</a>
<a id="30716" class="Keyword">open</a> <a id="30721" class="Keyword">import</a> <a id="30728" href="univalent-combinatorics.skipping-element-standard-finite-types.html" class="Module">univalent-combinatorics.skipping-element-standard-finite-types</a>
<a id="30791" class="Keyword">open</a> <a id="30796" class="Keyword">import</a> <a id="30803" href="univalent-combinatorics.species.html" class="Module">univalent-combinatorics.species</a>
<a id="30835" class="Keyword">open</a> <a id="30840" class="Keyword">import</a> <a id="30847" href="univalent-combinatorics.standard-finite-pruned-trees.html" class="Module">univalent-combinatorics.standard-finite-pruned-trees</a>
<a id="30900" class="Keyword">open</a> <a id="30905" class="Keyword">import</a> <a id="30912" href="univalent-combinatorics.standard-finite-trees.html" class="Module">univalent-combinatorics.standard-finite-trees</a>
<a id="30958" class="Keyword">open</a> <a id="30963" class="Keyword">import</a> <a id="30970" href="univalent-combinatorics.standard-finite-types.html" class="Module">univalent-combinatorics.standard-finite-types</a>
<a id="31016" class="Keyword">open</a> <a id="31021" class="Keyword">import</a> <a id="31028" href="univalent-combinatorics.sums-of-natural-numbers.html" class="Module">univalent-combinatorics.sums-of-natural-numbers</a>
<a id="31076" class="Keyword">open</a> <a id="31081" class="Keyword">import</a> <a id="31088" href="univalent-combinatorics.surjective-maps.html" class="Module">univalent-combinatorics.surjective-maps</a>
<a id="31128" class="Keyword">open</a> <a id="31133" class="Keyword">import</a> <a id="31140" href="univalent-combinatorics.symmetric-difference.html" class="Module">univalent-combinatorics.symmetric-difference</a>
</pre>
## Wild algebra

<pre class="Agda"><a id="31215" class="Keyword">open</a> <a id="31220" class="Keyword">import</a> <a id="31227" href="wild-algebra.html" class="Module">wild-algebra</a>
<a id="31240" class="Keyword">open</a> <a id="31245" class="Keyword">import</a> <a id="31252" href="wild-algebra.magmas.html" class="Module">wild-algebra.magmas</a>
<a id="31272" class="Keyword">open</a> <a id="31277" class="Keyword">import</a> <a id="31284" href="wild-algebra.morphisms-magmas.html" class="Module">wild-algebra.morphisms-magmas</a>
<a id="31314" class="Keyword">open</a> <a id="31319" class="Keyword">import</a> <a id="31326" href="wild-algebra.morphisms-wild-unital-magmas.html" class="Module">wild-algebra.morphisms-wild-unital-magmas</a>
<a id="31368" class="Keyword">open</a> <a id="31373" class="Keyword">import</a> <a id="31380" href="wild-algebra.universal-property-lists-wild-monoids.html" class="Module">wild-algebra.universal-property-lists-wild-monoids</a>
<a id="31431" class="Keyword">open</a> <a id="31436" class="Keyword">import</a> <a id="31443" href="wild-algebra.wild-groups.html" class="Module">wild-algebra.wild-groups</a>
<a id="31468" class="Keyword">open</a> <a id="31473" class="Keyword">import</a> <a id="31480" href="wild-algebra.wild-loops.html" class="Module">wild-algebra.wild-loops</a>
<a id="31504" class="Keyword">open</a> <a id="31509" class="Keyword">import</a> <a id="31516" href="wild-algebra.wild-monoids.html" class="Module">wild-algebra.wild-monoids</a>
<a id="31542" class="Keyword">open</a> <a id="31547" class="Keyword">import</a> <a id="31554" href="wild-algebra.wild-quasigroups.html" class="Module">wild-algebra.wild-quasigroups</a>
<a id="31584" class="Keyword">open</a> <a id="31589" class="Keyword">import</a> <a id="31596" href="wild-algebra.wild-semigroups.html" class="Module">wild-algebra.wild-semigroups</a>
<a id="31625" class="Keyword">open</a> <a id="31630" class="Keyword">import</a> <a id="31637" href="wild-algebra.wild-unital-magmas.html" class="Module">wild-algebra.wild-unital-magmas</a>
</pre>
## Everything

See the list of all Agda modules [here](everything.html).

