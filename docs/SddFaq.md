<html>
            <head>
                <title>SddFaq - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>DonovanSharp - Thu Sep 07 2006 - Version 1.7<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>Frequently Asked Questions</h3>

<h4>There's already a perfectly good descriptive data standard in DELTA - why not continue to use it?</h4>

<a name="DeltaFaq"></a> The <a href="http://biodiversity.uno.edu/delta/">DELTA</a> system, developed from 1971 at CSIRO in Canberra, was for many years a widely used format for capturing and manipulating descriptive data. The <a href="http://biodiversity.uno.edu/delta/">DELTA</a> data format was accepted as a standard by TDWG in 1991.

<p>However, the <a href="http://biodiversity.uno.edu/delta/">DELTA</a> system comprises a data format closely tied to a particular software implementation (the DELTA programs such as CONFOR, INTKEY etc). Because of this close linkage between the data format and the software, any changes to the <a href="http://biodiversity.uno.edu/delta/">DELTA</a> standard required matching changes in a large body of software code. Since the code-base belonged to a particular developer group, no changes to the <a href="http://biodiversity.uno.edu/delta/">DELTA</a> format could be made unless the developers accepted the changes and made appropriate modifications to the software. By the later 1990's a number of improvements to the <a href="http://biodiversity.uno.edu/delta/">DELTA</a> format had been suggested, by the DELTA developers and others, but these changes were not implemented because of difficulties in updating the software.</p>

<p>Also by the late 1990s a number of developers had created alternative software packages (e.g. <a href="http://www.diversitycampus.net/Workbench/Descriptions/">DeltaAccess</a>, <a href="http://www.lucidcentral.com">Lucid</a>) based on alternative data formats (either new formats or modifications to DELTA). These formats were generally not fully mappable with DELTA data, or with each other. This in turn meant that data could not be losslessly translated from one format to the another, making roundtripping of data impossible.</p>

<p>It was in response to these challenges that the SDD data standard was created as an implementation--independent format created through international collaboration. The format of SDD has been designed allow extensibility of the standard without creating immediate problems for generating or consuming applications. Independence from a particular software implementation also means that loss of support for any given implementing program will have no implications for maintenance of the standard.</p>

<p> </p>

<h4>SDD instance documents seem extremely verbose - why is this, and is it a problem?</h4>

<a name="VerboseFaq"></a> SDD uses XML to represent descriptive data. XML (Extensible Markup Language: see <a href="http://www.w3.org">www.w3.org</a>) is an extremely flexible and effective markup language. It is also usually verbose - in fact, one of the design criteria for the World Wide Web Consortium (W3C) in creating XML was "Terseness in XML markup is of minimal importance". This is because terseness (such as, for instance, through extensive use of abbreviated codewords rather than plain text) makes the document harder to read by both people and machines.

<p>Much of the verbosity of XML occurs because XML is a markup language in which the structure of the data is explicitly represented by tags, rather than relying on implicit (e.g. positional) methods for determining data elements. For example, consider a small data matrix, comprising three columns and two rows of integers. The matrix could be represented straightforwardly using two lines of comma-separated values:</p>

<p>0,1,8</p>

<p>7,4,2</p>

<p>The same data matrix represented in XML will require many tags and is considerably more verbose.</p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>&lt;Matrix&gt;    
    &lt;Row id=1&gt;
        &lt;Column id=1&gt;0&lt;/Column&gt;
        &lt;Column id=2&gt;1&lt;/Column&gt;
        &lt;Column id=3&gt;8&lt;/Column&gt;
    &lt;/Row&gt;
    &lt;Row id=2&gt;
        &lt;Column id=1&gt;7&lt;/Column&gt;
        &lt;Column id=2&gt;4&lt;/Column&gt;
        &lt;Column id=3&gt;2&lt;/Column&gt;
    &lt;/Row&gt;
&lt;/Matrix&gt;
</code></pre>

</td>
</tr>

</table>

<p>While deceptively simple, the first (matrix) representation cannot be parsed without specifying a number of implicit parsing rules (for instance, that the values are separated by commas, that while parsing a row the column number can be determined by tallying commas, and that the row number is determined by tallying line breaks). The data can be read only by a special-purpose parser furnished with these rules. By contrast, the XML representation requires a minimum number of implicit parsing rules, and any XML parser will be able to parse the data.</p>

<p>SDD documents, particularly simple instances such as given in the examples in this Primer, also appear complex because SDD is weighted to bring efficiencies to representations of large documents rather than small ones. For instance, authors and contributors in SDD documents are specified once, then referred to by numeric key references throughout the remainder of the document. While this may appear nonsensical in a small document where only one author is referred to once, it will be maximally efficient for large documents where many authors are referred to many times.</p>

<h4>Why are there so many numbers within an SDD instance document and to what do they relate</h4>

<p>Every higher level element within an SDD document must have a unique identifier by which references to that element can be reconciled. There are many ways of achieving this. Every element can be assigned a unique number, for example;    </p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code> &lt;TaxonName id="54"&gt;
  &lt;Representation&gt;
   &lt;Label xml:lang="en-us"&gt;Korthalsella papuana&lt;/Label&gt;
  &lt;/Representation&gt;
 &lt;/TaxonName&gt;


or

  &lt;StateDefinition id="76"&gt;
   &lt;Representation&gt;
    &lt;Label xml:lang="en-us"&gt;aquatic&lt;/Label&gt;
   &lt;/Representation&gt;
   &lt;/StateDefinition&gt;.
</code></pre>

</td>
</tr>

</table>

<p>Alternatively each element can be assigned a unique identifier with a prefix providing information about the element it is associated with, for example;    </p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code> &lt;TaxonName id="t54"&gt;
  &lt;Representation&gt;
   &lt;Label xml:lang="en-us"&gt;Korthalsella papuana&lt;/Label&gt;
  &lt;/Representation&gt;
 &lt;/TaxonName&gt;

or

  &lt;StateDefinition id="s76"&gt;
   &lt;Representation&gt;
    &lt;Label xml:lang="en-us"&gt;aquatic&lt;/Label&gt;
   &lt;/Representation&gt;
   &lt;/StateDefinition&gt;.

</code></pre>

</td>
</tr>

</table>

<p>-- Main.DonovanSharp - 02 Jun 2006</p>
            </body>
            </html>