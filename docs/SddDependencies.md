<html>
            <head>
                <title>SddDependencies - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>HeleneFradin - Fri Jul 27 2007 - Version 1.11<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard </h2>

<h3>3.11 Dependencies in SDD</h3>

<p>   Dependencies are logical relationships between characters such that a state of one character controls the presence (or absence) of another feature in interactive keys.</p>

<p>Consider, for example, the following features:</p>

<p><a href="SddDependencies/depend.jpg"><img src="SddDependencies/depend.jpg"/></a>   Wing colour and Wing shape only have meaning when wings are present &#8211; if wings are absent, they are logically inappropriate in the key. Relationships of this kind are generally accomodated within interactive identification applications by the use of dependencies. For the above example a negative dependency may be set such that if a user chooses the state Wings: absent, then the characters Wing Colour and Wing Shape will be removed from characters Available. Alternatively, some applications allow a positive dependency to be set so for example Wing Colour and Wing Shape are initially hidden and only appear if a user chooses the state Wings: present. Dependencies can help to keep the character list cleaner and less cluttered, and help make some features work better.</p>

<p>In SDD dependencies are defined by &lt;DependencyRules&gt; within the &lt;CharacterTree&gt; element.</p>

<p>A simple SDD code instance representing dependency definition has the basic structure shown below and in Example 3.11.1.</p>

<p><a href="SddDependencies/chartreenodeseq.gif"><img src="SddDependencies/chartreenodeseq.gif"/></a></p>

<h4>Example 3.11.1 - Negative dependencies in SDD.</h4>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>
  
<pre><code>        &lt;Nodes&gt;
          &lt;CharNode&gt;
            &lt;DependencyRules&gt;
              &lt;InapplicableIf&gt;
                &lt;State ref="s13"/&gt;
              &lt;/InapplicableIf&gt;
            &lt;/DependencyRules&gt;
            &lt;Character ref="c1"/&gt;
          &lt;/CharNode&gt;
          &lt;CharNode&gt;
            &lt;DependencyRules&gt;
              &lt;InapplicableIf&gt;
                &lt;State ref="s4"/&gt;
                &lt;State ref="s13"/&gt;
              &lt;/InapplicableIf&gt;
            &lt;/DependencyRules&gt;
            &lt;Character ref="c2"/&gt;
          &lt;/CharNode&gt;

		  ... etc.
		  
        &lt;/Nodes&gt; 
</code></pre>
	
</td>
</tr>

</table>

<p>Positive dependencies are expressed in the same fashion with the &lt;InapplicableIf&gt; tag. Applicable-If and Inapplicable-If statements are in principle convertible, but </p>

<h3>Discussion</h3>

<p>It is currently unknown how applications which enforce referential integrity between scored data and dependencies will manage data imported from applications which do not enforce referential integrity. -- Main.DonovanSharp - 01 Jun 2006</p>

<p>Does Lucid have problems with this? <nop>DeltaAccess/DiversityDescriptions does maintain referential integrity between applicability rules and terminology, and between terminology and data, but not between applicability rules and data. The main reason for not doing this is that it would prevent creating a desirable applicability rule before all violating data (which may be hundreds) have been removed first. Instead, DiversityDescriptions allows violation of dependency rules, but warns the user, enabling him or her to fix the violations as time goes by. It is thus an application-level integrity, not a database-level one. -- Main.GregorHagedorn, 2007-05-07.</p>

<p>As a use case example, the XPer2 software deals with character dependencies using an inapplicability rules and a set of exclusion modes. However, the displaying in the identification interface relates more to the positive approach: characters are displayed to the user only once a mode or several modes (distinct from the exclusion(s) mode(s)) has(have) been selected. -- Main.HeleneFradin - 27 Jul 2007</p>

<p>As SDD dependencies are defined in a &lt;CharacterTree&gt; element, I think I would need an example that includes a character hierarchy to understand better if the character under the rule of applicability has to be hierarchically dependent from the character that displays the &lt;InapplicableIf&gt; state (my understanding is that it is not necessary) and to distinguish clearly the character that is attached to the &lt;CharNode&gt; element and the potential parent character. I tried to build an example from the schema above about Wings characters. Is it correct ?</p>

<table bgcolor="#ddddff" border="0" width="100%" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111">

<tr>
<td>
  
<pre><code>        &lt;Characters&gt;
          &lt;CategoricalCharacter id="c1"&gt;
            &lt;Representation&gt;
              &lt;Label&gt;Presence&lt;/Label&gt;
            &lt;/Representation&gt;
            &lt;States&gt;
              &lt;StateDefinition id="s1"&gt;
                &lt;Representation&gt;
                  &lt;Label&gt;present&lt;/Label&gt;
                &lt;/Representation&gt;
              &lt;/StateDefinition&gt;
              &lt;StateDefinition id="s2"&gt;
                &lt;Representation&gt;
                  &lt;Label&gt;absent&lt;/Label&gt;
                &lt;/Representation&gt;
              &lt;/StateDefinition&gt;
            &lt;/States&gt;
          &lt;CategoricalCharacter id="c2"&gt;
            &lt;Representation&gt;
              &lt;Label&gt;Colour&lt;/Label&gt;
            &lt;/Representation&gt;
            &lt;States&gt;
              &lt;StateDefinition id="s3"&gt;
                &lt;Representation&gt;
                  &lt;Label&gt;blue&lt;/Label&gt;
                &lt;/Representation&gt;
              &lt;/StateDefinition&gt;
              &lt;StateDefinition id="s4"&gt;
                &lt;Representation&gt;
                  &lt;Label&gt;yellow&lt;/Label&gt;
                &lt;/Representation&gt;
              &lt;/StateDefinition&gt;
            &lt;/States&gt;

        ...

        &lt;/Characters&gt;

        &lt;DescriptiveConcepts&gt;
          &lt;DescriptiveConcept id="dc1"&gt;
            &lt;Representation&gt;
              &lt;Label&gt;Wings&lt;/Label&gt;
            &lt;/Representation&gt;
      	  &lt;/DescriptiveConcept&gt;
        &lt;/DescriptiveConcepts&gt;

        ... etc (for more detail see the topic &lt;DescriptiveConcepts&gt;)

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
              &lt;CharNode&gt;
	        &lt;Parent ref="cn1"/&gt;
            	&lt;Character ref="c1"/&gt;
	      &lt;/CharNode&gt;
              &lt;CharNode&gt;
	        &lt;DependencyRules&gt;
                  &lt;InapplicableIf&gt;
                    &lt;State ref="s2"/&gt;
    	          &lt;/InapplicableIf&gt;
         	&lt;/DependencyRules&gt;
                &lt;Parent ref="cn1"/&gt;
            	&lt;Character ref="c2"/&gt;
              &lt;/CharNode&gt;

        ...

            &lt;/Nodes&gt;
          &lt;/CharacterTree&gt;
        &lt;/CharacterTrees&gt;
</code></pre>
	
</td>
</tr>

</table>

<p>-- Main.HeleneFradin - 27 Jul 2007</p>


            </body>
            </html>