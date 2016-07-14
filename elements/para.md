## Paragraph

(see: http://docbook.org/tdg51/en/html/para.html)

### Booktype classes converted to paragraphs:

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

### Alignment of paragraphs

In Booktype you can set the alignment per paragraph. Therefore we must pass them on as an attribute in the `para` tag. 

Because there is no such attribute available, we use `remap`.

```
<para> => book / default align (or automatic in the case of a rtl document)

<para remap="text-align:left"> => align left

<para remap="text-align:right"> => align right

<para remap="text-align:center"> => center aligned

<para remap="text-align:justify"> => justify paragraph
```
 
