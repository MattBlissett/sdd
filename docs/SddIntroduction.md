<html>
            <head>
                <title>SddIntroduction - SDD Primer</title>
                <meta charset="utf-8">
                <style>body { margin: 1em auto; max-width: 1000px; font-size: 16px; font-family: sans-serif; }</style>
            </head>
            <body>
                <p>KevinThiele - Fri Sep 15 2006 - Version 1.19<br> <a href="SddContents.html">Parent topic: SddContents</a><br></p>

<h2>SDD Part 0: Introduction and Primer to the SDD Standard</h2>

<h3>Abstract</h3>

<p>SDD Part 0 is a non-normative introduction to the <a href="http://www.tdwg.org">Taxonomic Databases Working Group</a> SDD (Structure of Descriptive Data) Standard. Its intention is to provide a background, introduction and primer to the SDD Standard, with examples. Since the SDD Standard is a work-in-progress, this document will be updated from time to time.</p>

<h3>Status of this document and version history</h3>

<p>See <a href="DocumentStatus.html">DocumentStatus</a></p>

<h2>1.0 Introduction</h2>

<h3>1.1 Background to the TDWG-SDD Subgroup</h3>

<p>In September 1998 the <a href="http://www.tdwg.org">Taxonomic Databases Working Group </a> (TDWG) of the <a href="http://www.iubs.org">International Union of Biological Sciences</a> (IUBS) established the Structure of Descriptive Data (SDD) subgroup. TDWG&#8217;s role is to facilitate and manage the development of international standards in the taxonomic domain. The SDD subgroup was established to develop an international XML-based standard for capturing and managing descriptive data for organisms.</p>

<p>Development of the SDD standard was initiated in response to recognition that the existing standard previously endorsed by TDWG &#8211; the <a href="http://delta-intkey.com/">DELTA</a> data standard developed at CSIRO in Canberra from 1971 and adopted by TDWG as a descriptive data standard in 1991 &#8211; had become inadequate <a href="SddFaq.html">(FAQ: Why not continue to use DELTA?)</a>.</p>

<p>The SDD subgroup began discussing and scoping a standard through an email discussion group in November 1999 (see the <a href="http://listserv.nhm.ku.edu/archives/tdwg-sdd.html">SDD email list archives</a>). Considerable progress has been made at face-to-face meetings amongst a small group of core contributors, in Nov. 2001 (Canberra), Oct. 2002 (Sao Paulo), Feb. 2003 (Paris), October 2003 (Lisbon), May 2004 (Berlin) and Oct. 2004 (Christchurch).</p>

<h3>1.2 The nature of descriptive data in taxonomy</h3>

<p>In taxonomy, descriptive data takes a number of very different forms.</p>

<p>Natural-language descriptions (Box 1.2.1) are semi-structured, semi-formalised descriptions of a taxon (or occasionally of an individual specimen). They may be simple, short and written in plain language (if used for a popular field guide), or long, highly formal and using specialised terminology when used in a taxonomic monograph or other treatment.</p>

<h4>Box 1.2.1 -  A typical natural language description</h4>

<table bgcolor="#ddddff" cellspacing="2" cellpadding="2" border="1" width="80%">
<tr>
    <td>
  <p align="left">
  <b>Red Knot (Calidris canutus)</b><br>
  Stout wader with bill same length as head, crown unstreaked, narrow white bar 
	in wing, pale rump with grey barring, shortish olive legs. Non-breeding: 
	grey above with narrow pale edging to feathers, pale eyebrow, smudged sides 
	to neck with faint spotting. Juvenile: feathers of back edged white with 
	dark subterminal bar, breast more heavily spotted pale buff and flanks 
	barred, crown faintly streaked. Breeding: rufous underparts, feathers of 
	back rufous patterned with black. Voice: 'knut-knut', `nyui , high-pitched `toowit-wit'.</p>
  <p align="right">
from Slater, P., Slater, P. &amp; Slater, R. (2001) The Slater Field Guide to 
Australian Birds&nbsp; (Reed New Holland: Sydney)</p>
</td>
</tr>
</table>

<p>  Dichotomous keys (Box 1.2.2) are specialised identification tools comprising fragments of descriptive data arranged in couplets forming a branching tree. Each fragment (lead) comprises a small (occasionally verbose) natural-language description.</p>

<h4>Box 1.2.2 -  A simple dichotomous key</h4>

