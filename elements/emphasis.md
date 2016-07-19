## Font styling

The `emphasis` element is used to describe font styles like bold, underline, etc.
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