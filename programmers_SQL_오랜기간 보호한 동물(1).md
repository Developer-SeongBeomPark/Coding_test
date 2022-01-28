```
SELECT *
from (
    SELECT a.name, a.datetime
    from animal_ins a, animal_outs b
    where a.animal_id = b.animal_id(+) and b.sex_upon_outcome is null
    order by a.datetime
    )
where rownum <= 3;
```
