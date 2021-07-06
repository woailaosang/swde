# swde
*Structured Web Data Extraction*

A dataset for structured data extraction from web pages.

<div class="wikidoc">
<p><span style="font-size:10.5pt"><strong>Motivation</strong></span></p>
<p>This dataset is a real-world web page collection used for research on the automatic extraction of structured data (e.g., attribute-value pairs of entities) from the Web. We hope it could serve as a useful benchmark for evaluating and comparing different
 methods for structured web data extraction.</p>
<p><strong><span style="font-size:10.5pt">Contents of the Dataset</span></strong></p>
<p>Currently the dataset involves:</p>
<ul>
<li><span style="color:#0000ff"><strong>8 verticals </strong></span>with diverse semantics;
</li><li><span style="color:#0000ff"><strong>80 web sites </strong></span>(10 per vertical);
</li><li><span style="color:#0000ff"><strong>124,291 web pages </strong></span>(200~2,000 per web site), each containing a single data record with detailed information of an entity;
</li><li><span style="color:#0000ff"><strong>32 attributes </strong></span>(3~5 per vertical) associated with
<span style="color:#0000ff"><strong>carefully labeled ground-truth</strong></span> of corresponding values in each web page. The goal of structured data extraction is to automatically identify the values of these attributes from web pages.
</li></ul>
<p>The involved verticals are summarized as follows:</p>
<table border="0" align="left">
<tbody>
<tr align="center">
<td>Vertical</td>
<td>#Sites</td>
<td>#Pages</td>
<td>#Attributes</td>
<td align="center" valign="middle">Attributes</td>
</tr>
<tr>
<td align="center" valign="middle"><em>Auto</em></td>
<td align="center" valign="middle">10</td>
<td align="center" valign="middle">17,923</td>
<td align="center" valign="middle">4</td>
<td align="center" valign="middle">model, price, engine, fuel_economy</td>
</tr>
<tr>
<td align="center" valign="middle"><em>Book</em></td>
<td align="center" valign="middle">10</td>
<td align="center" valign="middle">20,000</td>
<td align="center" valign="middle">5</td>
<td align="center" valign="middle">title, author, isbn_13, publisher, publication_date</td>
</tr>
<tr>
<td align="center" valign="middle"><em>Camera</em></td>
<td align="center" valign="middle">10</td>
<td align="center" valign="middle">&nbsp; 5,258</td>
<td align="center" valign="middle">3</td>
<td align="center" valign="middle">model, price, manufacturer</td>
</tr>
<tr>
<td align="center" valign="middle"><em>Job</em></td>
<td align="center" valign="middle">10</td>
<td align="center" valign="middle">20,000</td>
<td align="center" valign="middle">4</td>
<td align="center" valign="middle">title, company, location, date_posted</td>
</tr>
<tr>
<td align="center" valign="middle"><em>Movie</em></td>
<td align="center" valign="middle">10</td>
<td align="center" valign="middle">20,000</td>
<td align="center" valign="middle">4</td>
<td align="center" valign="middle">title, director, genre, mpaa_rating</td>
</tr>
<tr>
<td align="center" valign="middle"><em>NBA Player</em></td>
<td align="center" valign="middle">10</td>
<td align="center" valign="middle">&nbsp; 4,405</td>
<td align="center" valign="middle">4</td>
<td align="center" valign="middle">name, team, height, weight</td>
</tr>
<tr>
<td align="center" valign="middle"><em>Restaurant</em></td>
<td align="center" valign="middle">10</td>
<td align="center" valign="middle">20,000</td>
<td align="center" valign="middle">4</td>
<td align="center" valign="middle">name, address, phone, cuisine</td>
</tr>
<tr>
<td align="center" valign="middle"><em>University</em></td>
<td align="center" valign="middle">10</td>
<td align="center" valign="middle">16,705</td>
<td align="center" valign="middle">4</td>
<td align="center" valign="middle">name, phone, website, type</td>
</tr>
</tbody>
</table>
<p><br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
</p>
<p><span lang="EN-US" style="font-size:10.5pt"><strong>Format of Web Pages</strong></span></p>
<p>Each web page in the dataset is stored as one <strong>.htm</strong> file (in UTF-8 encoding) where the first tag encodes the source URL of the page.</p>
<p><span lang="EN-US" style="font-size:10.5pt"><strong>Format of Ground-truth Files</strong></span></p>
<p>For each web site, the page-level ground-truth of attribute values&nbsp;has been labeled using handcrafted regular expressions and stored in
<strong>.txt</strong> files (in UTF-8 encoding) named as &quot;<strong>&lt;</strong><em>vertical</em><strong>&gt;-&lt;</strong><em>site</em><strong>&gt;-&lt;</strong><em>attribute</em>&quot;.txt&quot;.</p>
<p>In each such file:</p>
<ul>
<li>The first line stores the names of vertical, site, and attribute, separated by TAB characters ('\t').
</li><li>The second line stores some statistics (separated by TABs) w.r.t. the corresponding site and attribute, including:
<ol>
<li>the total number of pages, </li><li>the number of pages containing attribute values, </li><li>the total number of attribute values contained in the pages, </li><li>the number of unique attribute values. </li></ol>
</li><li>Each remaining line stores the ground-truth information (separated by TABs) of one page, in sequence of:
<ol>
<li>page ID, </li><li>the number of attribute values in the page, </li><li>attribute values (&quot;&lt;NULL&gt;&quot; in case of non-existence). </li></ol>
</li></ul>
<p><span lang="EN-US" style="font-size:10.5pt"><strong>Notes on Ground-truth Labeling</strong></span></p>
<ul>
<li>The ground-truth labeling was conducted in the DOM-node level. More specifically, the candidate attribute values in a web page are the non-empty strings contained in text nodes in the corresponding DOM tree.
</li><li>One page (although containing a single data record) may contain multiple distinct values that correspond to an attribute (e.g., multiple
<em>authors</em> of a book, multiple granularity levels of <em>addresses</em>). </li><li>Currently, when a text node presents a mixture of multiple attributes, its string value is labeled with each of these attributes, if no substitute is available.
</li><li>Before being stored in .txt files, the raw attribute values were refined by removing redundant&nbsp;separators (e.g., ' ', '\t', '\n').
</li></ul>
<p><span lang="EN-US" style="font-size:10.5pt"><strong>How to Download</strong></span></p>
<p>You can access the latest version of this dataset (associated with ground-truth, sample code, website list, and readme file) from
<a href="http://swde.codeplex.com/SourceControl/list/changesets" target="_blank">
HERE</a>.</p>
<p><span lang="EN-US"><strong>Reference</strong></span></p>
<p>We would appreciate it if you cite the following paper when using the dataset:</p>
<p><span style="font-size:10pt">Qiang Hao, Rui Cai, Yanwei Pang, and Lei Zhang. &quot;From One Tree to a Forest: a Uniﬁed Solution for Structured Web Data Extraction&quot;. in Proc. of the 34th International ACM SIGIR Conference on Research and Development in Information
 Retrieval (SIGIR 2011), pp.775-784, Beijing, China. July 24-28, 2011.</span></p>

<p><span lang="EN-US"><strong>Original Archive</strong></span></p>
https://archive.codeplex.com/?p=swde
