```
SELECT to_char(datetime,'hh24') as hour, count(*) as count
from animal_outs
where to_char(datetime,'hh24') between 09 and 19
group by to_char(datetime,'hh24')
order by to_char(datetime,'hh24');
```

* 자료형이 DATE인 datetime을 시간만으로 표현해야 하므로 to_char(컬럼명,포맷)을 사용한다.
* 09시부터 19시 까지만 표현해야 하므로 where절의 between을 사용한다.
