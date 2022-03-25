---
title: Formalisation of the Symmetry Book
---

<pre class="Agda"><a id="60" class="Symbol">{-#</a> <a id="64" class="Keyword">OPTIONS</a> <a id="72" class="Pragma">--without-K</a> <a id="84" class="Pragma">--exact-split</a> <a id="98" class="Symbol">#-}</a>

<a id="103" class="Keyword">module</a> <a id="110" href="group-theory.examples-higher-groups.html" class="Module">group-theory.examples-higher-groups</a> <a id="146" class="Keyword">where</a>

<a id="153" class="Keyword">open</a> <a id="158" class="Keyword">import</a> <a id="165" href="foundation.connected-components-universes.html" class="Module">foundation.connected-components-universes</a>
<a id="207" class="Keyword">open</a> <a id="212" class="Keyword">import</a> <a id="219" href="foundation.connected-types.html" class="Module">foundation.connected-types</a>
<a id="246" class="Keyword">open</a> <a id="251" class="Keyword">import</a> <a id="258" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a>
<a id="290" class="Keyword">open</a> <a id="295" class="Keyword">import</a> <a id="302" href="foundation.mere-equivalences.html" class="Module">foundation.mere-equivalences</a>
<a id="331" class="Keyword">open</a> <a id="336" class="Keyword">import</a> <a id="343" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a>

<a id="371" class="Keyword">open</a> <a id="376" class="Keyword">import</a> <a id="383" href="group-theory.higher-groups.html" class="Module">group-theory.higher-groups</a>

<a id="411" class="Keyword">open</a> <a id="416" class="Keyword">import</a> <a id="423" href="synthetic-homotopy-theory.circle.html" class="Module">synthetic-homotopy-theory.circle</a>
<a id="456" class="Keyword">open</a> <a id="461" class="Keyword">import</a> <a id="468" href="synthetic-homotopy-theory.pointed-types.html" class="Module">synthetic-homotopy-theory.pointed-types</a>
</pre>
<pre class="Agda"><a id="521" class="Keyword">module</a> <a id="528" href="group-theory.examples-higher-groups.html#528" class="Module">_</a>
  <a id="532" class="Keyword">where</a>

  <a id="541" href="group-theory.examples-higher-groups.html#541" class="Function">classifying-type-ℤ-∞-Group</a> <a id="568" class="Symbol">:</a> <a id="570" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="573" href="Agda.Primitive.html#764" class="Primitive">lzero</a>
  <a id="581" href="group-theory.examples-higher-groups.html#541" class="Function">classifying-type-ℤ-∞-Group</a> <a id="608" class="Symbol">=</a> <a id="610" href="synthetic-homotopy-theory.circle.html#12175" class="Postulate">𝕊¹</a>

  <a id="616" href="group-theory.examples-higher-groups.html#616" class="Function">shape-ℤ-∞-Group</a> <a id="632" class="Symbol">:</a> <a id="634" href="synthetic-homotopy-theory.circle.html#12175" class="Postulate">𝕊¹</a>
  <a id="639" href="group-theory.examples-higher-groups.html#616" class="Function">shape-ℤ-∞-Group</a> <a id="655" class="Symbol">=</a> <a id="657" href="synthetic-homotopy-theory.circle.html#12200" class="Postulate">base-𝕊¹</a>

  <a id="668" href="group-theory.examples-higher-groups.html#668" class="Function">classifying-pointed-type-ℤ-∞-Group</a> <a id="703" class="Symbol">:</a> <a id="705" href="synthetic-homotopy-theory.pointed-types.html#392" class="Function">Pointed-Type</a> <a id="718" href="Agda.Primitive.html#764" class="Primitive">lzero</a>
  <a id="726" href="group-theory.examples-higher-groups.html#668" class="Function">classifying-pointed-type-ℤ-∞-Group</a> <a id="761" class="Symbol">=</a>
    <a id="767" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a>
      <a id="778" href="group-theory.examples-higher-groups.html#541" class="Function">classifying-type-ℤ-∞-Group</a>
      <a id="811" href="group-theory.examples-higher-groups.html#616" class="Function">shape-ℤ-∞-Group</a>

  <a id="830" href="group-theory.examples-higher-groups.html#830" class="Function">ℤ-∞-Group</a> <a id="840" class="Symbol">:</a> <a id="842" href="group-theory.higher-groups.html#1500" class="Function">∞-Group</a> <a id="850" href="Agda.Primitive.html#764" class="Primitive">lzero</a>
  <a id="858" href="group-theory.examples-higher-groups.html#830" class="Function">ℤ-∞-Group</a> <a id="868" class="Symbol">=</a>
    <a id="874" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a>
      <a id="885" href="group-theory.examples-higher-groups.html#668" class="Function">classifying-pointed-type-ℤ-∞-Group</a>
      <a id="926" href="synthetic-homotopy-theory.circle.html#19693" class="Function">is-path-connected-𝕊¹</a>

<a id="948" class="Keyword">module</a> <a id="955" href="group-theory.examples-higher-groups.html#955" class="Module">_</a>
  <a id="959" class="Symbol">{</a><a id="960" href="group-theory.examples-higher-groups.html#960" class="Bound">l</a> <a id="962" class="Symbol">:</a> <a id="964" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="969" class="Symbol">}</a> <a id="971" class="Symbol">(</a><a id="972" href="group-theory.examples-higher-groups.html#972" class="Bound">X</a> <a id="974" class="Symbol">:</a> <a id="976" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="979" href="group-theory.examples-higher-groups.html#960" class="Bound">l</a><a id="980" class="Symbol">)</a>
  <a id="984" class="Keyword">where</a>

  <a id="993" href="group-theory.examples-higher-groups.html#993" class="Function">classifying-type-symmetric-∞-Group</a> <a id="1028" class="Symbol">:</a> <a id="1030" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1033" class="Symbol">(</a><a id="1034" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="1039" href="group-theory.examples-higher-groups.html#960" class="Bound">l</a><a id="1040" class="Symbol">)</a>
  <a id="1044" href="group-theory.examples-higher-groups.html#993" class="Function">classifying-type-symmetric-∞-Group</a> <a id="1079" class="Symbol">=</a> <a id="1081" href="foundation.connected-components-universes.html#2310" class="Function">component-UU</a> <a id="1094" href="group-theory.examples-higher-groups.html#972" class="Bound">X</a>

  <a id="1099" href="group-theory.examples-higher-groups.html#1099" class="Function">shape-symmetric-∞-Group</a> <a id="1123" class="Symbol">:</a> <a id="1125" href="group-theory.examples-higher-groups.html#993" class="Function">classifying-type-symmetric-∞-Group</a>
  <a id="1162" href="group-theory.examples-higher-groups.html#1099" class="Function">shape-symmetric-∞-Group</a> <a id="1186" class="Symbol">=</a>
    <a id="1192" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1197" href="group-theory.examples-higher-groups.html#972" class="Bound">X</a> <a id="1199" class="Symbol">(</a><a id="1200" href="foundation.mere-equivalences.html#1762" class="Function">refl-mere-equiv</a> <a id="1216" href="group-theory.examples-higher-groups.html#972" class="Bound">X</a><a id="1217" class="Symbol">)</a>

  <a id="1222" href="group-theory.examples-higher-groups.html#1222" class="Function">classifying-pointed-type-symmetric-∞-Group</a> <a id="1265" class="Symbol">:</a> <a id="1267" href="synthetic-homotopy-theory.pointed-types.html#392" class="Function">Pointed-Type</a> <a id="1280" class="Symbol">(</a><a id="1281" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="1286" href="group-theory.examples-higher-groups.html#960" class="Bound">l</a><a id="1287" class="Symbol">)</a>
  <a id="1291" href="group-theory.examples-higher-groups.html#1222" class="Function">classifying-pointed-type-symmetric-∞-Group</a> <a id="1334" class="Symbol">=</a>
    <a id="1340" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a>
      <a id="1351" href="group-theory.examples-higher-groups.html#993" class="Function">classifying-type-symmetric-∞-Group</a>
      <a id="1392" href="group-theory.examples-higher-groups.html#1099" class="Function">shape-symmetric-∞-Group</a>

  <a id="1419" href="group-theory.examples-higher-groups.html#1419" class="Function">is-path-connected-classifying-type-symmetric-∞-Group</a> <a id="1472" class="Symbol">:</a>
    <a id="1478" href="foundation.connected-types.html#1682" class="Function">is-path-connected</a> <a id="1496" href="group-theory.examples-higher-groups.html#993" class="Function">classifying-type-symmetric-∞-Group</a>
  <a id="1533" href="group-theory.examples-higher-groups.html#1419" class="Function">is-path-connected-classifying-type-symmetric-∞-Group</a> <a id="1586" class="Symbol">=</a>
    <a id="1592" href="foundation.connected-components-universes.html#6383" class="Function">is-path-connected-component-UU</a> <a id="1623" href="group-theory.examples-higher-groups.html#972" class="Bound">X</a>
  
  <a id="1630" href="group-theory.examples-higher-groups.html#1630" class="Function">symmetric-∞-Group</a> <a id="1648" class="Symbol">:</a> <a id="1650" href="group-theory.higher-groups.html#1500" class="Function">∞-Group</a> <a id="1658" class="Symbol">(</a><a id="1659" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="1664" href="group-theory.examples-higher-groups.html#960" class="Bound">l</a><a id="1665" class="Symbol">)</a>
  <a id="1669" href="group-theory.examples-higher-groups.html#1630" class="Function">symmetric-∞-Group</a> <a id="1687" class="Symbol">=</a>
    <a id="1693" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a>
      <a id="1704" href="group-theory.examples-higher-groups.html#1222" class="Function">classifying-pointed-type-symmetric-∞-Group</a>
      <a id="1753" href="group-theory.examples-higher-groups.html#1419" class="Function">is-path-connected-classifying-type-symmetric-∞-Group</a>
</pre>