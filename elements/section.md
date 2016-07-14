## Sections (inside chapters) 

```
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
```

To improve widows and orphans, it is important to cluster a headline with the following content. 
The headline can than optionally move to the next page, if the line count at the bottom of the page
requires it.
 * The content inside the chapter is clustered using `section` tags.
 * The section title is in the `title` tag.
 * Each section keeps the original HTML information as a `role` (h1|h2|h3|h4|h5).
 * Each section ends before the next headline.
 * IMPORTANT: `section` tags are only added where headlines have the `chapter` tag as a root level (and not for elements inside e.g. tables)
 * The `role` attribute in the `section` is identical (and lowercase) of the following headline tag.