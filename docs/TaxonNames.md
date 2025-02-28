<html>
            <head>
                <title>TaxonNames - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>DonovanSharp - Tue Aug 29 2006 - Version 1.19<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.4 Defining taxon names</h3>

<h3>3.4.1 Defining taxon names</h3>

<p>Datasets in SDD documents will generally contain descriptions or other data for a defined set of organisms. The names of these are specified in the &lt;<a href="TaxonNames.html">TaxonNames</a>&gt; element. </p>

<p>Taxon names in SDD may be provided directly within the document, or they may be linked to or derived from external taxonomic databases. Each taxon is assigned a human readable name.</p>

<p>A simple SDD code instance representing taxon name definition has the basic structure shown below and in Example 3.4.1.1.</p>

<p><a href="TaxonNames/taxonnames.gif"><img src="TaxonNames/taxonnames.gif"/></a></p>

<h4>Example 3.4.1.1 - A simple list of taxon names</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>


<pre><code>    &lt;TaxonNames&gt;
     &lt;TaxonName id='Taxon95'&gt;
        &lt;Label&gt;
          &lt;Text&gt;Collembola&lt;/Text&gt;
        &lt;/Label&gt;
      &lt;/TaxonName&gt;
      &lt;TaxonName id='Taxon96'&gt;
        &lt;Label&gt;
          &lt;Text&gt;Protura&lt;/Text&gt;
        &lt;/Label&gt;
      &lt;/TaxonName&gt;
      &lt;TaxonName id='Taxon97'&gt;
        &lt;Label&gt;
          &lt;Text&gt;Diplura&lt;/Text&gt;
        &lt;/Label&gt;
      &lt;/TaxonName&gt;
    &lt;/TaxonNames&gt;
</code></pre>	


</td>
</tr>

</table>

<p>Taxa may be assigned multiple alernative names, which can then be utilised for varying purposes by a consuming application. For example, full names, abbreviated names and common names can be supplied for any taxon.</p>

<h4>Example 3.4.1.2 - Multiple names for a single taxon</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

 
<pre><code>   
  &lt;TaxonName id="taxon1"&gt;
   &lt;Representation&gt;
    &lt;Label role="Full"&gt;Aristida latifolia&lt;/Label&gt;
    &lt;Label role="Abbrev"&gt;A. latifolia&lt;/Label&gt;
    &lt;Label role="Token"&gt;Feathertop Wiregrass&lt;/Label&gt;
   &lt;/Representation&gt;
  &lt;/TaxonName&gt;
</code></pre>

</td>
</tr>

</table>

<h3>3.4.2 Elements within &lt;<a href="TaxonNames.html">TaxonNames</a>&gt;</h3>

<p>Taxonomic names may be simple (Pandanus tectorius) or quite complicated due to the additions supported by various taxonomic naming conventions (<i>Pandanus</i> L.f. <i>tectorius</i> Parkinson sens. lat. meaning of the genus <i>Pandanus</i> as described by Linnaeus and the species <i>tectorius</i> in the broad sense as described by Parkinson). There are a number of elements within &lt;<a href="TaxonNames.html">TaxonNames</a>&gt; to facilitate the management of the various additions to simple taxonomic names.The basic structure of the SDD code to support this is shown below and in Example 3.4.2.1.</p>

<p><a href="TaxonNames/taxonnameelements.gif"><img src="TaxonNames/taxonnameelements.gif"/></a></p>

<h4>Example 3.4.2.1 Basic structure within taxon names</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

 
<pre><code>   
		&lt;TaxonNames&gt;
			&lt;TaxonName id="t1"&gt;
				&lt;Representation&gt;
					&lt;Label&gt;Gleditsia triacanthos&lt;/Label&gt;
				&lt;/Representation&gt;
				&lt;NomenclaturalCode&gt;Botanical&lt;/NomenclaturalCode&gt;
				&lt;Rank literal="Species"/&gt;
				&lt;CanonicalName&gt;
					&lt;Simple&gt;Pandanus tectorius&lt;/Simple&gt;
				&lt;/CanonicalName&gt;
				&lt;CanonicalAuthorship&gt;
					&lt;Simple&gt;Parkinson&lt;/Simple&gt;
				&lt;/CanonicalAuthorship&gt;
				&lt;ConceptSuffix literal="sens lat."/&gt;
				&lt;TaxonPlacement&gt;
					&lt;TaxonName ref="t3"/&gt;
				&lt;/TaxonPlacement&gt;
			&lt;/TaxonName&gt;
		&lt;/TaxonNames&gt;
</code></pre>

</td>
</tr>

</table>

<h5>3.4.2.1 NomenclaturalCode</h5>

<p>The relevent nomenclatural code governing the entity. This may be used to validate entity names.</p>

<p>The following sets of rules (nomenclature codes) are currently accepted:</p>

<ul>
  <li>Plants (including fungi and algae): International code of the Botanical nomenclature (ICBN)</li>
  <li>Animals: International code OF Zoological Nomenclature (ICZN)</li>
  <li>Bacteria: Bacteriological code (BC)</li>
  <li>Cultivated plants: Internationally code OF Nomenclature for Cultivated Plants (ICNCP)</li>
  <li>Viruses: Internationally code OF virus Classification and Nomenclature (ICVCN)</li>
</ul>

<p>Other codes are currently in development but not yet accepted, including the are Phylocode and bio code, aiming to unify the various currently accepted codes.</p>

<h5>3.4.2.2 Rank</h5>

<p>For biological taxonomic names: order, family, species, etc. </p>

<h5>3.4.2.3 CanonicalName</h5>

<p>Canonical name enforcing strict inclusion of only nomenclatural information, i.e. not taxonomic hierarchy information with the exception of the necessary placements within Genus or Species. Canonical name may be a simple text representation or an atomised representation in the following format</p>

<p><a href="TaxonNames/canonicalname.gif"><img src="TaxonNames/canonicalname.gif"/></a></p>

<h5>3.4.2.4 CanonicalAuthorship</h5>

<p>Canonical authorship of the name, optionally atomized</p>

<h5>3.4.2.5 ConceptSuffix</h5>

<p>A part of the taxon name indicating either imprecise concept hints ('s. str.', 'p.p.', 's. l.', 'auct.'), an informal or fomal according-to citation ('sec. Muell.', 'sensu Hagedorn, Sydowia 1998'). In the later case this may be made more precise by using the available attributes to add a local or uri reference to a publication.</p>

<h5>3.4.2.6 Race</h5>

<p>Race numbers, names, possibly other ranks not governed by a code (patho/bio/serovar).</p>

<h5>3.4.2.7 TaxonPlacement</h5>

<p>Additional hierarchical information which may be designed to be part of the name. Example: a name may be cited as "Cortinarius (subg. Phlegmacium) glaucopus s. l. (Cortinariaceae)". Here 'Cortinarius glaucopus' is canonical name, 's. l.' Concept suffix, and 'Phlegmacium' and 'Cortinariaceae' is additional hierarchical placement information.</p>

<p>-- Main.DonovanSharp - 01 Jun 2006</p>


            </body>
            </html>