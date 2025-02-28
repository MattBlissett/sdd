<html>
            <head>
                <title>CodedData - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>LeeBelbin - Fri Nov 20 2009 - Version 1.22<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>Main.BDI Part 0: Introduction and Primer to the Main.BDI Standard </h2>

<h3>2.1 Main.BDI for coded summary descriptions</h3>

<p>  Coded descriptions comprise highly structured data used in computer identification and analysis programs such as Lucid (<a href="http://www.lucidcentral.org"">www.lucidcentral.org</a>), DELTA (<a href="http://www.delta-intkey.com">www.delta-intkey.com</a>) and phylogenetic analysis programs such as PAUP (<a href="http://www.paup.csit.fsu.edu">www.paup.csit.fsu.edu</a>). </p>

<h4>Box 2.1.1 -  Simple examples of coded descriptions</h4>

<div>

<table bgcolor="#ddddff" border="0" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111" width="80%" id="table9">
  <tr>
    <td width="50%">
<div>


Lucid Interchange Format (LIF) file</div>


#Lucid Interchange Format File v. 2.1<br>
<br>
[..Character List..]<br>
Distribution by region<br>
&nbsp; Tropical North<br>
&nbsp; Subtropical and Temperate East and South<br>
&nbsp; South West<br>
&nbsp; Arid &amp; Semi-arid (Central)<br>
&nbsp; Island Territories<br>
General habit<br>
&nbsp; tree<br>
&nbsp; shrub<br>
&nbsp; climber (woody or herbaceous)<br>
&nbsp; herb<br>
&nbsp; grass- or sedge-like plant<br>
Seasonal longevity<br>
&nbsp; annual, biennial or ephemeral<br>
&nbsp; perennial<br>
<br>
[..Taxon List..]<br>
Acanthaceae<br>
Aceraceae<br>
Actinidiaceae<br>
Agavaceae<br>
Aizoaceae<br>
Akaniaceae<br>
Alangiaceae<br>
Alismataceae<br>
Aloaceae<br>
Alseuosmiaceae<br>
<br>
[..Main Data (txs)..]<br>
101101111111<br>
100100000101<br>
101000000010<br>
011110111111<br>
101111111111<br>
100100000011<br>
101101000011<br>
011111011111<br>
011100100111<br>
101100000010</div>

<p>    </td>     <td width="50%"></p>

<div>
DELTA file</div>

<p>*SHOW: Gentianella - character list. Last revised 16 April 1997.<br> <br> *CHARACTER LIST <br> <br> #1. plants/<br> 1. monocarpic/<br> 2. polycarpic/<br> <br> #2. &lt;plants lifecycle&gt;/<br> 1. annual/<br> 2. biennial/<br> 3. perennial/<br> <br> #3. height in flower/<br> &lt;&gt; cm/<br> <br> #4. caudex/<br> 1. unbranched/<br> 2. branched/<br> <br> *ITEM DESCRIPTIONS <br> <br> # Gentianella amabilis/<br> 1,2 2,3 3,3-13 4,1<br> <br> # Gentianella antarctica/<br> 1,1 2,1&lt;Godley 1982&gt; 3,1.6-22.0&lt;Godley 1982&gt; 4,1<br> <br> # Gentianella antipoda/<br> 1,1&lt;Godley 1982&gt; 2,2 3,3.5-9.8-24 4,1/2&lt;depends on size of plant&gt;<br> <br> # Gentianella astonii/<br> 1,2 2,3 3,15 4,2<br> <br> # Gentianella cerina/<br> 1,2 2,3 3,9-17 4,1/2<br> <br> #Gentianella concinna/<br> 1,1 2,1 3,2.7-15.0 4,1<br> &nbsp;</div></p>

<p>    </td>     <td width="50%">&nbsp;<p>&nbsp;</td>   </tr> </table></p>

<p></div></p>

<p>Coded summary descriptions record the range of characteristics found in a taxon (such as a family, genus, species etc). To record raw (sample) data for individual specimens, see the topic <a href="SampleData.html">Using Main.BDI for raw (sample) data</a>.</p>

<p>A coded sample description requires three essential items: the names of the taxa being described, a set of descriptors (characters and states) used to describe the taxa, and the coded descriptions themselves.</p>

<p>A simple Main.BDI instance document for coded summary data has the basic structure shown below and in Example 2.1.1.</p>

<img src="CodedData/coded_summary_descriptions.gif"/>

<h4>Example 2.1.1 - A simple coded description</h4>

<div>
<table bgcolor="#ddddff" border="0" width="80%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">
<pre>
<tr>
<td>
<pre><code>&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;Datasets xsi:schemaLocation="http://ns.tdwg.org/UBIF/2006/ 
  http://www.lucidcentral.org/2006/SDD/SDD1.1-RC1/SDD.xsd" 
  xmlns="http://ns.tdwg.org/UBIF/2006" 
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"&gt;
  &lt;Dataset xml:lang="en-us"&gt;
    &lt;TaxonNames&gt;
      &lt;TaxonName id="t1"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Acanthaceae&lt;/Label&gt;
        &lt;/Representation&gt;
      &lt;/TaxonName&gt;
          ...etc
    &lt;/TaxonNames&gt;
    &lt;Characters&gt;
      &lt;CategoricalCharacter id="c1"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Habit&lt;/Label&gt;
        &lt;/Representation&gt;
        &lt;States&gt;
          &lt;StateDefinition id="s1"&gt;
            &lt;Representation&gt;
              &lt;Label&gt;tree&lt;/Label&gt;
            &lt;/Representation&gt;
          &lt;/StateDefinition&gt;
          &lt;StateDefinition id="s2"&gt;
            &lt;Representation&gt;
              &lt;Label&gt;shrub&lt;/Label&gt;
            &lt;/Representation&gt;
          &lt;/StateDefinition&gt;
          &lt;StateDefinition id="s3"&gt;
            &lt;Representation&gt;
              &lt;Label&gt;herb&lt;/Label&gt;
            &lt;/Representation&gt;
          &lt;/StateDefinition&gt;
        &lt;/States&gt;
      &lt;/CategoricalCharacter&gt;
          ...etc
    &lt;/Characters&gt;
    &lt;CodedDescriptions&gt;
      &lt;CodedDescription id="cd1"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Acanthaceae&lt;/Label&gt;
        &lt;/Representation&gt;
        &lt;Scope&gt;
          &lt;TaxonName ref="t1"/&gt;
        &lt;/Scope&gt;
        &lt;SummaryData&gt;
          &lt;Categorical ref="c1"&gt;
            &lt;State ref="s2"/&gt;
            &lt;State ref="s3"/&gt;
          &lt;/Categorical&gt;
        &lt;/SummaryData&gt;
          ...etc
      &lt;/CodedDescription&gt;
    &lt;/CodedDescriptions&gt;
    &lt;MediaObjects/&gt;
  &lt;/Dataset&gt;
&lt;/Datasets&gt;
</code></pre>
</td>
</tr>
	</pre>
</table>
</div>

<p>For more information on defining taxon names using the &lt;<a href="TaxonNames.html">TaxonNames</a>&gt; element, see the topic <a href="TaxonNames.html">Defining taxon names</a>.  For more infirmation on defining characters and states using the &lt;Characters&gt; element, see the topic <a href="SddCharacters.html">Defining characters and states</a>.</p>

<p>Both taxa and characters can be arranged into hierarchies; see <a href="TaxonHierarchies.html">Defining taxon hierarchies</a> and <a href="CharacterHierarchies.html">Defining character hierarchies</a> for more information.</p>

<p>The &lt;Representation&gt; element provides a label for the description. This reflects the fact that a single taxon may have several descriptions. In a butterfly, "Gonepteryx rhamni, male" and "Gonepteryx rhamni, female", and "caterpillar of Gonepteryx rhamni" may be three different descriptions. Other examples are descriptions scoped to a geographic region ("in Australia"), to a small number of defined specimens, or to a given publication (which may have been kept separate because less trusted). Each coded description in Main.BDI may express these scopes of a description in the Scope element. To allow human users a simple and consistent access to descriptions, the separate description label is provided.</p>

<p>One problem that Main.BDI cannot solve itself is the fact that while some data models make a distinction between a taxon and multiple descriptions, many do not. Most current programs either have no formal taxon name (e.g. DELTA, Xper, etc. are careful to avoid the name "taxon description") or they handle male/female as pseudo-taxa (Lucid, ETI-Linneaus II). Software importing and exporting Main.BDI therefore needs to take care to accept both datasets that have only a Description Label and those that have explicit Taxon names.</p>

<p>&lt;Scope&gt; describes the taxon or set of taxa to which the description applies.</p>

<p>Characters used in the description are listed under &lt;<a href="SummaryData.html">SummaryData</a>&gt;. Main.BDI distinguishes between different kinds of characters (see the topic <a href="SddCharacters.html">Defining characters and states</a> for more information). For categorical characters (characters with states) the states occurring in the taxon being described are listed by reference. In the example given above, the taxon Acanthaceae is described as being a shrub or herb (states s2 and s3 of character c1). Note that states that are not listed are inferred to not occur in the taxon being described.</p>

<p>States used in a description can also be modified using a predefined set of modifiers (such as "rare", "uncertain" etc.). See the topic <a href="DescriptiveConcepts.html">&lt;DescriptiveConcepts&gt;</a>  for more information</p>

<p>-- Main.KevinThiele - 06 Jul 2006</p>


            </body>
            </html>