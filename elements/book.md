## Book - the wrapper around everything

Additional namespace `xmlns:xl='http://www.w3.org/1999/xlink'` needed to validate internal and external links.

```
<?xml version='1.0' encoding='UTF-8'?>

<book xmlns='http://docbook.org/ns/docbook' xmlns:xl='http://www.w3.org/1999/xlink' version='5.1'>
  <title>%title%</title>
  <titleabbrev>short-title</titleabbrev>
  <subtitle>%subtitle%</subtitle>
  <info>
    <legalnotice><para>%rights%</para></legalnotice>
    <author xml:base='%url_author%'>
      <personname>%author%</personname></author>
    <editor>
      <personname>%author%</personname>
    </editor>
    <publisher>
      <publishername>%publisher%</publishername>
      <address>
        <city>%publisher_city%</city>
        <uri>%url_publisher%</uri>
      </address>
    </publisher>
    <abstract><para>%short_description%</para></abstract>
    <copyright>
      <year>%dateCopyrighted%</year>
      <holder>%rights_holder%</holder>
    </copyright>
    <biblioid class='isbn'>%???%</biblioid>
    <edition>%as edition%</edition>
  
    <othercredit role='coverdesigner'>
      <personname>%cover_design%</personname>
    </othercredit>
    <othercredit role='translator'>
      <personname>%translation_by%</personname>
    </othercredit>
    <othercredit role='illustrator'>
      <personname>%illustration_by%</personname>
    </othercredit>
    <othercredit role='proofreader'>
      <personname>%proofreading%</personname>
    </othercredit>
    
    <othercredit role='photographer'>
      <personname>%photography%</personname>
    </othercredit>
    <othercredit role='cover_photography'>
      <personname>%cover_photography%</personname>
    </othercredit>
    <othercredit role='lectorate'>
      <personname>%lectorate%</personname>
    </othercredit>
    <othercredit role='rights_clearing'>
      <personname>%rights_clearing%</personname>
    </othercredit>
    <othercredit role='research'>
      <personname>%research%</personname>
    </othercredit>
    <othercredit role='text_by'>
      <personname>%text_by%</personname>
    </othercredit>
    <othercredit role='introduction_by'>
      <personname>%introduction_by%</personname>
    </othercredit>
    
    <bibliomisc role='ebook_isbn'>%ebook_isbn%</bibliomisc>
    <bibliomisc role='bibliographic_information'>%bibliographic_information%</bibliomisc>
    <bibliomisc role='typeface'>%typeface%</bibliomisc>
    <bibliomisc role='printed_on'>%printed_on%</bibliomisc>
    <bibliomisc role='bookbinder'>%bookbinder%</bibliomisc>
    <bibliomisc role='printer'>%printer%</bibliomisc>
    <bibliomisc role='printer_country'>%printer_country%</bibliomisc>
    <bibliomisc role='paper_certification'>%paper_certification%</bibliomisc>
  </info>
  <acknowledgements><para>...</para></acknowledgements>
  <dedication><para>This book is dedicated to you.</para></dedication>
  <part>...
    <chapter>...
  ...
</book>
```
(see: http://docbook.org/tdg51/en/html/book.html)


### Setting the language

(see: https://www.w3.org/International/articles/language-tags/)
(see: http://www.lingoes.net/en/translator/langcode.htm)