## Section used for InfoBox

(see: http://docbook.org/tdg51/en/html/section.html)

### Info box using `section` with role ` 

IMPORTANT: The section MUST have the `role` element = `infobox`
 
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
<section role='infobox'>
  <title>Box141ToC Title also for table of boxes</title>
  <para>L142orem The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested. Sections 1.10.32 and 1.10.33 from "de Finibus Bonorum et Malorum" by Cicero are also reproduced in their exact original form, accompanied by English versions from the 1914 translation by H. Rackham.</para>
  <para>L143orem has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. </para>
  <para>L144orem The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested. Sections 1.10.32 and 1.10.33 from "de Finibus Bonorum et Malorum" by Cicero are also reproduced in their exact original form, accompanied by English versions from the 1914 translation by H. Rackham.</para>
</section>
```