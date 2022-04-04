# Group theory

<pre class="Agda"><a id="25" class="Symbol">{-#</a> <a id="29" class="Keyword">OPTIONS</a> <a id="37" class="Pragma">--without-K</a> <a id="49" class="Pragma">--exact-split</a> <a id="63" class="Symbol">#-}</a>

<a id="68" class="Keyword">module</a> <a id="75" href="group-theory.html" class="Module">group-theory</a> <a id="88" class="Keyword">where</a>

<a id="95" class="Keyword">open</a> <a id="100" class="Keyword">import</a> <a id="107" href="group-theory.abelian-groups.html" class="Module">group-theory.abelian-groups</a> <a id="135" class="Keyword">public</a>
<a id="142" class="Keyword">open</a> <a id="147" class="Keyword">import</a> <a id="154" href="group-theory.abelian-subgroups.html" class="Module">group-theory.abelian-subgroups</a> <a id="185" class="Keyword">public</a>
<a id="192" class="Keyword">open</a> <a id="197" class="Keyword">import</a> <a id="204" href="group-theory.abstract-group-torsors.html" class="Module">group-theory.abstract-group-torsors</a> <a id="240" class="Keyword">public</a>
<a id="247" class="Keyword">open</a> <a id="252" class="Keyword">import</a> <a id="259" href="group-theory.addition-homomorphisms-abelian-groups.html" class="Module">group-theory.addition-homomorphisms-abelian-groups</a> <a id="310" class="Keyword">public</a>
<a id="317" class="Keyword">open</a> <a id="322" class="Keyword">import</a> <a id="329" href="group-theory.category-of-groups.html" class="Module">group-theory.category-of-groups</a> <a id="361" class="Keyword">public</a>
<a id="368" class="Keyword">open</a> <a id="373" class="Keyword">import</a> <a id="380" href="group-theory.category-of-semigroups.html" class="Module">group-theory.category-of-semigroups</a> <a id="416" class="Keyword">public</a>
<a id="423" class="Keyword">open</a> <a id="428" class="Keyword">import</a> <a id="435" href="group-theory.cayleys-theorem.html" class="Module">group-theory.cayleys-theorem</a> <a id="464" class="Keyword">public</a>
<a id="471" class="Keyword">open</a> <a id="476" class="Keyword">import</a> <a id="483" href="group-theory.concrete-group-actions.html" class="Module">group-theory.concrete-group-actions</a> <a id="519" class="Keyword">public</a>
<a id="526" class="Keyword">open</a> <a id="531" class="Keyword">import</a> <a id="538" href="group-theory.concrete-groups.html" class="Module">group-theory.concrete-groups</a> <a id="567" class="Keyword">public</a>
<a id="574" class="Keyword">open</a> <a id="579" class="Keyword">import</a> <a id="586" href="group-theory.concrete-subgroups.html" class="Module">group-theory.concrete-subgroups</a> <a id="618" class="Keyword">public</a>
<a id="625" class="Keyword">open</a> <a id="630" class="Keyword">import</a> <a id="637" href="group-theory.conjugation.html" class="Module">group-theory.conjugation</a> <a id="662" class="Keyword">public</a>
<a id="669" class="Keyword">open</a> <a id="674" class="Keyword">import</a> <a id="681" href="group-theory.embeddings-groups.html" class="Module">group-theory.embeddings-groups</a> <a id="712" class="Keyword">public</a>
<a id="719" class="Keyword">open</a> <a id="724" class="Keyword">import</a> <a id="731" href="group-theory.endomorphism-rings-abelian-groups.html" class="Module">group-theory.endomorphism-rings-abelian-groups</a> <a id="778" class="Keyword">public</a>
<a id="785" class="Keyword">open</a> <a id="790" class="Keyword">import</a> <a id="797" href="group-theory.equivalences-group-actions.html" class="Module">group-theory.equivalences-group-actions</a> <a id="837" class="Keyword">public</a>
<a id="844" class="Keyword">open</a> <a id="849" class="Keyword">import</a> <a id="856" href="group-theory.equivalences-semigroups.html" class="Module">group-theory.equivalences-semigroups</a> <a id="893" class="Keyword">public</a>
<a id="900" class="Keyword">open</a> <a id="905" class="Keyword">import</a> <a id="912" href="group-theory.examples-higher-groups.html" class="Module">group-theory.examples-higher-groups</a> <a id="948" class="Keyword">public</a>
<a id="955" class="Keyword">open</a> <a id="960" class="Keyword">import</a> <a id="967" href="group-theory.furstenberg-groups.html" class="Module">group-theory.furstenberg-groups</a> <a id="999" class="Keyword">public</a>
<a id="1006" class="Keyword">open</a> <a id="1011" class="Keyword">import</a> <a id="1018" href="group-theory.group-actions.html" class="Module">group-theory.group-actions</a> <a id="1045" class="Keyword">public</a>
<a id="1052" class="Keyword">open</a> <a id="1057" class="Keyword">import</a> <a id="1064" href="group-theory.groups.html" class="Module">group-theory.groups</a> <a id="1084" class="Keyword">public</a>
<a id="1091" class="Keyword">open</a> <a id="1096" class="Keyword">import</a> <a id="1103" href="group-theory.higher-groups.html" class="Module">group-theory.higher-groups</a> <a id="1130" class="Keyword">public</a>
<a id="1137" class="Keyword">open</a> <a id="1142" class="Keyword">import</a> <a id="1149" href="group-theory.homomorphisms-abelian-groups.html" class="Module">group-theory.homomorphisms-abelian-groups</a> <a id="1191" class="Keyword">public</a>
<a id="1198" class="Keyword">open</a> <a id="1203" class="Keyword">import</a> <a id="1210" href="group-theory.homomorphisms-group-actions.html" class="Module">group-theory.homomorphisms-group-actions</a> <a id="1251" class="Keyword">public</a>
<a id="1258" class="Keyword">open</a> <a id="1263" class="Keyword">import</a> <a id="1270" href="group-theory.homomorphisms-groups.html" class="Module">group-theory.homomorphisms-groups</a> <a id="1304" class="Keyword">public</a>
<a id="1311" class="Keyword">open</a> <a id="1316" class="Keyword">import</a> <a id="1323" href="group-theory.homomorphisms-monoids.html" class="Module">group-theory.homomorphisms-monoids</a> <a id="1358" class="Keyword">public</a>
<a id="1365" class="Keyword">open</a> <a id="1370" class="Keyword">import</a> <a id="1377" href="group-theory.homomorphisms-semigroups.html" class="Module">group-theory.homomorphisms-semigroups</a> <a id="1415" class="Keyword">public</a>
<a id="1422" class="Keyword">open</a> <a id="1427" class="Keyword">import</a> <a id="1434" href="group-theory.invertible-elements-monoids.html" class="Module">group-theory.invertible-elements-monoids</a> <a id="1475" class="Keyword">public</a>
<a id="1482" class="Keyword">open</a> <a id="1487" class="Keyword">import</a> <a id="1494" href="group-theory.isomorphisms-abelian-groups.html" class="Module">group-theory.isomorphisms-abelian-groups</a> <a id="1535" class="Keyword">public</a>
<a id="1542" class="Keyword">open</a> <a id="1547" class="Keyword">import</a> <a id="1554" href="group-theory.isomorphisms-group-actions.html" class="Module">group-theory.isomorphisms-group-actions</a> <a id="1594" class="Keyword">public</a>
<a id="1601" class="Keyword">open</a> <a id="1606" class="Keyword">import</a> <a id="1613" href="group-theory.isomorphisms-groups.html" class="Module">group-theory.isomorphisms-groups</a> <a id="1646" class="Keyword">public</a>
<a id="1653" class="Keyword">open</a> <a id="1658" class="Keyword">import</a> <a id="1665" href="group-theory.isomorphisms-semigroups.html" class="Module">group-theory.isomorphisms-semigroups</a> <a id="1702" class="Keyword">public</a>
<a id="1709" class="Keyword">open</a> <a id="1714" class="Keyword">import</a> <a id="1721" href="group-theory.mere-equivalences-group-actions.html" class="Module">group-theory.mere-equivalences-group-actions</a> <a id="1766" class="Keyword">public</a>
<a id="1773" class="Keyword">open</a> <a id="1778" class="Keyword">import</a> <a id="1785" href="group-theory.monoids.html" class="Module">group-theory.monoids</a> <a id="1806" class="Keyword">public</a>
<a id="1813" class="Keyword">open</a> <a id="1818" class="Keyword">import</a> <a id="1825" href="group-theory.orbits-group-actions.html" class="Module">group-theory.orbits-group-actions</a> <a id="1859" class="Keyword">public</a>
<a id="1866" class="Keyword">open</a> <a id="1871" class="Keyword">import</a> <a id="1878" href="group-theory.precategory-of-group-actions.html" class="Module">group-theory.precategory-of-group-actions</a> <a id="1920" class="Keyword">public</a>
<a id="1927" class="Keyword">open</a> <a id="1932" class="Keyword">import</a> <a id="1939" href="group-theory.precategory-of-groups.html" class="Module">group-theory.precategory-of-groups</a> <a id="1974" class="Keyword">public</a>
<a id="1981" class="Keyword">open</a> <a id="1986" class="Keyword">import</a> <a id="1993" href="group-theory.precategory-of-semigroups.html" class="Module">group-theory.precategory-of-semigroups</a> <a id="2032" class="Keyword">public</a>
<a id="2039" class="Keyword">open</a> <a id="2044" class="Keyword">import</a> <a id="2051" href="group-theory.principal-group-actions.html" class="Module">group-theory.principal-group-actions</a> <a id="2088" class="Keyword">public</a>
<a id="2095" class="Keyword">open</a> <a id="2100" class="Keyword">import</a> <a id="2107" href="group-theory.semigroups.html" class="Module">group-theory.semigroups</a> <a id="2131" class="Keyword">public</a>
<a id="2138" class="Keyword">open</a> <a id="2143" class="Keyword">import</a> <a id="2150" href="group-theory.sheargroups.html" class="Module">group-theory.sheargroups</a> <a id="2175" class="Keyword">public</a>
<a id="2182" class="Keyword">open</a> <a id="2187" class="Keyword">import</a> <a id="2194" href="group-theory.stabilizer-groups.html" class="Module">group-theory.stabilizer-groups</a> <a id="2225" class="Keyword">public</a>
<a id="2232" class="Keyword">open</a> <a id="2237" class="Keyword">import</a> <a id="2244" href="group-theory.subgroups.html" class="Module">group-theory.subgroups</a> <a id="2267" class="Keyword">public</a>
<a id="2274" class="Keyword">open</a> <a id="2279" class="Keyword">import</a> <a id="2286" href="group-theory.substitution-functor-group-actions.html" class="Module">group-theory.substitution-functor-group-actions</a> <a id="2334" class="Keyword">public</a>
<a id="2341" class="Keyword">open</a> <a id="2346" class="Keyword">import</a> <a id="2353" href="group-theory.symmetric-groups.html" class="Module">group-theory.symmetric-groups</a> <a id="2383" class="Keyword">public</a>
<a id="2390" class="Keyword">open</a> <a id="2395" class="Keyword">import</a> <a id="2402" href="group-theory.transitive-group-actions.html" class="Module">group-theory.transitive-group-actions</a> <a id="2440" class="Keyword">public</a>
</pre>