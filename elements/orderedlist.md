## Lists (ordered = numbering)
```
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
(see: http://docbook.org/tdg51/en/html/orderedlist.html)