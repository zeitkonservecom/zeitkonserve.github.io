---
title: E-Mail batching workflow with mutt
---

1. Create temporary dir `mkdir /tmp/t`
2. On each email open mail text with `v` and save (press `s`) its text in folder `/tmp/t` - for example in the file `/tmp/t/01` (btw jumping to the beginning of the filename press `ctrl+a`
3. `cat /tmp/t/* > /tmp/all` to file print with `cat /tmp/t/* | lpr -p`
4. edit file `/tmp/all`, comment it, send it, love it
