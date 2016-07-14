# DocBook XML export from Booktype

We are adding a new export/publish format to www.booktype.pro: DocBook XML.

This repo contains sub-set of DocBook elements that we will use. The typical workflow for authors and publishers using Booktype would be:

* Create a book by importing DOCX or EPUB or starting it in the browser.
* Edit the book in the browser - alone or in teams.
* Export the book to DocBookXML (other output formats are PDF, EPUB, MOBI, XHTML site, ...)

It is important to note that the DocBook XML structure is not limiting the book creation and editing process. On export, the existing book will be converted into valid DocBook XML. We are using DocBook version 5.1.

## Information about DocBook:
* http://docbook.org/tdg51/en/html/docbook.html
* The complete reference: http://docbook.org/tdg51/en/html/chunk-part-d64e10384.html

## Information about Booktype:
* https://booktype.pro
* Features: https://booktype.pro/en/booktype/screenshots/
* Try it online at https://omnibook.pro/

You can find the lists of all elements of our sub-set with detailed descriptions in the elements folder. 

Here an example of the content skeleton:
```
    <part label="###Frontmatter"> 
      <title>Part title for table of contents</title> 
      <chapter label="ChapterTitleFromToC" id="chapterURL">
        <info>
          <title>Foreword</title>
        </info>
        <section role="h1">
          <title>Heading</title>
          <para>...</para>
          ...
        </section>
        <section role="h2">
          <title>Subheading</title>
          <para>...</para>
          ...
        </section>
        <section role="h3">
          <title>Subsubheading</title>
          <para>...</para>
          ...
        </section>
        ...
      </chapter>
      <chapter label="ChapterTitleFromToC" id="chapterURL">
        ...
      </chapter>
    </part>
```

# Elements in the document

## Book - the wrapper around everything

