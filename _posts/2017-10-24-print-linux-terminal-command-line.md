---
title: print text file from command line
---

lpr -p /tmp/file, works when default printer is configured in Ubuntu.

enscript /tmp/file, works when default printer is configured in Ubuntu.

Enscript does not support UTF-8. Converting is neccessary. For example to ISO 8859-1 (not yet tested):

```
iconv -f utf-8 -t iso-8859-1 /tmp/file
enscript -X 88591 /tmp/file
```
