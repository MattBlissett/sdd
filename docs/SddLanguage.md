<html>
            <head>
                <title>SddLanguage - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>DonovanSharp - Wed Aug 30 2006 - Version 1.5<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.10 Language support in SDD</h3>

<p>SDD allows the use of any language supported in the xml namespace. Translations to and from languages can be explicitely tagged. Language can be specified and multiple entries included for all text based elements within SDD. All elements containing a &lt;Label&gt; tag may contain language specific markup.</p>

<p><a href="SddLanguage/labelattributes.jpg"><img src="SddLanguage/labelattributes.jpg"/></a></p>

<h4>Example 3.10.1 - Language support in SDD</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

 <pre><code>&lt;Representation&gt;
  &lt;Label xml:lang="en"&gt;Flying Fishes of the world&lt;/Label&gt;
  &lt;Label xml:lang="de"&gt;Fliegende Fische der Welt&lt;/Label&gt;
  &lt;Detail xml:lang="en" role="Description"&gt;A digital field guide&lt;/Detail&gt;
  &lt;Detail xml:lang="en" role="Coverage"&gt;Flying Fishes (Exocoetidae)&lt;/Detail&gt;
  &lt;Detail xml:lang="de" role="Coverage"&gt;Fliegende Fische (Exocoetidae)&lt;/Detail&gt;
  &lt;Detail xml:lang="en" translatedfrom="sp" role="Abstract"&gt;Abstract translated from Spanish goes here&lt;/Detail&gt;
  &lt;MediaObject ref="m1"/&gt;
&lt;/Representation&gt;	
</code></pre>

</td>
</tr>

</table>

<p>-- Main.DonovanSharp - 01 Jun 2006</p>


            </body>
            </html>
