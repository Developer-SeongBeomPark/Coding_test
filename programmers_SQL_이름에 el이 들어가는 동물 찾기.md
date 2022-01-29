```
SELECT animal_id, name
from animal_ins
where lower(name) like '%el%'
and animal_type = 'Dog'
order by name;
```

* 대소문자 구분 없이 검색하는 방법 : lower(name)
