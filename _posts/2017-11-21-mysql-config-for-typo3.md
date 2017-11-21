```
#1247602160: Expression #4 of SELECT list is not in GROUP BY clause and contains nonaggregated column 'typo3.d.uid' which is not functionally dependent on columns in GROUP BY clause; this is incompatible with sql_mode=only_full_group_by (More information)

soultion:

login (ssh) in mysql server and run in mysql cli:

SET GLOBAL sql_mode=(SELECT REPLACE(@@sql_mode,'ONLY_FULL_GROUP_BY',''));
```
