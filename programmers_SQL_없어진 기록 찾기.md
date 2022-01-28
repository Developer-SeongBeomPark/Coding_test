```
SELECT b.animal_id, b.name
from animal_ins a, animal_outs b
where a.animal_id(+) = b.animal_id and a.animal_id is null
order by animal_id;
```

* JOIN
 두 개 이상의 테이블을 비교할 때 사용한다.
 기준 테이블은 그대로 쓰고 대상 테이블에는 (+)를 붙여준다.
