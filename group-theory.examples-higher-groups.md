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

<a id="411" class="Keyword">open</a> <a id="416" class="Keyword">import</a> <a id="423" href="structured-types.pointed-types.html" class="Module">structured-types.pointed-types</a>

<a id="455" class="Keyword">open</a> <a id="460" class="Keyword">import</a> <a id="467" href="synthetic-homotopy-theory.circle.html" class="Module">synthetic-homotopy-theory.circle</a>
</pre>
<pre class="Agda"><a id="513" class="Keyword">module</a> <a id="520" href="group-theory.examples-higher-groups.html#520" class="Module">_</a>
  <a id="524" class="Keyword">where</a>

  <a id="533" href="group-theory.examples-higher-groups.html#533" class="Function">classifying-type-ℤ-∞-Group</a> <a id="560" class="Symbol">:</a> <a id="562" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="565" href="Agda.Primitive.html#764" class="Primitive">lzero</a>
  <a id="573" href="group-theory.examples-higher-groups.html#533" class="Function">classifying-type-ℤ-∞-Group</a> <a id="600" class="Symbol">=</a> <a id="602" href="synthetic-homotopy-theory.circle.html#12148" class="Postulate">𝕊¹</a>

  <a id="608" href="group-theory.examples-higher-groups.html#608" class="Function">shape-ℤ-∞-Group</a> <a id="624" class="Symbol">:</a> <a id="626" href="synthetic-homotopy-theory.circle.html#12148" class="Postulate">𝕊¹</a>
  <a id="631" href="group-theory.examples-higher-groups.html#608" class="Function">shape-ℤ-∞-Group</a> <a id="647" class="Symbol">=</a> <a id="649" href="synthetic-homotopy-theory.circle.html#12173" class="Postulate">base-𝕊¹</a>

  <a id="660" href="group-theory.examples-higher-groups.html#660" class="Function">classifying-pointed-type-ℤ-∞-Group</a> <a id="695" class="Symbol">:</a> <a id="697" href="structured-types.pointed-types.html#383" class="Function">Pointed-Type</a> <a id="710" href="Agda.Primitive.html#764" class="Primitive">lzero</a>
  <a id="718" href="group-theory.examples-higher-groups.html#660" class="Function">classifying-pointed-type-ℤ-∞-Group</a> <a id="753" class="Symbol">=</a>
    <a id="759" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a>
      <a id="770" href="group-theory.examples-higher-groups.html#533" class="Function">classifying-type-ℤ-∞-Group</a>
      <a id="803" href="group-theory.examples-higher-groups.html#608" class="Function">shape-ℤ-∞-Group</a>

  <a id="822" href="group-theory.examples-higher-groups.html#822" class="Function">ℤ-∞-Group</a> <a id="832" class="Symbol">:</a> <a id="834" href="group-theory.higher-groups.html#1474" class="Function">∞-Group</a> <a id="842" href="Agda.Primitive.html#764" class="Primitive">lzero</a>
  <a id="850" href="group-theory.examples-higher-groups.html#822" class="Function">ℤ-∞-Group</a> <a id="860" class="Symbol">=</a>
    <a id="866" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a>
      <a id="877" href="group-theory.examples-higher-groups.html#660" class="Function">classifying-pointed-type-ℤ-∞-Group</a>
      <a id="918" href="synthetic-homotopy-theory.circle.html#19666" class="Function">is-path-connected-𝕊¹</a>

