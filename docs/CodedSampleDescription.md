<html>
            <head>
                <title>CodedSampleDescription - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>LeeBelbin - Fri Nov 20 2009 - Version 1.8<br> <a href="CodedData.html">Parent topic: CodedData</a><br></p>

<h2>Main.BDI Part 0: Introduction and Primer to the Main.BDI Standard </h2>

<h3>2.2 Main.BDI for coded sample descriptions</h3>

<p>Sample data descriptions (Box 2.1.1.2) usually comprise repeated measurements of parts of individual specimens, and are the basis from which the more abstracted descriptions in natural language and coded descriptions are derived. Few taxonomists consistently record and archive their raw data in a standardised format. </p>

<h4>Box 2.2.1 - Example of sample (specimen) descriptive data</h4>

<p>  <div>
	<table bgcolor="#ddddff" border="1" width="80%" cellspacing="0" id="table10" cellpadding="0">
		<tr>
			<td rowspan="2" align="center">Specimen</td>
			<td colspan="5" align="center">Spore length</td>
			<td colspan="5" align="center">Spore width</td>
			<td width="163" rowspan="2" align="center">Spore colour</td>
		</tr>
		<tr>
			<td width="25" align="center">1</td>
			<td width="25" align="center">2</td>
			<td width="25" align="center">3</td>
			<td width="25" align="center">4</td>
			<td width="25" align="center">5</td>
			<td width="25" align="center">1</td>
			<td width="25" align="center">2</td>
			<td width="25" align="center">3</td>
			<td width="25" align="center">4</td>
			<td width="25" align="center">5</td>
		</tr>
		<tr>
			<td align="center">TJM45337</td>
			<td width="25" align="center">12</td>
			<td width="25" align="center">13</td>
			<td width="25" align="center">12</td>
			<td width="25" align="center">15</td>
			<td width="25" align="center">11</td>
			<td width="25" align="center">8</td>
			<td width="25" align="center">8</td>
			<td width="25" align="center">7</td>
			<td width="25" align="center">6</td>
			<td width="25" align="center">6</td>
			<td width="163" align="center">brown</td>
		</tr>
		<tr>
			<td align="center">TLM33466</td>
			<td width="25" align="center">15</td>
			<td width="25" align="center">18</td>
			<td width="25" align="center">17</td>
			<td width="25" align="center">17</td>
			<td width="25" align="center">15</td>
			<td width="25" align="center">10</td>
			<td width="25" align="center">8</td>
			<td width="25" align="center">9</td>
			<td width="25" align="center">9</td>
			<td width="25" align="center">10</td>
			<td width="163" align="center">yellow</td>
		</tr>
	</table>
	</div></p>

<p>Coded sample descriptions record the range of characteristics found in an individual, as opposed to a class or taxon (e.g. species, genus etc.). To record summary data for taxonomic levels higher than the individual, see the topic <a href="CodedData.html">Using Main.BDI for coded summary descriptions</a>.</p>

<p>A coded sample description requires three essential items: the identifiers of the specimens being described, a set of descriptors (characters and states) used to describe the specimens, and the coded descriptions themselves.</p>

<p>A simple Main.BDI instance document representing part of the sample data above has the basic structure shown below and in Example 2.2.1.</p>

<p><a href="CodedSampleDescription/coded_sample_descriptions.gif"><img src="CodedSampleDescription/coded_sample_descriptions.gif"/></a></p>

