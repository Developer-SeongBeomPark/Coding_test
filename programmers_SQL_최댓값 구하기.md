```
SELECT datetime from (select * from animal_ins order by datetime desc) where rownum = 1;
```

```
select max(datetime) from animal_ins;
```
