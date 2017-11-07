---
title: delete files older than 10 days in /tmp
---

`find /tmp -ctime +10 -exec rm -rf {} +`
