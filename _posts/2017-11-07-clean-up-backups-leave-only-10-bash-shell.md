---
title: Clean up backups, leave only ten left (bash, shell)
---

```
function cleanup() {
    f="$1"
    ls -1 "$f" | grep '^20' | sort | tail -10 > /tmp/last10.txt
    ls -1 "$f" | grep '^20' | sort > /tmp/all.txt
    cd "$f" rm -r -f `diff /tmp/last10.txt /tmp/all.txt | grep '^>' | grep '20.*' -o`
}

cleanup "/backup/"
```
