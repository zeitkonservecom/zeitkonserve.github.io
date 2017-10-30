---
title: Prepare a typo3-instance for a translation process
---

1. Export content elemenents which needs to be translated:
  ```
  SELECT concat(concat(uid, '_'),pid), concat(concat('http://localhost/typo3/alt_doc.php?&edit[tt_content][',uid),']=edit'), concat('http://localhost/index.php?&L=1&id=',pid), header, bodytext FROM `tt_content` WHERE deleted=0 and hidden=0 order by pid asc, uid asc
  ```
2. Remove html-tags:
  ```
  sed 's#<br */*>##g;s#<[^>]*>##g' ~/tt_content.csv > ~/tt_content_edited.csv
  ```
3. Add pid and uid to all elements in your page:
  ```
  tt_content.stdWrap.dataWrap = <div><div style="position:relative;left:0px;top:0px; background-color:white">{field:uid}_{field:pid}	<a href="http://localhost/typo3/alt_doc.php?&edit[tt_content][{field:uid}]=edit">EDIT</a></div>|</div>
  ```
4. Open ~/tt_content_edited.csv in LibreOffice, go through the website and collect/check all content elements which needs to be translated. 


```
http://localhost/typo3/alt_doc.php?&edit[tt_content][51]=edit
```