<a id="940" class="Keyword">module</a> <a id="947" href="group-theory.examples-higher-groups.html#947" class="Module">_</a>
  <a id="951" class="Symbol">{</a><a id="952" href="group-theory.examples-higher-groups.html#952" class="Bound">l</a> <a id="954" class="Symbol">:</a> <a id="956" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="961" class="Symbol">}</a> <a id="963" class="Symbol">(</a><a id="964" href="group-theory.examples-higher-groups.html#964" class="Bound">X</a> <a id="966" class="Symbol">:</a> <a id="968" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="971" href="group-theory.examples-higher-groups.html#952" class="Bound">l</a><a id="972" class="Symbol">)</a>
  <a id="976" class="Keyword">where</a>

  <a id="985" href="group-theory.examples-higher-groups.html#985" class="Function">classifying-type-symmetric-∞-Group</a> <a id="1020" class="Symbol">:</a> <a id="1022" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1025" class="Symbol">(</a><a id="1026" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="1031" href="group-theory.examples-higher-groups.html#952" class="Bound">l</a><a id="1032" class="Symbol">)</a>
  <a id="1036" href="group-theory.examples-higher-groups.html#985" class="Function">classifying-type-symmetric-∞-Group</a> <a id="1071" class="Symbol">=</a> <a id="1073" href="foundation.connected-components-universes.html#2310" class="Function">component-UU</a> <a id="1086" href="group-theory.examples-higher-groups.html#964" class="Bound">X</a>

  <a id="1091" href="group-theory.examples-higher-groups.html#1091" class="Function">shape-symmetric-∞-Group</a> <a id="1115" class="Symbol">:</a> <a id="1117" href="group-theory.examples-higher-groups.html#985" class="Function">classifying-type-symmetric-∞-Group</a>
  <a id="1154" href="group-theory.examples-higher-groups.html#1091" class="Function">shape-symmetric-∞-Group</a> <a id="1178" class="Symbol">=</a>
    <a id="1184" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1189" href="group-theory.examples-higher-groups.html#964" class="Bound">X</a> <a id="1191" class="Symbol">(</a><a id="1192" href="foundation.mere-equivalences.html#1762" class="Function">refl-mere-equiv</a> <a id="1208" href="group-theory.examples-higher-groups.html#964" class="Bound">X</a><a id="1209" class="Symbol">)</a>

  <a id="1214" href="group-theory.examples-higher-groups.html#1214" class="Function">classifying-pointed-type-symmetric-∞-Group</a> <a id="1257" class="Symbol">:</a> <a id="1259" href="structured-types.pointed-types.html#383" class="Function">Pointed-Type</a> <a id="1272" class="Symbol">(</a><a id="1273" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="1278" href="group-theory.examples-higher-groups.html#952" class="Bound">l</a><a id="1279" class="Symbol">)</a>
  <a id="1283" href="group-theory.examples-higher-groups.html#1214" class="Function">classifying-pointed-type-symmetric-∞-Group</a> <a id="1326" class="Symbol">=</a>
    <a id="1332" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a>
      <a id="1343" href="group-theory.examples-higher-groups.html#985" class="Function">classifying-type-symmetric-∞-Group</a>
      <a id="1384" href="group-theory.examples-higher-groups.html#1091" class="Function">shape-symmetric-∞-Group</a>

  <a id="1411" href="group-theory.examples-higher-groups.html#1411" class="Function">is-path-connected-classifying-type-symmetric-∞-Group</a> <a id="1464" class="Symbol">:</a>
    <a id="1470" href="foundation.connected-types.html#1682" class="Function">is-path-connected</a> <a id="1488" href="group-theory.examples-higher-groups.html#985" class="Function">classifying-type-symmetric-∞-Group</a>
  <a id="1525" href="group-theory.examples-higher-groups.html#1411" class="Function">is-path-connected-classifying-type-symmetric-∞-Group</a> <a id="1578" class="Symbol">=</a>
    <a id="1584" href="foundation.connected-components-universes.html#6383" class="Function">is-path-connected-component-UU</a> <a id="1615" href="group-theory.examples-higher-groups.html#964" class="Bound">X</a>
  
  <a id="1622" href="group-theory.examples-higher-groups.html#1622" class="Function">symmetric-∞-Group</a> <a id="1640" class="Symbol">:</a> <a id="1642" href="group-theory.higher-groups.html#1474" class="Function">∞-Group</a> <a id="1650" class="Symbol">(</a><a id="1651" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="1656" href="group-theory.examples-higher-groups.html#952" class="Bound">l</a><a id="1657" class="Symbol">)</a>
  <a id="1661" href="group-theory.examples-higher-groups.html#1622" class="Function">symmetric-∞-Group</a> <a id="1679" class="Symbol">=</a>
    <a id="1685" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a>
      <a id="1696" href="group-theory.examples-higher-groups.html#1214" class="Function">classifying-pointed-type-symmetric-∞-Group</a>
      <a id="1745" href="group-theory.examples-higher-groups.html#1411" class="Function">is-path-connected-classifying-type-symmetric-∞-Group</a>
</pre>