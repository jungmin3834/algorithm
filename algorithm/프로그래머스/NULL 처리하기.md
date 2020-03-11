# algorithm 
NULL 처리하기



# 문제 링크  
https://programmers.co.kr/learn/courses/30/lessons/59410

![title](https://github.com/jungmin3834/algorithm/blob/master/image/59410.png)
  

```sql
SELECT ANIMAL_TYPE, 
CASE 
    WHEN NAME IS NULL
    THEN 'No name'
    ELSE NAME
END 
, SEX_UPON_INTAKE 
FROM ANIMAL_INS 

```
