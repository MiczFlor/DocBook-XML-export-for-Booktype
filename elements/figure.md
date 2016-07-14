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