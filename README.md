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

Here an example of a book content skeleton:
```
<book xmlns='http://docbook.org/ns/docbook'>
  <title>Booktype goes DocBook</title>
  <info>
    <legalnotice><para>GNU Open Documentation</para></legalnotice>
    <author xml:base="https://booktype.pro"><givenname>The Booktype Team</givenname></author>
    <publisher>
      <publishername>Sourcefabric Publishing</publishername>
      <city>Prague</city>
      <uri>https://sourcefabric.org</uri>
    </publisher>
  <dedication><para>This book is dedicated to you.</para></dedication>
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
</book>
```

# Features in Booktype and corresponding DocBook elements

## Book - the wrapper around everything

The `book` element of DocBook contains also the book metadata from Booktype

[Book element](elements/book.md)

## Parts

Book parts are called sections in Booktype. 
The `part` element is wrapped around all chapters inside the part. 

[Part element](elements/part.md)

## Chapters

A chapter is - well - a chapter in the book.
It will be listed in the table of contents.

[Chapter element](elements/chapter.md) 

## Sections (inside chapters) 

The sections are defined inside the Booktype editor as H1, H2, H3 and so forth.

[Section element](elements/section.md) 

## Paragraph

We are using the `para` element for normal paragraphs. 
Another paragraph element of DocBook (`formalpara`) is used for a special feature, the info box (see below).

Also, paragraph alignment is described in this document.

[Paragraph element](elements/para.md) 

## Links

Booktype supports external links as well as internal references. 
Both can be represented in DocBook's `link` element.

[Link element](elements/link.md) 

## Image

For images we are using the `figure` element in DocBook. 
This is wrapped around the `mediaobject` element.

[Figure (images) element](elements/figure.md) 

## Table

[Table element](elements/table.md) 

## Lists

The Booktype editor supports ordered and unordered lists. 
In DocBook, these are represented in `itemizedlist` (unordered)
and `orderedlist` (ordered).

[Unordered list element](elements/itemizedlist.md) 

[Ordered list element](elements/orderedlist.md) 

## Font styling

Font styling means bold, italics, underline.
All of these are wrapped into the `emphasis` element of DocBook.

[Font styling: emphasis element](elements/emphasis.md) 

## Info box

An infobox is a special feature in Booktype.
It is represented using the `formalpara` element.
Other uses of `formalpara` might come later,
which is what the `role` attribute is important.

[formalpara element](elements/formalpara.md) 

## Endnotes (end of chapter notes)

Booktype does end of chapter notes (listed at the end of each chapter, 
starting with counter 1 for each chapter).

DocBook only provides the `footnote` element, so we use the 
`role` attribute to define 'end of chapter'.

[footnote (used for end of chapter notes) element](elements/footnote.md) 

## Other elements to be done

### Paragrpah alignment
[Booktype paragraph alignment](booktype-features-todo/booktype-alignment.md) 

### Horizontal lines
[Booktype horizontal line](booktype-features-todo/booktype-horizontalrule.md) 

### Indentation
[Booktype indentation](booktype-features-todo/booktype-indentation.md) 
