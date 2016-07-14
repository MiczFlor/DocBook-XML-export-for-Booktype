## Footnotes / endnotes

Footnotes from DocBook can be all at the end of the book or end of chapter notes.
The renderer needs to make that decision.

We want footnotes to be end of chapter notes.
Counting starts at 1 with each new chapter.

```
FROM (Booktype):
...

TO (DocBook 5.1):
<para>An annual percentage rate of 13.9%<footnote>
<para>The prime rate, as published in the Wall Street
Journal on the first business day of the month,
plus 7.0%.
</para>
</footnote>
will be charged on all balances carried forward.
</para>
```
(see: http://docbook.org/tdg51/en/html/footnote.html)