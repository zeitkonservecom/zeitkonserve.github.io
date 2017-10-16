---
title: curl output in terminal/console always empty
---

when `curl some-url.com` is always empty, but the `--trace-ascii /dev/stdout` switch shows all data, then there's somthing wrong with the encoding of the server repsonse.

```
> file output.txt
ASCI text, with CR line terminators
```

solution:

convert with `... | mac2unix`
