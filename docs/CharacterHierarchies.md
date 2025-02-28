<html>
            <head>
                <title>CharacterHierarchies - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>HeleneFradin - Fri Jul 27 2007 - Version 1.18<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.8 Character hierarchies</h3>

<p>The &lt;characters&gt; element in SDD is used to define a flat, unordered list of characters and states. However, some consuming applications may require characters to be ordered and/or to be arranged into hierarchies to, for example, enable easier navigation of characters in interactive keys, provide grouping mechanisms in listings and reports, and provide headers in natural language descriptions. </p>

<p>An example of a simple character tree is given below.</p>

<p><a href="CharacterHierarchies/character_trees_example.gif"><img src="CharacterHierarchies/character_trees_example.gif"/></a></p>

<p>In this example there are eight characters (Petal number, Petal shape, Leaf length etc) arranged into four (nested) groups (Flowers, Petals, Sepals and Leaves).</p>

<p>In SDD, a character tree is created using three elements:</p>

<ul>
  <li>Characters are defined in &lt;Characters&gt;</li>
  <li>Grouping concepts (such as the grouping nodes above) are defined in <a href="DescriptiveConcepts.html">&lt;DescriptiveConcepts&gt;</a></li>
  <li>One or more character trees are defined, using the characters and concepts defined above, in &lt;CharacterTrees&gt;</li>
</ul>

<p><a href="CharacterHierarchies/charactertrees.gif"><img src="CharacterHierarchies/charactertrees.gif"/></a></p>

<h4>Example 3.8.1 - A simple character hierarchy</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>

<pre><code>    &lt;Characters&gt;
      &lt;QuantitativeCharacter id="c1"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Petal Number&lt;/Label&gt;
        &lt;/Representation&gt;
      &lt;/QuantitativeCharacter&gt;
      &lt;CategoricalCharacter id="c2"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Petal Shape&lt;/Label&gt;
        &lt;/Representation&gt;
        &lt;States&gt;
          &lt;StateDefinition id="s1"&gt;
            &lt;Representation&gt;
              &lt;Label&gt;ovate&lt;/Label&gt;
            &lt;/Representation&gt;
          &lt;/StateDefinition&gt;
          &lt;StateDefinition id="s2"&gt;
            &lt;Representation&gt;
              &lt;Label&gt;linear&lt;/Label&gt;
            &lt;/Representation&gt;
          &lt;/StateDefinition&gt;
        &lt;/States&gt;
            ... etc (for more detail see the topic &lt;Characters&gt;)            
    &lt;/Characters&gt;

     &lt;DescriptiveConcepts&gt;
      &lt;DescriptiveConcept id="dc1"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Flowers&lt;/Label&gt;
        &lt;/Representation&gt;
      &lt;/DescriptiveConcept&gt;
      &lt;DescriptiveConcept id="dc2"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Petals&lt;/Label&gt;
        &lt;/Representation&gt;
            ... etc (for more detail see the topic &lt;DescriptiveConcepts&gt;)
    &lt;/DescriptiveConcepts&gt;

       &lt;CharacterTrees&gt;
      &lt;CharacterTree id="ct1"&gt;
        &lt;Representation&gt;
          &lt;Label&gt;Default Feature Tree&lt;/Label&gt;
        &lt;/Representation&gt;
        &lt;DesignedFor&gt;
          &lt;Role&gt;InteractiveIdentification&lt;/Role&gt;
        &lt;/DesignedFor&gt;
        &lt;Nodes&gt;
          &lt;Node id="cn1"&gt;
            &lt;DescriptiveConcept ref="dc1"/&gt;
          &lt;/Node&gt;
          &lt;Node id="cn2"&gt;
            &lt;Parent ref="cn1"/&gt;
            &lt;DescriptiveConcept ref="dc2"/&gt;
          &lt;/Node&gt;
          &lt;CharNode&gt;
            &lt;Parent ref="cn2"/&gt;
            &lt;Character ref="c1"/&gt;
          &lt;/CharNode&gt;
          &lt;CharNode&gt;
            &lt;Parent ref="cn2"/&gt;
            &lt;Character ref="c2"/&gt;
          &lt;/CharNode&gt;
          &lt;CharNode&gt;
            &lt;Parent ref="cn2"/&gt;
            &lt;Character ref="c3"/&gt;
          &lt;/CharNode&gt;
          &lt;Node id="cn3"&gt;
            &lt;Parent ref="cn1"/&gt;
            &lt;DescriptiveConcept ref="dc3"/&gt;
          &lt;/Node&gt;
          &lt;CharNode&gt;
            &lt;Parent ref="cn3"/&gt;
            &lt;Character ref="c4"/&gt;
          &lt;/CharNode&gt;
          &lt;CharNode&gt;
            &lt;Parent ref="cn3"/&gt;
            &lt;Character ref="c5"/&gt;
          &lt;/CharNode&gt;
          &lt;Node id="cn4"&gt;
            &lt;DescriptiveConcept ref="dc4"/&gt;
          &lt;/Node&gt;
          &lt;CharNode&gt;
            &lt;Parent ref="cn4"/&gt;
            &lt;Character ref="c6"/&gt;
          &lt;/CharNode&gt;
          &lt;CharNode&gt;
            &lt;Parent ref="cn4"/&gt;
            &lt;Character ref="c7"/&gt;
          &lt;/CharNode&gt;
          &lt;CharNode&gt;
            &lt;Parent ref="cn4"/&gt;
            &lt;Character ref="c8"/&gt;
          &lt;/CharNode&gt;
        &lt;/Nodes&gt;
      &lt;/CharacterTree&gt;
    &lt;/CharacterTrees&gt;
</code></pre>
</td>
</tr>
</table>

<p>The first node in this tree, node "cn1" references the descriptive concept "dc1" (Flowers). The second node, "cn2",  references the descriptive concept "dc2" (Petals). The third node, "cn3", references the first true character in the hierarchy, "c1" (Petal number). Each node references it's parent (the node supporting the character "Petal number" references the descriptive concept "Petals" which is its immediate parent) and the character or concept which is tied to it. If a descriptive concept is tied to a node this is declared within the &lt;Node&gt; element, if a character is tied to a node this is declared in a &lt;CharNode&gt; element, which references its supporting node.</p>

<p>The &lt;Representation&gt; element provides a label for the character tree. This may be useful if the instance document includes multiple trees for different purposes, or is intended for publication in multiple languages (see the topic Language support in SDD).</p>

<p>&lt;DesignedFor&gt; specifies this character tree's purpose. Important roles are interactive identification, natural language reporting, or filtering.</p>

<p>The &lt;Nodes&gt; element is used to define the structure of the character tree. It contains an unordered list of &lt;Node&gt; and &lt;Char&gt; elements, each of which specifies a parent &lt;Node&gt;. The list can be used by a consuming application to construct a character tree.</p>

<p>The &lt;CharacterTrees&gt; element is also used to declare <a href="SddDependencies.html">dependencies</a></p>

<p>-- Main.DonovanSharp - 01 Jun 2006</p>


            </body>
            </html>