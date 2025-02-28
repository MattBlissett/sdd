<html>
            <head>
                <title>SamplingEvent - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>LeeBelbin - Fri Nov 20 2009 - Version 1.12<br> <a href="CodedDescription.html">Parent topic: CodedDescription</a><br></p>

<h2>Main.BDI Part 0: Introduction and Primer to the Main.BDI Standard </h2>

<h3>4.5 Elements within &lt;<a href="SamplingEvent.html">SamplingEvent</a>&gt;</h3>

<p>The element &lt;SamplingUnit&gt; contains raw sample data for a specimen. &lt;<a href="SamplingEvent.html">SamplingEvent</a>&gt; contains information about where and when that sampling occurred.</p>

<p>A simple Main.BDI instance document representing a sampling event has the basic structure shown below and in example 4.5.1.1.</p>

<p><a href="SamplingEvent/sampledata4.gif"><img src="SamplingEvent/sampledata4.gif"/></a></p>

<p>Example 4.5.1.1 - A simple sampling event </p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>&lt;SampleData&gt;
	&lt;SamplingEvent id="TJM45337"&gt;
	&lt;DateTime minute="17" hour="7" day="17" month="7" year="2006"/&gt;
	&lt;DateTimeSpanEnd minute="27" hour="7" day="17" month="7" year="2006"/&gt;
	&lt;GeographicArea ref="g2"/&gt;
	&lt;Coordinates latitude="20.44" longitude="139.29"/&gt;
		&lt;SamplingUnit&gt;
			&lt;Quantitative ref="ch1" value="12"/&gt;
		&lt;/SamplingUnit&gt;
                     ...etc
&lt;/SampleData&gt;
</code></pre>

</td>
</tr>

</table>

<p>&lt;DateTime&gt; records the date and time when the sampling event occurred, either as a single time point or as the start of a time period.</p>

<p>&lt;DateTimeSpanEnd&gt; records the end of a time span if event timing is recorded as such. Both date/times may be incomplete in ways not expressible in xs:datetime, e.g. the day and year may be known, but month unknown.</p>

<p>&lt;GeographicArea&gt; is a reference to a geographic area at which the event occurred. This is defined in the element &lt;GeographicAreas&gt; with the basic structure shown below and in example 4.5.1.2.</p>

<p><a href="SamplingEvent/geographicarea.gif"><img src="SamplingEvent/geographicarea.gif"/></a></p>

<p>Example 4.5.1.2 Defining geographic areas</p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>&lt;GeographicAreas&gt;
  &lt;GeographicArea id="g1"&gt;
    &lt;Representation&gt;
      &lt;Label&gt;Worldwide&lt;/Label&gt;
    &lt;/Representation&gt;
  &lt;/GeographicArea&gt;
  &lt;GeographicArea id="g2"&gt;
    &lt;Representation&gt;
      &lt;Label&gt;Europe&lt;/Label&gt;
    &lt;/Representation&gt;
  &lt;/GeographicArea&gt;
&lt;/GeographicAreas&gt;
</code></pre>

</td>
</tr>

</table>

<p>&lt;Coordinates&gt; records a point on earth at which the event occurred. Elements available are &lt;Latitude&gt;, &lt;Longitude&gt;, &lt;GeodeticDatum&gt;; &lt;Verbatim&gt; (a textual representation of the original location data) and &lt;Literal&gt; (a free-form string in addition to or instead of numeric coordinates (i.e. Charley's Creek, near Chinchilla).</p>

<p>Example 4.5.1.3 Use of the &lt;Coordinate&gt; element</p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>&lt;SampleData&gt;
 &lt;SamplingEvent id="AQ578462"&gt;
  &lt;DateTime&gt;&lt;/DateTime&gt;
   &lt;Coordinates latitude="26.5" longitude="150.5" 
           geodeticdatum="GDA94" verbatim="5km NW of Roma"/&gt;
    &lt;SamplingUnit&gt;
     &lt;Categorical ref="c1"&gt;
      &lt;State ref="s1"/&gt;
     &lt;/Categorical&gt;
    &lt;/SamplingUnit&gt;
 &lt;/SamplingEvent&gt;
&lt;/SampleData&gt;
</code></pre>

</td>
</tr>

</table>

<h4>4.5.2. SamplingUnit</h4>

<p>A sampling unit may be an individual organism, a leaf of a tree, a piece of tissue, etc. In each sampling unit multiple characters may have been observed together ('paired observations'). Example: 'leaf shape, length, and width' of a single leaf). Value frequencies (e. g., '2.3': observed 4 x) are not supported; they are useful when only a single character variable is supported, but complicate paired observations unnecessarily. Char. values with a frequency should be entered in repeated SamplingUnits.</p>

<p>A simple Main.BDI code snippet representing part of the sample data above has the basic structure shown below and in Example 4.5.2.1.</p>

<p><a href="SamplingEvent/samplingunit2.gif"><img src="SamplingEvent/samplingunit2.gif"/></a></p>

<p>Example 4.5.2.1. Recording sampling data in Main.BDI</p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>  &lt;SampleData&gt;
    &lt;SamplingEvent id="sev1000"&gt;
    &lt;DateTime&gt;&lt;/DateTime&gt;
      &lt;SamplingUnit&gt;
        &lt;Categorical ref="c1"&gt;
          &lt;State ref="s2"/&gt;
        &lt;/Categorical&gt;
        &lt;Quantitative ref="c2" value="110"/&gt;
      &lt;/SamplingUnit&gt;
      &lt;SamplingUnit&gt;
        &lt;Categorical ref="c1"&gt;
          &lt;State ref="s1"/&gt;
        &lt;/Categorical&gt;
        &lt;Quantitative ref="c2" value="112"/&gt;
      &lt;/SamplingUnit&gt;
      &lt;SamplingUnit&gt;
        &lt;Categorical ref="c1"&gt;
          &lt;State ref="s1"/&gt;
        &lt;/Categorical&gt;
        &lt;Quantitative ref="c2" value="110"/&gt;
      &lt;/SamplingUnit&gt;
      &lt;SamplingUnit&gt;
        &lt;Categorical ref="c1"&gt;
          &lt;State ref="s1"/&gt;
        &lt;/Categorical&gt;
        &lt;Quantitative ref="c2" value="118"/&gt;
      &lt;/SamplingUnit&gt;
    &lt;/SamplingEvent&gt;
  &lt;/SampleData&gt;
</code></pre>

</td>
</tr>

</table>

<p>-- Main.DonovanSharp - 21 Jun 2006</p>


            </body>
            </html>