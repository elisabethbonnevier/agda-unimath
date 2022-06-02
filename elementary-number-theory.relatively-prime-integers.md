# Relatively prime integers

<pre class="Agda"><a id="38" class="Symbol">{-#</a> <a id="42" class="Keyword">OPTIONS</a> <a id="50" class="Pragma">--without-K</a> <a id="62" class="Pragma">--exact-split</a> <a id="76" class="Symbol">#-}</a>

<a id="81" class="Keyword">module</a> <a id="88" href="elementary-number-theory.relatively-prime-integers.html" class="Module">elementary-number-theory.relatively-prime-integers</a> <a id="139" class="Keyword">where</a>

<a id="146" class="Keyword">open</a> <a id="151" class="Keyword">import</a> <a id="158" href="elementary-number-theory.greatest-common-divisor-integers.html" class="Module">elementary-number-theory.greatest-common-divisor-integers</a> <a id="216" class="Keyword">using</a>
  <a id="224" class="Symbol">(</a> <a id="226" href="elementary-number-theory.greatest-common-divisor-integers.html#4655" class="Function">gcd-ℤ</a><a id="231" class="Symbol">)</a>
<a id="233" class="Keyword">open</a> <a id="238" class="Keyword">import</a> <a id="245" href="elementary-number-theory.integers.html" class="Module">elementary-number-theory.integers</a> <a id="279" class="Keyword">using</a> <a id="285" class="Symbol">(</a><a id="286" href="elementary-number-theory.integers.html#1867" class="Function">ℤ</a><a id="287" class="Symbol">;</a> <a id="289" href="elementary-number-theory.integers.html#2393" class="Function">is-one-ℤ</a><a id="297" class="Symbol">)</a>

<a id="300" class="Keyword">open</a> <a id="305" class="Keyword">import</a> <a id="312" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="339" class="Keyword">using</a> <a id="345" class="Symbol">(</a><a id="346" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="348" class="Symbol">;</a> <a id="350" href="Agda.Primitive.html#764" class="Primitive">lzero</a><a id="355" class="Symbol">)</a>
</pre>
## Idea

Two integers are said to be relatively prime if their greatest common divisor is 1.

## Definition

<pre class="Agda"><a id="is-relative-prime-ℤ"></a><a id="479" href="elementary-number-theory.relatively-prime-integers.html#479" class="Function">is-relative-prime-ℤ</a> <a id="499" class="Symbol">:</a> <a id="501" href="elementary-number-theory.integers.html#1867" class="Function">ℤ</a> <a id="503" class="Symbol">→</a> <a id="505" href="elementary-number-theory.integers.html#1867" class="Function">ℤ</a> <a id="507" class="Symbol">→</a> <a id="509" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="512" href="Agda.Primitive.html#764" class="Primitive">lzero</a>
<a id="518" href="elementary-number-theory.relatively-prime-integers.html#479" class="Function">is-relative-prime-ℤ</a> <a id="538" href="elementary-number-theory.relatively-prime-integers.html#538" class="Bound">x</a> <a id="540" href="elementary-number-theory.relatively-prime-integers.html#540" class="Bound">y</a> <a id="542" class="Symbol">=</a> <a id="544" href="elementary-number-theory.integers.html#2393" class="Function">is-one-ℤ</a> <a id="553" class="Symbol">(</a><a id="554" href="elementary-number-theory.greatest-common-divisor-integers.html#4655" class="Function">gcd-ℤ</a> <a id="560" href="elementary-number-theory.relatively-prime-integers.html#538" class="Bound">x</a> <a id="562" href="elementary-number-theory.relatively-prime-integers.html#540" class="Bound">y</a><a id="563" class="Symbol">)</a>
</pre>
## Properties