<html>
            <head>
                <title>SddScope - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>GregorHagedorn - Mon May 07 2007 - Version 1.7<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.19 Scope of descriptions</h3>

<h4>3.19.1 What is scoping?</h4>

<p>While an SDD instance document may contain more than one set of descriptions for different purposes, the group of taxa described within each description is not set and may contain any subset of <a href="TaxonNames.html">&lt;TaxonNames&gt;</a> or <a href="SpecimenNames.html">&lt;Specimens&gt;</a>. The scope element is applicable within any element nested within &lt;Dataset&gt; (<a href="NaturalLanguageDescriptions.html">natural language descriptions</a>, <a href="CodedDescription.html">coded descriptions</a>, and <a href="DichotomousKeys.html">dichotomous keys</a>) and allows a definition of the entities covered by each distinct description. </p>

<p>When used on &lt;Dataset&gt;, &lt;Scope&gt; defines the (taxonomic, ecological, geographic) scope for all keys or descriptions in the entire dataset, e.g. for a key to Australian desert grasses. In a <a href="CodedDescription.html">CodedDescription</a>, the &lt;Scope&gt; element could be used to define a description as refering to mandibles of immature male Lycanthropes of Wisconsin.</p>

<p>A simple SDD instance document for defining scope has the basic structure shown below.</p>

<p><a href="SddScope/scope.gif"><img src="SddScope/scope.gif"/></a></p>

<p>The scope of a dataset may be defined with reference to taxa, specimens, geographic names, etc. Multiple taxon names may be used to express ambiguities or groupings for which no higher taxon name exists (e. g., species from a geographical region). Taxon names may include a &lt;citation&gt; to the original source of the scope definition. Specimen scopes refer to the original physical object and may include reference to a geographical locality.</p>


            </body>
            </html>