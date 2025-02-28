<html>
            <head>
                <title>TaxonHierarchies - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>DonovanSharp - Wed Aug 30 2006 - Version 1.14<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.7 Taxon heirarchies</h3>

<p>Taxon hierarchies allow one or more hierarchical structures to be set for the coded entities. Hierarchies may tbe taxonomic (order/family/genus etc.) or non-taxonomic (weed/species/diseases, herb/shrub/tree).</p>

<h4>Example 3.7.1 - A simple taxon hierarchy</h4>

<p><a href="TaxonHierarchies/taxon_hierarchy_example.gif"><img src="TaxonHierarchies/taxon_hierarchy_example.gif"/></a></p>

<p>A taxon hierarchy requires two essential items within SDD: the names of the taxa being described, and the hierarchy itself.</p>

<p>A simple SDD instance document for a taxon hierarchy has the basic structure shown below and in Example 3.7.2.</p>

<p><a href="TaxonHierarchies/taxonhierarchy.gif"><img src="TaxonHierarchies/taxonhierarchy.gif"/></a></p>

<h4>Example 3.7.2 - A simple taxon hierarchy, SDD representation</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>
    
<pre><code>    &lt;TaxonHierarchies&gt;
      &lt;TaxonHierarchy id="th1"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Default Entity Tree&lt;/Label&gt;
        &lt;/Representation&gt;
        &lt;TaxonHierarchyType&gt;UnspecifiedTaxonomy&lt;/TaxonHierarchyType&gt;
        &lt;Nodes&gt;
          &lt;Node id="tn1"&gt;
            &lt;TaxonName ref="t1"/&gt;
          &lt;/Node&gt;
          &lt;Node id="tn2"&gt;
            &lt;Parent ref="tn1"/&gt;
            &lt;TaxonName ref="t2"/&gt;
          &lt;/Node&gt;
          &lt;Node id="tn3"&gt;
            &lt;Parent ref="tn2"/&gt;
            &lt;TaxonName ref="t3"/&gt;
          &lt;/Node&gt;
          &lt;Node id="tn4"&gt;
            &lt;Parent ref="tn2"/&gt;
            &lt;TaxonName ref="t4"/&gt;
          &lt;/Node&gt;
          &lt;Node id="tn5"&gt;
            &lt;Parent ref="tn1"/&gt;
            &lt;TaxonName ref="t5"/&gt;
          &lt;/Node&gt;
          &lt;Node id="tn6"&gt;
            &lt;Parent ref="tn5"/&gt;
            &lt;TaxonName ref="t6"/&gt;
          &lt;/Node&gt;
          &lt;Node id="tn7"&gt;
            &lt;Parent ref="tn5"/&gt;
            &lt;TaxonName ref="t7"/&gt;
          &lt;/Node&gt;
        &lt;/Nodes&gt;
      &lt;/TaxonHierarchy&gt;
    &lt;/TaxonHierarchies&gt;
</code></pre>

</td>
</tr>

</table>

<p>The &lt;Representation&gt; element provides a label for the description. This may be useful if the instance document includes multiple descriptions for different purposes, or is intended for publication in multiple languages (see the topic <a href="SddLanguage.html">Language support in SDD</a>.</p>

<p><a href="SddScope.html">&lt;Scope&gt;</a> defines the group of taxa for which this TaxonHierarchy is relevant, currently only taxonomic scope is supported. Records taxon names and citation for the source of the information.</p>

<p>The taxon hierarchy supports taxonomic (order/family/genus etc.) and non-taxonomic (weed species, diseases, herb/shrub/tree) hierarchies. For many analytical purposes it is relevant whether a hierarchy is based on phylogenetic (= evolutionary) relatedness or whether it is an operational categorization. This is defined in the &lt;TaxonHierarchyType&gt; element. Currently content is restricted to "NonphylogeneticTaxonomy", "PhylogeneticTaxonomy", "SubsetFilter" or "UnspecifiedTaxonomy".</p>

<h4>3.7.2 The structure of &lt;Nodes&gt; in &lt;TaxonHierarchy&gt;</h4>

<p>The tree structure of the taxon hierarchy is presented as an ordered list of nodes together with edges pointing to parent nodes. Inner nodes may have taxon name references or may be anonymous (esp. for phylogenetic analyses). The &lt;Node&gt; element has the basic structure shown below.</p>

<p><a href="TaxonHierarchies/taxonhierarchynodes.gif"><img src="TaxonHierarchies/taxonhierarchynodes.gif"/></a></p>

<p>&lt;Parent&gt; Refers to an inner node of the current tree. Omitting this is interpreted as a reference to the root of the tree.</p>

<p>&lt;TaxonName&gt; is a reference to a taxon name. Inner nodes may be anonymous or identified as a higher taxon; terminal nodes should always point to a taxon name (requires external validation).</p>

<p>&lt;Synonyms&gt; The expression of synonyms may be essential for reports and to convey the concept of a taxon to information consumers. Synonyms must refer to an entity previously defined in teh element &lt;<a href="TaxonNames.html">TaxonNames</a>&gt;, for more information refer to the topic <a href="TaxonNames.html">Defining taxon names</a>.</p>

<p>-- Main.DonovanSharp - 01 Jun 2006</p>


            </body>
            </html>