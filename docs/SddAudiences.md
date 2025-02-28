<html>
            <head>
                <title>SddAudiences - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>DonovanSharp - Wed Aug 30 2006 - Version 1.8<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.9 SDD audiences</h3>

<p>SDD contains the provision for defining taxon names for each entity to be applied to delivering products targetted at particular audiences, enabling users to be provided with names they are familiar with. For example taxonomists may be provided with scientific names while landholders are provided with common names.</p>

<p>A simple SDD code instance defining audiences has the basic structure shown below and in Example 3.9.1.</p>

<p><a href="SddAudiences/audiences.gif"><img src="SddAudiences/audiences.gif"/></a></p>

<h4>Example 3.9.1 - Multiple taxon names for a single entity based on intended audience</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>   &lt;TaxonNames&gt;
       &lt;TaxonName id='95'&gt;
         &lt;Label audience="student"&gt;
           &lt;Text&gt;Aristida latifolia
           &lt;/Text&gt;
         &lt;/Label&gt;
         &lt;Label audience="expert"&gt;
           &lt;Text&gt;A. latifolia
           &lt;/Text&gt;
         &lt;/Label&gt;
         &lt;Label audience="farmer"&gt;
           &lt;Text&gt;Feathertop Wiregrass
           &lt;/Text&gt;
         &lt;/Label&gt;
       &lt;/TaxonName&gt;
  &lt;/TaxonNames&gt;
  &lt;Audiences&gt;
    &lt;Audience&gt;
      &lt;Representation&gt;
          &lt;Label&gt;student&lt;/Label&gt;
      &lt;/Representation&gt;
      &lt;ExpertiseLevel&gt;ExpertiseLevel2&lt;/ExpertiseLevel&gt;
    &lt;/Audience&gt;
    &lt;Audience&gt;
      &lt;Representation&gt;
          &lt;Label&gt;expert&lt;/Label&gt;
      &lt;/Representation&gt;
      &lt;ExpertiseLevel&gt;ExpertiseLevel5&lt;/ExpertiseLevel&gt;
    &lt;/Audience&gt;
    &lt;Audience&gt;
      &lt;Representation&gt;
          &lt;Label&gt;farmer&lt;/Label&gt;
      &lt;/Representation&gt;
      &lt;ExpertiseLevel&gt;ExpertiseLevel3&lt;/ExpertiseLevel&gt;
    &lt;/Audience&gt;
  &lt;/Audiences&gt;
</code></pre>

</td>
</tr>

</table>

<p>The &lt;Representation&gt; element provides a label for the description. This may be useful if the instance document includes multiple descriptions for different purposes, or is intended for publication in multiple languages (see the topic <a href="SddLanguage.html">Language support in SDD</a>.</p>

<p>&lt;ExpertiseLevel&gt; is restricted to values from 0-5. These categories allow the communication of expected expertise between different applications using UBIF. </p>

<p>Recommended interpretations:</p>

<ul>
  <li>0 = expertise level undefined</li>
  <li>1 = elementary school (year 1 to 6);</li>
  <li>2 = middle school (year 7 to 10);</li>
  <li>3 = high school (year 11 above) and general public (trying to avoid any specialized terminology or jargon);</li>
  <li>4 = university students or (partly) trained personnel (using terminology, but avoiding or explaining problematic terminology);</li>
  <li>5 = experts (using the full range of terminology).</li>
</ul>

<p>-- Main.DonovanSharp - 01 Jun 2006</p>


            </body>
            </html>