<p>	<div>
		<table bgcolor="#ddddff" border="1" cellpadding="5" style="border-collapse: collapse" bordercolor="#111111" width="80%" id="table8">
			<tr>
				<td style="border-left-style: solid; border-left-width: 1px; border-right-style: none; border-right-width: medium; border-top-style: solid; border-top-width: 1px; border-bottom-style: none; border-bottom-width: medium" colspan="3">
				<b>Key to Australian skinks in the genus <i>Ctenotus</i></b></td>
			</tr>
			<tr>
				<td width="50" style="border-left-style: solid; border-left-width: 1px; border-right-style: none; border-right-width: medium; border-top-style: solid; border-top-width: 1px; border-bottom-style: none; border-bottom-width: medium">1</td>
				<td style="border-left-style: none; border-left-width: medium; border-right-style: none; border-right-width: medium; border-top-style: solid; border-top-width: 1px; border-bottom-style: none; border-bottom-width: medium">Dark upper lateral zone with one or more distinct series of 
				pale spots or blotches along the body</td>
				<td width="114" valign="bottom" align="right" style="border-left-style: none; border-left-width: medium; border-right-style: solid; border-right-width: 1px; border-top-style: solid; border-top-width: 1px; border-bottom-style: none; border-bottom-width: medium">2</td>
			</tr>
			<tr>
				<td width="50" style="border-left-style: solid; border-left-width: 1px; border-right-style: none; border-right-width: medium; border-top-style: none; border-top-width: medium; border-bottom-style: none; border-bottom-width: medium">1a</td>
				<td style="border-style: none; border-width: medium">Dark upper lateral zone obscurely mottled or uniform with at 
				most a few pale spots anteriorly</td>
				<td width="114" valign="bottom" align="right" style="border-left-style: none; border-left-width: medium; border-right-style: solid; border-right-width: 1px; border-top-style: none; border-top-width: medium; border-bottom-style: none; border-bottom-width: medium">3</td>
			</tr>
			<tr>
				<td width="50" style="border-left-style: solid; border-left-width: 1px; border-right-style: none; border-right-width: medium; border-top-style: none; border-top-width: medium; border-bottom-style: none; border-bottom-width: medium">2</td>
				<td style="border-style: none; border-width: medium">Fewer than 25 lamellae under the fourth toe; supralabials 7-8 (usually 7); prefrontals separated</td>
				<td width="114" valign="bottom" align="right" style="border-left-style: none; border-left-width: medium; border-right-style: solid; border-right-width: 1px; border-top-style: none; border-top-width: medium; border-bottom-style: none; border-bottom-width: medium">
				<i>C. arcanus</i></td>
			</tr>
			<tr>
				<td width="50" style="border-left-style: solid; border-left-width: 1px; border-right-style: none; border-right-width: medium; border-top-style: none; border-top-width: medium; border-bottom-style: none; border-bottom-width: medium">2a</td>
				<td style="border-style: none; border-width: medium">More than 25 lamellae under the fourth toe; supralabials 8-9 
				(usually 8); prefrontals usually in contact</td>
				<td width="114" valign="bottom" align="right" style="border-left-style: none; border-left-width: medium; border-right-style: solid; border-right-width: 1px; border-top-style: none; border-top-width: medium; border-bottom-style: none; border-bottom-width: medium">
				<i>C. alleni</i></td>
			</tr>
			<tr>
				<td width="50" style="border-left-style: solid; border-left-width: 1px; border-right-style: none; border-right-width: medium; border-top-style: none; border-top-width: medium; border-bottom-style: none; border-bottom-width: medium">3</td>
				<td style="border-style: none; border-width: medium">Pale mid-lateral stripe passes over the hindlimb to continue 
				along the tail </td>
				<td width="114" valign="bottom" align="right" style="border-left-style: none; border-left-width: medium; border-right-style: solid; border-right-width: 1px; border-top-style: none; border-top-width: medium; border-bottom-style: none; border-bottom-width: medium">
				<i>C. inornatus</i></td>
			</tr>
			<tr>
				<td width="50" style="border-left-style: solid; border-left-width: 1px; border-right-style: none; border-right-width: medium; border-top-style: none; border-top-width: medium; border-bottom-style: solid; border-bottom-width: 1px">3a</td>
				<td style="border-left-style: none; border-left-width: medium; border-right-style: none; border-right-width: medium; border-top-style: none; border-top-width: medium; border-bottom-style: solid; border-bottom-width: 1px">Pale mid-lateral stripe extends to groin, then continues 
				along the front edge of the hindlimb</td>
				<td width="114" valign="bottom" align="right" style="border-left-style: none; border-left-width: medium; border-right-style: solid; border-right-width: 1px; border-top-style: none; border-top-width: medium; border-bottom-style: solid; border-bottom-width: 1px">
				<i>C. coggeri</i></td>
			</tr>
		</table>
