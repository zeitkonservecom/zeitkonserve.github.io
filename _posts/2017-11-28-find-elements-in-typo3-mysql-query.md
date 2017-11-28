```
mysql> select cnt.colpos, pgs.t3_origuid, pgs.t3ver_oid, pgs.uid, pgs.title, cnt.sys_language_uid, cnt.header,cnt.uid from pages pgs inner join tt_content cnt on cnt.pid = pgs.uid where cnt.ctype='multimedia' and (pgs.deleted = 0 and pgs.hidden=0) and (cnt.hidden=0 and cnt.deleted=0);

see also
* in backend under "not used elements" 
* the list module
* the column tx_templaviolaplus_flex (is the element used in templaviola?)
```
