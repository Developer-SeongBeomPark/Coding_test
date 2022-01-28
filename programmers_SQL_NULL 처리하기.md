```
SELECT animal_type, nvl(name,'No name') as name, sex_upon_intake
from animal_ins
order by animal_id;
```

* 데이터값이 null일 경우, 원하는 이름으로 값을 설정할 때 nvl(컬럼명,원하는 이름)을 사용한다.