</div>   Coded descriptions (Box 1.2.3) comprise highly structured data used in computer identification and analysis programs such as Lucid (<a href="http://www.lucidcentral.org">www.lucidcentral.org</a>) , DELTA (<a href="http://www.delta-intkey.com">www.delta-intkey.com</a>) and phylogenetic analysis programs such as PAUP (<a href="http://www.paup.csit.fsu.edu">www.paup.csit.fsu.edu</a>).</p>

<h4>Box 1.2.3 -  Simple examples of coded descriptions</h4>

<div>

<table bgcolor="#ddddff" border="0" cellpadding="5" cellspacing="5" style="border-collapse: collapse" bordercolor="#111111" width="80%" id="table9">
  <tr>
    <td width="50%">


<div>


Lucid Interchange Format (LIF) file</div>


#Lucid Interchange Format File v. 2.1<br>
<br>
[..Character List..]<br>
Distribution by region<br>
&nbsp; Tropical North<br>
&nbsp; Subtropical and Temperate East and South<br>
&nbsp; South West<br>
&nbsp; Arid &amp; Semi-arid (Central)<br>
&nbsp; Island Territories<br>
General habit<br>
&nbsp; tree<br>
&nbsp; shrub<br>
&nbsp; climber (woody or herbaceous)<br>
&nbsp; herb<br>
&nbsp; grass- or sedge-like plant<br>
Seasonal longevity<br>
&nbsp; annual, biennial or ephemeral<br>
&nbsp; perennial<br>
<br>
[..Taxon List..]<br>
Acanthaceae<br>
Aceraceae<br>
Actinidiaceae<br>
Agavaceae<br>
Aizoaceae<br>
Akaniaceae<br>
Alangiaceae<br>
Alismataceae<br>
Aloaceae<br>
Alseuosmiaceae<br>
<br>
[..Main Data (txs)..]<br>
101101111111<br>
100100000101<br>
101000000010<br>
011110111111<br>
101111111111<br>
100100000011<br>
101101000011<br>
011111011111<br>
011100100111<br>
101100000010</div>

<p>    </td>     <td width="50%"></p>

<div>
DELTA file</div>

<p>*SHOW: Gentianella - character list. Last revised 16 April 1997.<br> <br> *CHARACTER LIST <br> <br> #1. plants/<br> 1. monocarpic/<br> 2. polycarpic/<br> <br> #2. &lt;plants lifecycle&gt;/<br> 1. annual/<br> 2. biennial/<br> 3. perennial/<br> <br> #3. height in flower/<br> &lt;&gt; cm/<br> <br> #4. caudex/<br> 1. unbranched/<br> 2. branched/<br> <br> *ITEM DESCRIPTIONS <br> <br> # Gentianella amabilis/<br> 1,2 2,3 3,3-13 4,1<br> <br> # Gentianella antarctica/<br> 1,1 2,1&lt;Godley 1982&gt; 3,1.6-22.0&lt;Godley 1982&gt; 4,1<br> <br> # Gentianella antipoda/<br> 1,1&lt;Godley 1982&gt; 2,2 3,3.5-9.8-24 4,1/2&lt;depends on size of plant&gt;<br> <br> # Gentianella astonii/<br> 1,2 2,3 3,15 4,2<br> <br> # Gentianella cerina/<br> 1,2 2,3 3,9-17 4,1/2<br> <br> #Gentianella concinna/<br> 1,1 2,1 3,2.7-15.0 4,1<br> &nbsp;</div></p>

<p>    </td>     <td width="50%">&nbsp;<p>&nbsp;</td>   </tr> </table></p>

<p></div></p>

<p>  Raw data descriptions (Box 1.2.4) usually comprise repeated measurements of parts of individual specimens, and are the basis from which the more abstracted descriptions in natural language and coded descriptions are derived. Few taxonomists consistently record and archive their raw data in a standardised format. </p>

<h4>Box 1.2.4 - Example of raw (specimen) descriptive data</h4>

