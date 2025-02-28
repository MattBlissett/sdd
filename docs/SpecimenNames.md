<html>
            <head>
                <title>SpecimenNames - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>DonovanSharp - Wed Aug 30 2006 - Version 1.5<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.5 Defining specimen names</h3>

<h4>3.5.1 Defining specimen names</h4>

<p>Sample data descriptions usually comprise repeated measurements of parts of individual specimens, and are the basis from which the more abstracted descriptions in natural language and coded descriptions are derived. Few taxonomists consistently record and archive their raw data in a standardised format and specimen naming conventions will vary between institutions and workers. </p>

<p>Specimen names in SDD may be provided directly within the document, or they may be linked to or derived from external taxonomic databases. Each specimen is assigned a human readable name.</p>

<p><a href="SpecimenNames/specimennames.gif"><img src="SpecimenNames/specimennames.gif"/></a></p>

<p>Adding specimen names to an SDD instance document simply requires a unique identifier for each specimen as below: </p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">
<tr>
<td>
<pre><code>
		&lt;Specimens&gt;
			&lt;Specimen id="sp1"&gt;
				&lt;Representation&gt;
					&lt;Label&gt;TJM45337&lt;/Label&gt;
				&lt;/Representation&gt;
			&lt;/Specimen&gt;
			&lt;Specimen id="sp2"&gt;
				&lt;Representation&gt;
					&lt;Label&gt;TLM33466&lt;/Label&gt;
				&lt;/Representation&gt;
			&lt;/Specimen&gt;
		&lt;/Specimens&gt;
</code></pre>
</td>
</tr>

</table>

<p>Specimen names are required for the recording of <a href="CodedSampleDescription.html">sample data</a> in SDD instance documents.</p>

<p>The unique identifier for eact specimen is recoeded in the  &lt;Representation&gt; element.</p>

<p>Other information which may be recorded within the <SpecimenName> element include elements recording a taxonomic name for the specimen, an indication of the certainty applied to this taxonomic name and whether the specimen is preserved in a collection.</p>

<p><a href="SpecimenNames/specimen_elements.gif"><img src="SpecimenNames/specimen_elements.gif"/></a></p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">
<tr>
<td>
<pre><code>			&lt;Specimen id="sp1"&gt;
				&lt;Representation&gt;
					&lt;Label&gt;TJM45337&lt;/Label&gt;
				&lt;/Representation&gt;
				&lt;TaxonName ref="t1"/&gt;
				&lt;IdentificationCertainty&gt;IdentificationUncertain&lt;/IdentificationCertainty&gt;
				&lt;IsPreservedInCollection&gt;true&lt;/IsPreservedInCollection&gt;
			&lt;/Specimen&gt;
</code></pre>
</td>
</tr>

</table>

<p>&lt;TaxonName&gt; refers to a TaxonName specified in the &lt;TaxonName&gt; element (See the topic <a href="TaxonNames.html">Defining taxon names</a> for more detail).</p>

<p>There are currently four allowable modifiers for the element &lt;IdentificationCertainty&gt;; IdentificationCertain, IdentificationCertaintyUnknown, IdentificationSimilarTo and IdentificationUncertain.</p>

<p>For the element &lt;IsPreservedInCollection&gt; true means the specimen is preserved in a collection, false means it is not.</p>

<p>-- Main.DonovanSharp - 07 Jul 2006</p>


            </body>
            </html>