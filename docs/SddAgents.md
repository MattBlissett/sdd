<html>
            <head>
                <title>SddAgents - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>DonovanSharp - Wed Aug 30 2006 - Version 1.7<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.14 Referencing contributors and sources</h3>

<p>In SDD, this is a central repository for names of persons or organization, and is used throughout the data when attributing intellectual work, enabling management of authors, editors, contributors, translators and their respective contributions.</p>

<p>Agents are defined simply with a text string and an optional URL leading to more detailed information, as shown in the wire diagram and simple example below.</p>

<p><a href="SddAgents/agent.gif"><img src="SddAgents/agent.gif"/></a></p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>&lt;Agents&gt;
  &lt;Agent id="a1"&gt;
    &lt;Representation&gt;
      &lt;Label&gt;Kevin Thiele&lt;/Label&gt;
    &lt;/Representation&gt;
  &lt;/Agent&gt;
  &lt;Agent id="a2"&gt;
    &lt;Representation&gt;
      &lt;Label&gt;Gregor Hagedorn&lt;/Label&gt;
    &lt;/Representation&gt;
  &lt;/Agent&gt;
  &lt;Agent id="a3"&gt;
    &lt;Representation&gt;
      &lt;Label&gt;Ali Baba&lt;/Label&gt;
      &lt;Detail role="Description"&gt;Ali Baba is also known as r.a.m.&lt;/Detail&gt;
    &lt;/Representation&gt;
  &lt;/Agent&gt;
&lt;/Agents&gt;
</code></pre>

</td>
</tr>

</table>

<p>The &lt;Representation&gt; element provides a label for the description. This may be useful if the instance document includes multiple descriptions for different purposes, or is intended for publication in multiple languages (see the topic <a href="SddLanguage.html">Language support in SDD</a>.</p>

<p>-- Main.DonovanSharp - 09 Jun 2006</p>


            </body>
            </html>