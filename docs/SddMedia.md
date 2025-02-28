<html>
            <head>
                <title>SddMedia - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>DonovanSharp - Wed Aug 30 2006 - Version 1.11<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.12 Attaching Media to SDD Items</h3>

<h4>3.12.1 Media resources in SDD.</h4>

<p>The location of media in an SDD instance document is represented by a simple resource list. Media may include images (.jpeg, .png etc.), sound, video and web resources. SDD allows external references, embedded resource data, and provides for a multilingual caption.</p>

<p>Media items are defined within the &lt;MediaObjects&gt; element and simply referenced each time they are used elsewhere in an SDD instance document.</p>

<p>Simple SDD code for associated media has the basic structure shown below and in Example 3.12.1.1.</p>

<p><a href="SddMedia/media.gif"><img src="SddMedia/media.gif"/></a></p>

<h4>Example 3.12.1.1 - A simple SDD media dialog</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>


<pre><code>    &lt;MediaObjects&gt;
      &lt;MediaObject id="m1"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Image description, e. g., to be used for alt-attribute in html.&lt;/Label&gt;
        &lt;/Representation&gt;
        &lt;Type&gt;Text&lt;/Type&gt;
        &lt;Data href="file:/Media/Html/Gleditsia_triacanthos.htm"/&gt;
      &lt;/MediaObject&gt;
      &lt;MediaObject id="m2"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;No caption&lt;/Label&gt;
        &lt;/Representation&gt;
        &lt;Type&gt;Image&lt;/Type&gt;
        &lt;Data href="file:/Media/Images/Gleditsia triacanthos.jpg"/&gt;
      &lt;/MediaObject&gt;
    &lt;/MediaObjects&gt;
</code></pre>

</td>
</tr>

</table>

<p>The location of locally stored media objects is defined relative to the SDD instance document.</p>

<p>The &lt;Representation&gt; element provides a label for the media object. This may be useful if the instance document includes multiple descriptions for different purposes, or is intended for publication in multiple languages (see the topic <a href="SddLanguage.html">Language support in SDD</a>.</p>

<p>&lt;Owners&gt; refers to a person, persons or institution defined in the SDD <a href="SddAgents.html">&lt;Agents&gt;</a> element.</p>

<p>&lt;IPRStatements&gt; records the original source of media (for example the full citation for a publication). and any restrictions on useage. May contain URL to IPR statements external to the SDD instance document.</p>

<p>Media items are defined once and referenced for each useage. Multiple media items of different types may be referenced for an item.</p>

<h4>Example 3.12.1.2 - Referencing media</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>


<pre><code>  &lt;Dataset&gt;

    &lt;TaxonNames&gt;
      &lt;TaxonName id="t1"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Gleditsia triacanthos&lt;/Label&gt;
          &lt;MediaObject ref="m1"/&gt;
          &lt;MediaObject ref="m2"/&gt;
        &lt;/Representation&gt;
      &lt;/TaxonName&gt;
    &lt;/TaxonNames&gt;
    &lt;Characters&gt;
      &lt;CategoricalCharacter id="c1"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Armature&lt;/Label&gt;
        &lt;/Representation&gt;
        &lt;States&gt;
          &lt;StateDefinition id="s1"&gt;
            &lt;Representation&gt;
              &lt;Label&gt;armed&lt;/Label&gt;
              &lt;MediaObject ref="m3"/&gt;
              &lt;MediaObject ref="m4"/&gt;
            &lt;/Representation&gt;
          &lt;/StateDefinition&gt;
        &lt;/States&gt;
      &lt;/CategoricalCharacter&gt;
    &lt;/Characters&gt;
&lt;MediaObjects&gt;
	... media dialog goes here
&lt;/MediaObjects&gt;

  &lt;/Dataset&gt;

</code></pre>

</td>
</tr>

</table>

<p>Associated information may include captions, web addresses and translations. Media may be directly embedded in the SDD code instead of referenced with a URL.</p>

<h4>Example 3.12.1.3 - Associated information for embedded media</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>


<pre><code>		&lt;MediaObjects&gt;
			&lt;MediaObject id="m1" uri="urn:lsid:local:local:129739128"&gt;
				&lt;Representation&gt;
					&lt;Label&gt;Image description, e. g., to be used for alt-attribute in html.&lt;/Label&gt;
				&lt;/Representation&gt;
				&lt;Owners&gt;
					&lt;Agent ref="a1" role="own "/&gt;
				&lt;/Owners&gt;
				&lt;Type&gt;Image&lt;/Type&gt;
				&lt;Data href="http://test.edu/test.jpg"/&gt;
			&lt;/MediaObject&gt;
			&lt;MediaObject id="m2"&gt;
				&lt;Representation&gt;
					&lt;Label&gt;Morning call of Homo sapiens&lt;/Label&gt;
				&lt;/Representation&gt;
				&lt;Type&gt;Sound&lt;/Type&gt;
				&lt;Data href="http://test.edu/123.mp3"/&gt;
			&lt;/MediaObject&gt;
			&lt;MediaObject id="m3"&gt;
				&lt;Representation&gt;
					&lt;Label&gt;Melampsora evonymi-caprearum&lt;/Label&gt;
					&lt;!-- Details like Caption are optional --&gt;
					&lt;Detail role="Caption" xml:lang="fr"&gt;&lt;i&gt;Melampsora evonymi-caprearum&lt;/i&gt; Kleb., stade II sur &lt;i&gt;Salix caprea&lt;/i&gt;L.&lt;/Detail&gt;
					&lt;Detail role="Caption" xml:lang="de"&gt;&lt;i&gt;Melampsora evonymi-caprearum&lt;/i&gt; Kleb., Sporenstadium II auf &lt;i&gt;Salix caprea&lt;/i&gt; L.&lt;/Detail&gt;
					&lt;Detail role="Caption" xml:lang="en"&gt;&lt;i&gt;Melampsora evonymi-caprearum&lt;/i&gt; Kleb., spore stage II on &lt;i&gt;Salix caprea&lt;/i&gt; L.&lt;/Detail&gt;
				&lt;/Representation&gt;
				&lt;Type&gt;Image&lt;/Type&gt;
				&lt;!-- Optionally Resources may be included rather than referencenced through URIs. 
           An additional href specifying the source of the encoded resource is optional (in addition to the encoded content) --&gt;
    &lt;EncodedData ContentType="image/png"  href="http://test.edu/Melampsora_evonymi-caprearum.png"&gt;R0lGODlhcgGSALMAAAQCAEMmCZtuMFQxDS8b&lt;/EncodedData&gt;
			&lt;/MediaObject&gt;
		&lt;/MediaObjects&gt;
</code></pre>

</td>
</tr>

</table>

<p>Available "roles" within the &lt;Detail&gt; element are; Abstract, Caption, Coverage, Description, Normative and UnknownDetailRole.</p>

<p>If resources are included within the SDD instance document they should be directly encoded, i.e. not wrapped into a MIME object first.</p>

<p>-- Main.DonovanSharp - 05 Jun 2006</p>


            </body>
            </html>