<html>
            <head>
                <title>SummaryData - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>DonovanSharp - Thu Jul 06 2006 - Version 1.7<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>4.4 Elements of structured summary data in SDD.</h3>

<p>A coded description requires three essential items: the names of the taxa being described, the terminology (characters and states) used to describe the taxa, and the coded descriptions themselves</p>

<p>     <img src="SummaryData/coded_data.gif"/></p>

<p>An SDD instance document for coded summary data has the basic structure shown in Example 4.4.1.</p>

<h4>Example 4.4.1 - SDD structure of coded descriptions</h4>

<table bgcolor="#ddddff" border="0" width="80%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>&lt;Datasets&gt;
  &lt;Dataset&gt;
	
    &lt;TaxonNames&gt;
      ... provides a list of the entities (usually taxa) described
    &lt;/TaxonNames&gt;
	
    &lt;TaxonHierarchies&gt;
      ... optional element to describe relationships between entities
    &lt;/TaxonHierarchies&gt;
	
    &lt;DescriptiveTerminology&gt;
      ... provides the terminology and ontology used to describe the 
	  entities (see DescriptiveConcepts, SddCharacters, CharacterTrees)
    &lt;/DescriptiveTerminology&gt;
	
    &lt;CodedDescriptions&gt;
       &lt;SummaryData&gt;
            ... the actual descriptions
       &lt;/SummaryData&gt;
    &lt;/CodedDescriptions&gt;
	
    &lt;MediaResources&gt;
      ... optional element providing media (images, video, audio etc.) associated with 
          any of the above
    &lt;/MediaResources&gt;
	
  &lt;/Dataset&gt;
&lt;/Datasets&gt;
</code></pre>
</td>
</tr>

</table>

<p>Optional elements allow the taxa to be arranged into a hierarchy, and the recording of media files (images etc) for taxa or characters.</p>

<h4>Example 4.4.1 - A simple summary description of a taxon (<i>Korthalsella</i>)</h4>

<p><pre><code>    &lt;CodedDescriptions&gt;
      &lt;CodedDescription id="cd1"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Korthalsella&lt;/Label&gt;
        &lt;/Representation&gt;
        &lt;Scope&gt;
          &lt;TaxonName ref="t2"/&gt;
        &lt;/Scope&gt;
        &lt;SummaryData&gt;
          &lt;Categorical ref="c3"&gt;
            &lt;State ref="s7"/&gt;
          &lt;/Categorical&gt;
          &lt;Categorical ref="c1"&gt;
            &lt;State ref="s2"/&gt;
          &lt;/Categorical&gt;
          &lt;Quantitative ref="c4"&gt;
            &lt;Measure type="Min" value="5.0"/&gt;
            &lt;Measure type="UMethUpper" value="10.0"/&gt;
            &lt;Measure type="UMethlower" value="20.0"/&gt;
            &lt;Measure type="Max" value="25.0"/&gt;
          &lt;/Quantitative&gt;
        &lt;/SummaryData&gt;
      &lt;/CodedDescription&gt;
    &lt;/CodedDescriptions&gt;
</code></pre> 	 </td> </tr></p>

<p></table></p>

<p>-- Main.DonovanSharp - 02 Jun 2006</p>


            </body>
            </html>