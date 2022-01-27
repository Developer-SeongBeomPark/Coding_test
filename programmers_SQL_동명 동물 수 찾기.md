```
SELECT name, count(*) count
from animal_ins 
group by name
having count(name) > 1
order by name;
```

* 문제에서 이름이 없는 동물은 집계에서 제외하라고 명시했기 때문에 Having문에서 count(*) > 1을 해도 결과는 같게 나오지만  '집계에서 제외'를 이행하지 않았으므로 틀린 것으로 나온다.
