```
SELECT animal_type, count(*) 
from animal_ins 
group by animal_type
having animal_type = 'Dog'
or     animal_type = 'Cat' 
order by animal_type;
```