```
<book xmlns='http://docbook.org/ns/docbook'>
<title>%title%</title>
<titleabbrev>short-title</titleabbrev>
<subtitle>%subtitle%</subtitle>
<info>
  <legalnotice><para>%rights%</para></legalnotice>
  <author xml:base="%url_author%"><givenname>%author%</givenname></author>
  <editor><givenname>%author%</givenname></editor>
  <publisher>
    <publishername>%publisher%</publishername>
    <city>%publisher_city%</city>
    <uri>%url_publisher%</uri>
  </publisher>
  <abstract><para>%short_description%</para></abstract>
  <copyright>
    <year>%dateCopyrighted%</year>
    <holder>%rights_holder%</holder>
  </copyright>
  <biblioid>
    <isbn>%???%</isbn>
  </biblioid>
  <edition>%as edition%</edition>

  <othercredit class="coverdesigner">
    <personname><givenname>%cover_design%</givenname></personname>
  </othercredit>
  <othercredit class="translator">
    <personname><givenname>%translation_by%</givenname></personname>
  </othercredit>
  <othercredit class="illustrator">
    <personname><givenname>%illustration_by%</givenname></personname>
  </othercredit>
  <othercredit class="proofreader">
    <personname><givenname>%proofreading%</givenname></personname>
  </othercredit>
  
  <othercredit otherclass="photographer">
    <personname><givenname>%photography%</givenname></personname>
  </othercredit>
  <othercredit otherclass="cover_photography">
    <personname><givenname>%cover_photography%</givenname></personname>
  </othercredit>
  <othercredit otherclass="lectorate">
    <personname><givenname>%lectorate%</givenname></personname>
  </othercredit>
  <othercredit otherclass="rights_clearing">
    <personname><givenname>%rights_clearing%</givenname></personname>
  </othercredit>
  <othercredit otherclass="research">
    <personname><givenname>%research%</givenname></personname>
  </othercredit>
  <othercredit otherclass="text_by">
    <personname><givenname>%text_by%</givenname></personname>
  </othercredit>
  <othercredit otherclass="introduction_by">
    <personname><givenname>%introduction_by%</givenname></personname>
  </othercredit>
  
  <bibliomisc role="ebook_isbn">%ebook_isbn%</bibliomisc>
  <bibliomisc role="bibliographic_information">%bibliographic_information%</bibliomisc>
  <bibliomisc role="typeface">%typeface%</bibliomisc>
  <bibliomisc role="printed_on">%printed_on%</bibliomisc>
  <bibliomisc role="bookbinder">%bookbinder%</bibliomisc>
  <bibliomisc role="printer">%printer%</bibliomisc>
  <bibliomisc role="printer_country">%printer_country%</bibliomisc>
  <bibliomisc role="paper_certification">%paper_certification%</bibliomisc>
</info>
<acknowledgements><para>...</para></acknowledgements>
<dedication><para>This book is dedicated to you.</para></dedication>
<part>...
<chapter>...
...
</book>
```
(see: http://docbook.org/tdg51/en/html/book.html)

## Part
```
<part label="###Frontmatter"> 
  <title>Part title for table of contents</title> 
  ...
</part>
```

* The print title is in the `title` tag.
* A book does not necessarily have parts as a structure.
* A part is started with an empty page on the right hand side. 
* Parts also appear in the table of content

Parts in the Booktype table of contents which start with '###' are not printed in the book.
These parts contain special information to structure the book (better).

## Chapters
```
<chapter label="ChapterTitleFromToC" id="chapterURL">
  <info>
    <title>Foreword</title>
  </info>
  ...
</chapter>
```

The `label` of the chapter is not identical with the title.
 * Chapter `label` is the string taken from the table of contents (which can differ). And should be listed there.
 * The title printed in the chapter inside the `title` tag inside the `info` tag. 

## Sections (inside chapters) 

```
<chapter label="ChapterTitleFromToC" id="chapterURL">
  <info>
    <title>Foreword</title>
  </info>
  <section role="h1">
    <title>Heading</title>
    <para>...</para>
    ...
  </section>
  <section role="h2">
    <title>Subheading</title>
    <para>...</para>
    ...
  </section>
  <section role="h3">
    <title>Subsubheading</title>
    <para>...</para>
    ...
  </section>
  ...
</chapter>
<chapter label="ChapterTitleFromToC" id="chapterURL">
  ...
</chapter>
```

To improve widows and orphans, it is important to cluster a headline with the following content. 
The headline can than optionally move to the next page, if the line count at the bottom of the page
requires it.
 * The content inside the chapter is clustered using `section` tags.
 * The section title is in the `title` tag.
 * Each section keeps the original HTML information as a `role` (h1|h2|h3|h4|h5).
 * Each section ends before the next headline.
 * IMPORTANT: `section` tags are only added where headlines have the `chapter` tag as a root level (and not for elements inside e.g. tables)
 * The `role` attribute in the `section` is identical (and lowercase) of the following headline tag.

## Paragraph
```
<p class="body-first"> => <para role="body-first">
Rule: no indent of first line, no margin / padding at the bottom

<p class="body"> => <para role="body">
Rule: indent first line 1em

<p class="hanging"> => <para role="hanging">
Rule: indent paragraph 1em, indent first line -1em

<p class="quote"> => <blockquote><para>
Rule: to be done

<p class="noindent"> => <para role="noindent">
Rule: no indentation

<p class="caption_small center ..."> => <para>
Rule: ignore the classes, use the content in <para> tag.
```

## Links
External links:
```
FROM (Booktype):
<a href="https://booktype.pro">Visit Booktype</a>

TO (DocBook 5.1):
<link xlink:href="https://booktype.pro">Visit Booktype</link>
```

Internal links:
```
FROM (Booktype):
<a href="../chapterid/">See this other chapter</a>

TO (DocBook 5.1):
<link linkend='chapterid'>See this other chapter</link>
```
## Image
```
FROM (Booktype)
<div class="group_img">
  <div class="image"><img src="../Images/idea-fig-one.png" alt=""/></div>
  <p class="caption_small center">This is the first image in the text.</p>
</div>

TO (DocBook 5.1)
<figure>
<title>The title - also for the table of figures</title>
<mediaobject>
  <imageobject condition="print">
    <imagedata fileref="figs/print/db5d_ref01.pdf"/>
  </imageobject>
  <textobject><phrase>ALT text here (caption?)</phrase></textobject>
  <caption>
    <para>If given, comes beneath the image / figure and beneath or following the title</para>
  </caption>
</mediaobject>
</figure>

MVP
<figure>
<mediaobject>
  <imageobject condition="print">
    <imagedata fileref="figs/print/db5d_ref10.pdf" format="PDF" role="keep-together"/>
  </imageobject>
</mediaobject>
</figure>
```
(see: http://docbook.org/tdg51/en/html/informalfigure.html)

### Rules:

Definitions of variables used:
* {figure object} means image and caption and potentially other elements.
* {figure space needed} means image size (plus caption, etc.) after calculating width and height.
* {figure position} means the place where the image is inside the text body.
* {page printarea} the available dimensions for text on a page (without margins, header, footer).

Rules in plain English:
* IF {figure object} is wider or higher than {page printarea}:
  * Calculate {figure width} and {figure height} to fit inside {page printarea}, keeping proportions. 
* Try to place {figure object} at {figure position}.
* IF {figure height} is larger than the space left on the page:
  * IF text from beneath {figure position} is long enough to fill the empty space on current page:
    * Fill empty space on current page with text
      * NOTE: Do rules for widows and orphans - as if there is not image - to decide number of lines for current page.
    * Move image to top of next page
  * ELSE (not enough text follows image to fill empty space):
    * IF chapter is finished (no more text or other elements):
      * Leave page empty
      * Move image to top of next page
    * ELSE (no text, but other element follows - like image or table):
      * Do this rule set recursively

## Table
* The table always contains thead, tfoot and tbody
* They can have zero or more elements (each of them)

```
<table>
  <caption>A table using thead and tbody correctly, no th just td</caption>
  <thead>
    <tr>
      <td>Head 1</td>
      <td>Head 2</td>
      <td>Head 3</td>
      <td>Head 4</td>
      <td>Head 5</td>
      <td>Head 6</td>
    </tr>
  </thead>
  <tfoot>
  </tfoot>
  <tbody>
    <tr>
      <td>a</td>
      <td>b</td>
      <td>c</td>
      <td>d</td>
      <td>e</td>
      <td>f</td>
    </tr>
  </tbody>
</table>
```
(see: http://docbook.org/tdg51/en/html/html.table.html)
### Rules:
 * See rules for images (figure element)

## Lists
```
FROM (Booktype):
<ul>
  <li>First item</li>
  <li>Second item with a soft line<br/>
  break in the middle of the line.</li>
  <li>Third item.</li>
</ul>

TO (DocBook 5.1)
<itemizedlist>
  <listitem>
    <para>TeX and LaTeX</para>
  </listitem>
  <listitem>
    <para>Troff
    </para>
  </listitem>
  <listitem>
    <para>Lout
    </para>
  </listitem>
</itemizedlist>

FROM (Booktype):
<ol>
  <li>First item</li>
  <li>Second item with a soft line <br/>
  break in the middle of the line.</li>
  <li>Third item.</li>
</ol>

TO (DocBook 5.1)
<orderedlist>
  <listitem>
    <para>One</para>
  </listitem>
  <listitem>
    <para>Two</para>
  </listitem>
  <listitem>
    <para>Three</para>
  </listitem>
  <listitem>
    <para>Four</para>
  </listitem>
</orderedlist>
```
(see: http://docbook.org/tdg51/en/html/itemizedlist.html)
(see: http://docbook.org/tdg51/en/html/orderedlist.html)

## Indentation
```
FROM:
<p>The following paragraph is indented
once:</p>
<p style="margin-left: 48px;">This is the
indented paragraph. The next paragraph is indented even more, i.e.
twice:</p>
<p style="margin-left: 96px;">This is the double-indented
paragraph. </p>
<p>And back to no indentation at all.</p>

TO:
- to be done
```

## Font styling
```
FROM (Booktype):
<p>And we have <i>italicised text with
<b>bold</b> and <u>underlined</u> in it</i>.</p>
<p>And <b>bold text with <i>italicised</i>
and <u>underlined</u> in it</b>.</p>
<p>And <u>underlined text with <b>bold</b>
and <i>italicised</i> and <b><i>bolditalicised</i></b> in
it</u>.</p>

TO (DocBook 5.1):
<b> => <emphasis role="bold">Bold</emphasis>
<i> => <emphasis role="italics">Italic</emphasis>
<u> => <emphasis role="underline">Underline</emphasis>
```

## Info box
(This is a special case of a multi-column box: single column)
```
FROM (Booktype):
<div class="bk-columns" data-column="1" data-valign="" data-gap="0">
<h2>This is an info box</h2>
<p style="">LoremBox28 It has roots in a piece of classical Latin
literature from 45 BC, making it over 2000 years old. Richard
McClintock, a Latin professor at Hampden-Sydney College in
Virginia, looked up one of the more obscure Latin words,
consectetur, from a Lorem Ipsum passage, and going through the
cites of the word in classical literature, discovered the
undoubtable source. Lorem Ipsum comes from sections 1.10.32 and
1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good
and Evil) by Cicero, written in 45 BC. This book is a treatise on
the theory of ethics, very popular during the Renaissance. The
first line of Lorem Ipsum, " dolor sit amet..", comes from a line
in section 1.10.32.</p>
<hr/>
<p><i>Source: the source of this
information is added here.</i></p>
</div>

TO (DocBook 5.1):
<formalpara>
  <title>The title, also used in the table of boxes</title>
  <para>This is a test.  This is only a test.  Had this been a real
    example, it would have made more sense.  Or less.
  </para>
  <para>...</para>
</formalpara>
```
## Endnotes (end of chapter notes)

```
FROM (Booktype):
...

TO (DocBook 5.1):
<para>An annual percentage rate (<abbrev>APR</abbrev>) of 13.9%<footnote>
<para>The prime rate, as published in the <citetitle>Wall Street
Journal</citetitle> on the first business day of the month,
plus 7.0%.
</para>
</footnote>
will be charged on all balances carried forward.
</para>
```
(see: http://docbook.org/tdg51/en/html/footnote.html)

Footnotes from DocBook can be all at the end of the book or end of chapter notes.
The renderer needs to make that decision.

We want footnotes to be end of chapter notes.
Counting starts at 1 with each new chapter.

## Other elements

### Horizontal lines
```
<hr>
```


