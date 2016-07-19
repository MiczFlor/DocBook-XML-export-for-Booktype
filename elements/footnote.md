## Footnotes / endnotes

(see: http://docbook.org/tdg51/en/html/footnote.html)

Booktype does end of chapter notes (listed at the end of each chapter, 
starting with counter 1 for each chapter).

DocBook only provides the `footnote` element, so we use the 
`role` attribute to define 'end of chapter' with `endofchapter`.

```
FROM (Booktype):
...

TO (DocBook 5.1):
<para>An annual percentage rate of 13.9%<footnote role="endofchapter">
<para>The prime rate, as published in the Wall Street
Journal on the first business day of the month,
plus 7.0%.
</para>
</footnote>
will be charged on all balances carried forward.
</para>
```