<h4>Example 2.2.1 - A simple coded sample description</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">
<tr>
<td>
<pre><code>&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;Datasets xsi:schemaLocation="http://ns.tdwg.org/UBIF/2006 http://www.lucidcentral.org/2006/SDD/SDD1.1-RC1/SDD.xsd" xmlns="http://ns.tdwg.org/UBIF/2006" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"&gt;
	&lt;TechnicalMetadata created="2006-06-22T11:19:56.007+10:00"&gt;
		&lt;Generator name="by hand" version="1"/&gt;
	&lt;/TechnicalMetadata&gt;
	&lt;Dataset xml:lang="en-us"&gt;
		&lt;Representation&gt;
			&lt;Label&gt;sample data example&lt;/Label&gt;
		&lt;/Representation&gt;
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
                        ...etc
		&lt;/Specimens&gt;
		&lt;Characters&gt;
			&lt;QuantitativeCharacter id="ch1"&gt;
				&lt;Representation&gt;
					&lt;Label&gt;Spore length&lt;/Label&gt;
				&lt;/Representation&gt;
			&lt;/QuantitativeCharacter&gt;
			&lt;CategoricalCharacter id="ch3"&gt;
				&lt;Representation&gt;
					&lt;Label&gt;Spore colour&lt;/Label&gt;
				&lt;/Representation&gt;
				&lt;States&gt;
					&lt;StateDefinition id="s1"&gt;
						&lt;Representation&gt;
							&lt;Label&gt;brown&lt;/Label&gt;
						&lt;/Representation&gt;
					&lt;/StateDefinition&gt;
					&lt;StateDefinition id="s2"&gt;
						&lt;Representation&gt;
							&lt;Label&gt;yellow&lt;/Label&gt;
						&lt;/Representation&gt;
					&lt;/StateDefinition&gt;
                                        ...etc
				&lt;/States&gt;
			&lt;/CategoricalCharacter&gt;
                        ...etc
		&lt;/Characters&gt;
		&lt;CodedDescriptions&gt;
			&lt;CodedDescription&gt;
				&lt;Representation&gt;
					&lt;Label&gt;Specimen data for fungal specimens&lt;/Label&gt;
				&lt;/Representation&gt;
				&lt;SampleData&gt;
					&lt;SamplingEvent id="TJM45337"&gt;
						&lt;SamplingUnit&gt;
							&lt;Quantitative ref="ch1" value="12"/&gt;
						&lt;/SamplingUnit&gt;
						&lt;SamplingUnit&gt;
							&lt;Quantitative ref="ch1" value="13"/&gt;
						&lt;/SamplingUnit&gt;
						&lt;SamplingUnit&gt;
							&lt;Quantitative ref="ch1" value="12"/&gt;
						&lt;/SamplingUnit&gt;
						&lt;SamplingUnit&gt;
							&lt;Quantitative ref="ch1" value="15"/&gt;
						&lt;/SamplingUnit&gt;
						&lt;SamplingUnit&gt;
							&lt;Quantitative ref="ch1" value="11"/&gt;
						&lt;/SamplingUnit&gt;
						&lt;SamplingUnit&gt;
							&lt;Categorical ref="ch3"&gt;
								&lt;State ref="s1"/&gt;
							&lt;/Categorical&gt;
						&lt;/SamplingUnit&gt;
					&lt;/SamplingEvent&gt;
                                       ...etc
				&lt;/SampleData&gt;
			&lt;/CodedDescription&gt;
		&lt;/CodedDescriptions&gt;
	&lt;/Dataset&gt;
&lt;/Datasets&gt;
</code></pre>
</td>
</tr>

</table>

<p>For more information on defining sampling units using the &lt;Specimens&gt; element, see the topic <a href="SpecimenNames.html">Defining specimen names</a>.  For more information on defining characters and states using the &lt;Characters&gt; element, see the topic <a href="SddCharacters.html">Defining characters and states</a>.</p>

<p>Note that characters can also be arranged into hierarchies. See the topic <a href="CharacterHierarchies.html">Defining character hierarchies</a> for more information.</p>

<p>The &lt;Representation&gt; element provides a label for the description. This may be useful if the instance document includes multiple descriptions for different purposes, or is intended for publication in multiple languages (see the topic <a href="SddLanguage.html">Language support in Main.BDI</a>.</p>

<p>The &lt;<a href="SamplingEvent.html">SamplingEvent</a>&gt; includes elements specifying the timing and location of the sample data. For more information see the topic <a href="SamplingEvent.html">Elements within &lt;SamplingEvent&gt;</a></p>

<p>Characters used in the description are listed under &lt;SampleData&gt;. Main.BDI distinguishes between different kinds of characters (see the topic <a href="SddCharacters.html">Defining characters and states</a> for more information). For categorical characters (characters with states) the states occurring in the taxon being described are listed by reference. In the example given above, the specimen TJM45337 is described as having brown spores (state s1 of character ch3) while specimen TLM33466is described as having yellow spores (state s2 of character ch3). Note that states that are not listed are inferred to not occur in the taxon being described.</p>

<p>-- Main.KevinThiele - 06 Jul 2006</p>


            </body>
            </html>