<p>  <div>
	<table bgcolor="#ddddff" border="1" width="80%" cellspacing="0" id="table10" cellpadding="0">
		<tr>
			<td rowspan="2" align="center">Specimen</td>
			<td colspan="5" align="center">Spore length</td>
			<td colspan="5" align="center">Spore width</td>
			<td width="163" rowspan="2" align="center">Spore colour</td>
		</tr>
		<tr>
			<td width="25" align="center">1</td>
			<td width="25" align="center">2</td>
			<td width="25" align="center">3</td>
			<td width="25" align="center">4</td>
			<td width="25" align="center">5</td>
			<td width="25" align="center">1</td>
			<td width="25" align="center">2</td>
			<td width="25" align="center">3</td>
			<td width="25" align="center">4</td>
			<td width="25" align="center">5</td>
		</tr>
		<tr>
			<td align="center">TJM45337</td>
			<td width="25" align="center">12</td>
			<td width="25" align="center">13</td>
			<td width="25" align="center">12</td>
			<td width="25" align="center">15</td>
			<td width="25" align="center">11</td>
			<td width="25" align="center">8</td>
			<td width="25" align="center">8</td>
			<td width="25" align="center">7</td>
			<td width="25" align="center">6</td>
			<td width="25" align="center">6</td>
			<td width="163" align="center">brown</td>
		</tr>
		<tr>
			<td align="center">TLM33466</td>
			<td width="25" align="center">15</td>
			<td width="25" align="center">18</td>
			<td width="25" align="center">17</td>
			<td width="25" align="center">17</td>
			<td width="25" align="center">15</td>
			<td width="25" align="center">10</td>
			<td width="25" align="center">8</td>
			<td width="25" align="center">9</td>
			<td width="25" align="center">9</td>
			<td width="25" align="center">10</td>
			<td width="163" align="center">yellow</td>
		</tr>
	</table>
	</div>  </p>

<h3>1.3 Goals of SDD</h3>

<p>The goal of the SDD standard is to allow capture, transport, caching and archiving of descriptive data in all the forms shown above, using a platform- and application-independent, international standard. Such a standard is crucial to enabling lossless porting of data between existing and future software platforms including identification, data-mining and analysis tools, and federated databases.</p>

<h4>The SDD Standard:</h4>

<ul>
  <li>provides a flexible, platform-independent data structure for the capture and storage of taxonomic descriptions </li>
  <li>comprises a superset of data requirements of all existing programs </li>
  <li>provides extension beyond existing programs where data requirements can be predicted </li>
  <li>is readily extensible to account for future developments and data requirements </li>
  <li>is human-readable (although it is assumed that in almost all cases standard descriptions will be machine-generated and processed) </li>
  <li>is XML-based, and provides a schema for validation of documents. </li>
</ul>

<h4>It facilitates:</h4>

<ul>
  <li>lossless porting of data between standard-aware applications </li>
  <li>achievable progressive markup of legacy descriptions, particularly natural-language descriptions </li>
  <li>comparability and, if possible, combinability of alternate descriptions of any one taxon </li>
  <li>efficient multi-tasking of descriptions (one description serving alternate purposes) </li>
  <li>archiving and sharing of raw and processed data</li>
</ul>

<h4>SDD documents may include all or some of the following:</h4>

<ul>
  <li>Terminologies (characters, states, modifiers, char. trees, higher concepts) </li>
  <li>Structured (coded) data </li>
  <li>Sample data (e. g., measurements) </li>
  <li>Unstructured natural language data </li>
  <li>Natural language data with markup </li>
  <li>Dichotomous or polytomous keys </li>
  <li>Resources associated with descriptions (e. g., images, references, links) </li>
</ul>

<h3>SDD is currently not designed to accommodate:</h3>

<ul>
  <li>Molecular sequence and other genetic data (future plans exist)</li>
  <li>Occurrence and specimen data (e. g., distribution maps) </li>
  <li>Complex ecological data such as models and ecological observations </li>
  <li>Organism interactions (host-parasite, plant-pollinator, predator-prey, etc.)</li>
  <li>Nomenclatural and formal systematic (rank) information</li>
</ul>

<h3>1.4 SDD Streams</h3>

<p>This Primer is structured into several streams, each describing how SDD can help you with a specific task. For each stream, the Primer describes the core elements of SDD used to capture information related to the task, and provides examples extending from simple to complex. </p>

<p>The four main tasks (uses) of SDD are as follows:</p>

<ul>
  <li><a href="CodedData.html">Using SDD for coded summary descriptions</a></li>
  <li><a href="CodedSampleDescription.html">Using SDD for coded raw (sample) descriptions</a></li>
  <li><a href="NaturalLanguageDescriptions.html">Using SDD for natural language descriptions</a></li>
  <li><a href="DichotomousKeys.html">Using SDD for dichotomous (or polytomous) identification keys</a></li>
</ul>

<p>Choose a link above to enter one of the SDD streams. </p>

<p>In addition to the streams, a number of SDD elements are common to all streams. Choose a link below to find out how to:</p>

<ul>
  <li><a href="TechnicalMetadata.html">Describe metadata for a providing application</a></li>
  <li><a href="DatasetMetadata.html">Describe metadata for an SDD dataset</a></li>
  <li><a href="SddMedia.html">Attach media (images etc) to SDD items</a></li>
</ul>

<p>-- Main.KevinThiele - 07 Jul 2006</p>
            </body>
            </html>