---
title: Decidable subtypes of finite types
---

<pre class="Agda"><a id="60" class="Symbol">{-#</a> <a id="64" class="Keyword">OPTIONS</a> <a id="72" class="Pragma">--without-K</a> <a id="84" class="Pragma">--exact-split</a> <a id="98" class="Symbol">#-}</a>

<a id="103" class="Keyword">module</a> <a id="110" href="univalent-combinatorics.decidable-subtypes.html" class="Module">univalent-combinatorics.decidable-subtypes</a> <a id="153" class="Keyword">where</a>

<a id="160" class="Keyword">open</a> <a id="165" class="Keyword">import</a> <a id="172" href="foundation.decidable-subtypes.html" class="Module">foundation.decidable-subtypes</a> <a id="202" class="Keyword">public</a>

<a id="210" class="Keyword">open</a> <a id="215" class="Keyword">import</a> <a id="222" href="foundation.decidable-propositions.html" class="Module">foundation.decidable-propositions</a> <a id="256" class="Keyword">using</a>
  <a id="264" class="Symbol">(</a> <a id="266" href="foundation.decidable-propositions.html#2022" class="Function">prop-decidable-Prop</a><a id="285" class="Symbol">;</a> <a id="287" href="foundation.decidable-propositions.html#2361" class="Function">is-decidable-type-decidable-Prop</a><a id="319" class="Symbol">)</a>
<a id="321" class="Keyword">open</a> <a id="326" class="Keyword">import</a> <a id="333" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="360" class="Keyword">using</a> <a id="366" class="Symbol">(</a><a id="367" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="372" class="Symbol">;</a> <a id="374" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="376" class="Symbol">)</a>

<a id="379" class="Keyword">open</a> <a id="384" class="Keyword">import</a> <a id="391" href="univalent-combinatorics.dependent-sum-finite-types.html" class="Module">univalent-combinatorics.dependent-sum-finite-types</a> <a id="442" class="Keyword">using</a>
  <a id="450" class="Symbol">(</a> <a id="452" href="univalent-combinatorics.dependent-sum-finite-types.html#2485" class="Function">is-finite-Σ</a><a id="463" class="Symbol">)</a>
<a id="465" class="Keyword">open</a> <a id="470" class="Keyword">import</a> <a id="477" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a> <a id="514" class="Keyword">using</a>
  <a id="522" class="Symbol">(</a> <a id="524" href="univalent-combinatorics.finite-types.html#3664" class="Function">is-finite</a><a id="533" class="Symbol">;</a> <a id="535" href="univalent-combinatorics.finite-types.html#8470" class="Function">is-finite-is-decidable-Prop</a><a id="562" class="Symbol">)</a>
</pre>
## Idea

Decidable subtypes of finite types are finite.

## Properties

<pre class="Agda"><a id="649" class="Keyword">module</a> <a id="656" href="univalent-combinatorics.decidable-subtypes.html#656" class="Module">_</a>
  <a id="660" class="Symbol">{</a><a id="661" href="univalent-combinatorics.decidable-subtypes.html#661" class="Bound">l1</a> <a id="664" href="univalent-combinatorics.decidable-subtypes.html#664" class="Bound">l2</a> <a id="667" class="Symbol">:</a> <a id="669" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="674" class="Symbol">}</a> <a id="676" class="Symbol">{</a><a id="677" href="univalent-combinatorics.decidable-subtypes.html#677" class="Bound">X</a> <a id="679" class="Symbol">:</a> <a id="681" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="684" href="univalent-combinatorics.decidable-subtypes.html#661" class="Bound">l1</a><a id="686" class="Symbol">}</a> <a id="688" class="Symbol">(</a><a id="689" href="univalent-combinatorics.decidable-subtypes.html#689" class="Bound">P</a> <a id="691" class="Symbol">:</a> <a id="693" href="foundation.decidable-subtypes.html#857" class="Function">decidable-subtype</a> <a id="711" href="univalent-combinatorics.decidable-subtypes.html#664" class="Bound">l2</a> <a id="714" href="univalent-combinatorics.decidable-subtypes.html#677" class="Bound">X</a><a id="715" class="Symbol">)</a>
  <a id="719" class="Keyword">where</a>

  <a id="728" class="Keyword">abstract</a>
    <a id="741" href="univalent-combinatorics.decidable-subtypes.html#741" class="Function">is-finite-decidable-subtype</a> <a id="769" class="Symbol">:</a>
      <a id="777" href="univalent-combinatorics.finite-types.html#3664" class="Function">is-finite</a> <a id="787" href="univalent-combinatorics.decidable-subtypes.html#677" class="Bound">X</a> <a id="789" class="Symbol">→</a> <a id="791" href="univalent-combinatorics.finite-types.html#3664" class="Function">is-finite</a> <a id="801" class="Symbol">(</a><a id="802" href="foundation.decidable-subtypes.html#1756" class="Function">type-decidable-subtype</a> <a id="825" href="univalent-combinatorics.decidable-subtypes.html#689" class="Bound">P</a><a id="826" class="Symbol">)</a>
    <a id="832" href="univalent-combinatorics.decidable-subtypes.html#741" class="Function">is-finite-decidable-subtype</a> <a id="860" href="univalent-combinatorics.decidable-subtypes.html#860" class="Bound">H</a> <a id="862" class="Symbol">=</a>
      <a id="870" href="univalent-combinatorics.dependent-sum-finite-types.html#2485" class="Function">is-finite-Σ</a> <a id="882" href="univalent-combinatorics.decidable-subtypes.html#860" class="Bound">H</a>
        <a id="892" class="Symbol">(</a> <a id="894" class="Symbol">λ</a> <a id="896" href="univalent-combinatorics.decidable-subtypes.html#896" class="Bound">x</a> <a id="898" class="Symbol">→</a>
          <a id="910" href="univalent-combinatorics.finite-types.html#8470" class="Function">is-finite-is-decidable-Prop</a>
            <a id="950" class="Symbol">(</a> <a id="952" href="foundation.decidable-propositions.html#2022" class="Function">prop-decidable-Prop</a> <a id="972" class="Symbol">(</a><a id="973" href="univalent-combinatorics.decidable-subtypes.html#689" class="Bound">P</a> <a id="975" href="univalent-combinatorics.decidable-subtypes.html#896" class="Bound">x</a><a id="976" class="Symbol">))</a>
            <a id="991" class="Symbol">(</a> <a id="993" href="foundation.decidable-propositions.html#2361" class="Function">is-decidable-type-decidable-Prop</a> <a id="1026" class="Symbol">(</a><a id="1027" href="univalent-combinatorics.decidable-subtypes.html#689" class="Bound">P</a> <a id="1029" href="univalent-combinatorics.decidable-subtypes.html#896" class="Bound">x</a><a id="1030" class="Symbol">)))</a>
</pre>