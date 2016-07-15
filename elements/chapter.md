## Chapters
```
<chapter label="ChapterTitleFromToC" id="chapterURL">
  <info>
    <title>Foreword</title>    
    <author><givenname>Arthur van Book</givenname></author>
  </info>
  ...
</chapter>
```

The `label` of the chapter is not identical with the title.
* Chapter `label` is the string taken from the table of contents (which can differ). And should be listed there.
* The title printed in the chapter inside the `title` tag inside the `info` tag.
* The `author` field in `info` is optional.
  * If the `author` field is given, the full name is wrapped inside `givenname`