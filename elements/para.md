## Paragraph

(see: http://docbook.org/tdg51/en/html/para.html)

```
<p class="body-first"> => <para role="body-first">
Rule (depending on theme): no indent of first line, no margin / padding at the bottom

<p class="body"> => <para role="body">
Rule (depending on theme): indent first line 1em

<p class="hanging"> => <para role="hanging">
Rule: indent paragraph 1em, indent first line -1em

<p class="quote"> => <blockquote><para>
Rule: to be done

<p class="noindent"> => <para role="noindent">
Rule: no indentation

<p class="caption_small center ..."> => <para>
Rule: ignore the classes, use the content in <para> tag.
```