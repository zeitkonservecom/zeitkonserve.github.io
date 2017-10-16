---
title: curl output in terminal/console always empty
---

reason:

```
> file output.txt
ASCI text, with CR line terminators
```

solution:

convert with `... | mac2unix`
