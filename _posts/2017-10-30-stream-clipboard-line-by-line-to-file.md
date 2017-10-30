---
title: stream clipboard line by line to file
---

```
clip=`xclip -o -selection c`
while true
do
if [ -z "$clip" ]
then
else
    echo $clip >> stream.csv
    echo "" | xclip -selection c
fi

sleep 1s
clip=`xclip -o -selection c`
echo "$clip";
done;

```
