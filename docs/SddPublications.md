<html>
            <head>
                <title>SddPublications - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>DonovanSharp - Wed Aug 30 2006 - Version 1.10<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.18 Referencing publications in SDD</h3>

<p>Record for publications used in the dataset. Elements consist simply of a &lt;Representation&gt; (name of publication) and optional &lt;Link&gt; to a url as shown below and in Example 3.18.1.</p>

<p><a href="SddPublications/publications.gif"><img src="SddPublications/publications.gif"/></a></p>

<h4>Example 3.18.1 - Publications in SDD</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>&lt;Publications&gt;
  &lt;Publication id="p111"&gt;
    &lt;Representation&gt;
      &lt;Label&gt;Author, X (2000). Short Citation, including journal or publisher.&lt;/Label&gt;
    &lt;/Representation&gt;
  &lt;/Publication&gt;
  &lt;Publication id="p112"&gt;
    &lt;Representation&gt;
      &lt;Label&gt;Gee, X. &amp; Haa, Y. (2003). How to be happy in five minutes. Instant Gratifications, Palm Beach.&lt;/Label&gt;
    &lt;/Representation&gt;
    &lt;Links&gt;
    &lt;Link rel="BasedOn" href="doi:10.1992/32311"/&gt;
    &lt;Link rel="Alternate" href="http://some.service.net/providing/bibliographic.data"/&gt;
    &lt;/Links&gt;
    &lt;Extensions&gt;
        &lt;x:Data xmlns:x="www.x.edu"&gt;Applications may store additional data at the resource connectors.&lt;/x:Data&gt;
    &lt;/Extensions&gt;
  &lt;/Publication&gt;
&lt;/Publications&gt;
</code></pre>

</td>
</tr>

</table>

<p>-- Main.DonovanSharp - 05 Jun 2006</p>


            </body>
            </html>