<html>
            <head>
                <title>SddDatasets - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>KevinThiele - Fri Sep 15 2006 - Version 1.6<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.1 Datasets in SDD documents</h3>

<p>An SDD document will normally contain data about a single set of taxa described using a single set of characters. However, there may be occasions when it is useful to combine several related data sets into a single document. </p>

<p>For example, an SDD document may contain one data set providing descriptions of a set of parasites and another providing descriptions of their hosts. Since descriptions of the parasites and hosts will usually require different characters, it would not be appropriate to contain them within a single data set. Another SDD document may contain descriptions of one set of organisms provided by two different sources, each comprising an independent but related data set. </p>

<p>To accomodate this, the root element of SDD is called &lt;Datasets&gt;; containing a single <a href="TechnicalMetadata.html">&lt;TechnicalMetadata&gt;</a> element and an unlimited number of &lt;Dataset&gt; elements. All other objects are inside one of the &lt;Dataset&gt; elements.  </p>

<h4>Example 3.1.1 - An SDD document containing two datasets</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>


  <pre><code>  &lt;TechnicalMetadata created='2005-07-18T20:49:26'&gt;
   &lt;Generator name='By Hand' version='1'/&gt;
  &lt;/TechnicalMetadata&gt;
  &lt;Dataset&gt;
   &lt;Representation&gt;
    &lt;Label&gt;Descriptions of Ithomid butterflies&lt;/Label&gt;
   &lt;/Representation&gt;
  &lt;TaxonNames&gt;
     ... (names of the butterfly taxa)
  &lt;/TaxonNames&gt;
  &lt;DescriptiveTerminology&gt;
   &lt;Characters&gt;
     ... (characters and states for the butterfly descriptions)
   &lt;/Characters&gt;
  &lt;/DescriptiveTerminology&gt;
  &lt;CodedDescriptions&gt;
     ... (descriptions of the butterflies)
  &lt;/CodedDescriptions&gt;
 &lt;/Dataset&gt;
 &lt;Dataset&gt;
   &lt;Representation&gt;
    &lt;Label&gt;Descriptions of parasitoid wasps of Ithomid butterflies&lt;/Label&gt;
   &lt;/Representation&gt;
  &lt;TaxonNames&gt;
     ... (names of the wasp taxa)
  &lt;/TaxonNames&gt;
  &lt;DescriptiveTerminology&gt;
   &lt;Characters&gt;
     ... (characters and states for the wasp descriptions)
   &lt;/Characters&gt;
  &lt;/DescriptiveTerminology&gt;
  &lt;CodedDescriptions&gt;
     ... (descriptions of the wasps)
  &lt;/CodedDescriptions&gt;
 &lt;/Dataset&gt;
&lt;/Datasets&gt;
</code></pre>	

</td>
</tr>

</table>

<p>-- Main.DonovanSharp - 01 Jun 2006</p>
            </body>
            </html>