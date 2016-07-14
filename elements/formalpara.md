## Formal paragraphs

(see: http://docbook.org/tdg51/en/html/formalpara.html)

### Info box using `formalpara` 

Because `formalpara` might be used in other cases as well,
it is important to give this special use case the role `infobox`
as an attribute.
 
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
<formalpara role="infobox">
  <title>The title, also used in the table of boxes</title>
  <para>This is a test.  This is only a test.  Had this been a real
    example, it would have made more sense.  Or less.
  </para>
  <para>...</para>
</formalpara>
```