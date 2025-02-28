<html>
            <head>
                <title>SddMapping - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>DonovanSharp - Wed Aug 30 2006 - Version 1.14<br> <a href="SddCharacters.html">Parent topic: SddCharacters</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.13 Mapping one character onto another</h3>

<p>Mapping allows the definition of measurement units and the mapping of one character to another. Categorical states can be mapped onto other categorical states (i.e sub-ovate may be mapped onto ovate for identification purposes) and quantitative characters can be mapped onto categorical characters (i.e. 'length in mm' can be mapped onto the states 'small', 'medium' and 'large'.</p>

<h4>3.13.1 Mapping a categorical character state onto another</h4>

<p>Character states which are designed for a particular role (i.e. natural language descriptions) may be ambiguous in another role (i.e. identification keys) or for a different audience. For example Mapping allows the categorical state "sub-ovate" (useful for <a href="NaturalLanguageDescriptions.html">natural language descriptions</a> to be mapped to the state "ovate" for the generation of <a href="DichotomousKeys.html">dichotomous keys</a>. In essence the state "ovate" becomes a parent state of a sub-state "sub-ovate". Multiple states can be mapped to a single state in this way, for example the states "yellowish" and "translucent" could be mapped to the state "white".</p>

<p><a href="SddMapping/categoricalmapping.gif"><img src="SddMapping/categoricalmapping.gif"/></a></p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>			&lt;CategoricalCharacter id="c4"&gt;
				&lt;Representation&gt;
					&lt;Label&gt; Leaf shape&lt;/Label&gt;
				&lt;/Representation&gt;
				&lt;States&gt;
					&lt;StateDefinition id="s3"&gt;
						&lt;Representation&gt;
							&lt;Label&gt;Round&lt;/Label&gt;
						&lt;/Representation&gt;
					&lt;/StateDefinition&gt;
					&lt;StateDefinition id="s4"&gt;
						&lt;Representation&gt;
							&lt;Label&gt;Ovate&lt;/Label&gt;
						&lt;/Representation&gt;
					&lt;/StateDefinition&gt;
					&lt;StateDefinition id="s5"&gt;
						&lt;Representation&gt;
							&lt;Label&gt;Sub-ovate&lt;/Label&gt;
						&lt;/Representation&gt;
					&lt;/StateDefinition&gt;
				&lt;/States&gt;
				&lt;Mappings&gt;
					&lt;Mapping&gt;
						&lt;From ref="s5"/&gt;
						&lt;To ref="s4"/&gt;
					&lt;/Mapping&gt;
				&lt;/Mappings&gt;
			&lt;/CategoricalCharacter&gt;
</code></pre>

</td>
</tr>

</table>

<h4>3.13.2 Mapping a quantitative character onto a categorical character</h4>

<p><a href="SddMapping/quantitativemapping.gif"><img src="SddMapping/quantitativemapping.gif"/></a></p>

<p>Specific ranges of a quantitative character data can be mapped onto states of categorical characters, for example, to simplify the data for interactive key purposes. For example the data to populate the character "Leaf Area (Webb and Tracy Units)" with the four states "nanophyll", "microphyll", "mesophyll" and "macrophyll" would be automatically generated from the data in the quantitative character "Leaf Area".</p>

<h5>Example 3.13.2.1 - Units and mapping within quantitative characters.</h5>

<p>    </p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>&lt;QuantitativeCharacter id="c2"&gt;
  &lt;Representation&gt;
    &lt;Label&gt;Leaf length&lt;/Label&gt;
  &lt;/Representation&gt;
  &lt;Assumptions&gt;
    &lt;MeasurementScale&gt;Ratio&lt;/MeasurementScale&gt;
  &lt;/Assumptions&gt;
  &lt;Mappings&gt;
    &lt;Mapping&gt;
      &lt;From lower="0" upper="3"/&gt;
      &lt;ToState ref="s1"/&gt;
    &lt;/Mapping&gt;
    &lt;Mapping&gt;
      &lt;From lower="3" upper="10"/&gt;
      &lt;ToState ref="s2"/&gt;
    &lt;/Mapping&gt;
    &lt;Mapping&gt;
      &lt;From lower="4" upper="10000000"/&gt;
      &lt;ToState ref="s3"/&gt;
    &lt;/Mapping&gt;
  &lt;/Mappings&gt;
  &lt;MeasurementUnit&gt;
    &lt;Label role="Abbrev"&gt;m&lt;/Label&gt;
  &lt;/MeasurementUnit&gt;
  &lt;Default&gt;
    &lt;MeasurementUnitPrefix&gt;milli&lt;/MeasurementUnitPrefix&gt;
  &lt;/Default&gt;
&lt;/QuantitativeCharacter&gt;
</code></pre>

</td>
</tr>

</table>

<p>&lt;From&gt; gives an inclusive range defined through the two attributes "lower" and "upper".</p>

<p>&lt;ToState&gt; specifies the categorical state corresponding to the range defined in &lt;From&gt;. If &lt;ToState&gt; is missing then &lt;From&gt; governs partitioning into range classes automatically generated from the "upper" and "lower" values.</p>

<p>-- Main.DonovanSharp - 06 Jun 2006</p>


            </body>
            </html>