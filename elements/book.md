## Book - the wrapper around everything

```
<book xmlns='http://docbook.org/ns/docbook'>
  <title>%title%</title>
  <titleabbrev>short-title</titleabbrev>
  <subtitle>%subtitle%</subtitle>
  <info>
    <legalnotice><para>%rights%</para></legalnotice>
    <author xml:base="%url_author%"><givenname>%author%</givenname></author>
    <editor><givenname>%author%</givenname></editor>
    <publisher>
      <publishername>%publisher%</publishername>
      <city>%publisher_city%</city>
      <uri>%url_publisher%</uri>
    </publisher>
    <abstract><para>%short_description%</para></abstract>
    <copyright>
      <year>%dateCopyrighted%</year>
      <holder>%rights_holder%</holder>
    </copyright>
    <biblioid>
      <isbn>%???%</isbn>
    </biblioid>
    <edition>%as edition%</edition>
  
    <othercredit class="coverdesigner">
      <personname><givenname>%cover_design%</givenname></personname>
    </othercredit>
    <othercredit class="translator">
      <personname><givenname>%translation_by%</givenname></personname>
    </othercredit>
    <othercredit class="illustrator">
      <personname><givenname>%illustration_by%</givenname></personname>
    </othercredit>
    <othercredit class="proofreader">
      <personname><givenname>%proofreading%</givenname></personname>
    </othercredit>
    
    <othercredit otherclass="photographer">
      <personname><givenname>%photography%</givenname></personname>
    </othercredit>
    <othercredit otherclass="cover_photography">
      <personname><givenname>%cover_photography%</givenname></personname>
    </othercredit>
    <othercredit otherclass="lectorate">
      <personname><givenname>%lectorate%</givenname></personname>
    </othercredit>
    <othercredit otherclass="rights_clearing">
      <personname><givenname>%rights_clearing%</givenname></personname>
    </othercredit>
    <othercredit otherclass="research">
      <personname><givenname>%research%</givenname></personname>
    </othercredit>
    <othercredit otherclass="text_by">
      <personname><givenname>%text_by%</givenname></personname>
    </othercredit>
    <othercredit otherclass="introduction_by">
      <personname><givenname>%introduction_by%</givenname></personname>
    </othercredit>
    
    <bibliomisc role="ebook_isbn">%ebook_isbn%</bibliomisc>
    <bibliomisc role="bibliographic_information">%bibliographic_information%</bibliomisc>
    <bibliomisc role="typeface">%typeface%</bibliomisc>
    <bibliomisc role="printed_on">%printed_on%</bibliomisc>
    <bibliomisc role="bookbinder">%bookbinder%</bibliomisc>
    <bibliomisc role="printer">%printer%</bibliomisc>
    <bibliomisc role="printer_country">%printer_country%</bibliomisc>
    <bibliomisc role="paper_certification">%paper_certification%</bibliomisc>
  </info>
  <acknowledgements><para>...</para></acknowledgements>
  <dedication><para>This book is dedicated to you.</para></dedication>
  <part>...
    <chapter>...
  ...
</book>
```
(see: http://docbook.org/tdg51/en/html/book.html)