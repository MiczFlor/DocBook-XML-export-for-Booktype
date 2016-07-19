## Part

(see: http://docbook.org/tdg51/en/html/part.html)

```
<part label="###Frontmatter" role="structure"> 
  <title>###Frontmatter</title> 
  ...
</part>
```

* The print title is in the `title` tag.
* The `label` tab also contains the title of the part.
* A book does not necessarily have parts as a structure.
* A part is started with an empty page on the right hand side. 
* Parts also appear in the table of content
* role can be set in which case it must be `role="structure"`

### Parts for structure or as content

Parts are also used in Booktype to structure books. For example into frontmatter, mainmatter
and backmatter.

Such parts (called sections in Booktype)
* must not be printed in the mainmatter
* must not be contained in the table of contents

In Booktype, the names of such parts (sections) start with `###`, like `###Frontmatter`.

In the DocBook export, such structuring parts are given `role="structure"`.
The renderer can then decide what action to match with the label content.