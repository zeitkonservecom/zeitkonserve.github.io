---
title: Clean up backups, leave only ten left (bash, shell)
---

```
function cleanup() {
    f="$1"
    year=`date +%Y`
    ls -1 "$f" | grep "^$year-" | sort | tail -10 > /tmp/last10.txt
    ls -1 "$f" | grep "^$year-" | sort > /tmp/all.txt
    cd "$f" 
    rm -r -f `diff /tmp/last10.txt /tmp/all.txt | grep '^>' | grep "$year.*" -o`
}


cleanup "/backup/"
```
