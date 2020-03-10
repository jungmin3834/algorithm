# algorithm 
Select

# 문제 링크  
https://programmers.co.kr/learn/courses/30/parts/17042

![title](https://github.com/jungmin3834/algorithm/blob/master/image/17042.png)
  
###  모든 레코드 조회하기  

```sql
SELECT * FROM ANIMAL_INS ORDER BY ANIMAL_ID asc
```

###  역순 정렬하기

```sql
SELECT NAME , DATETIME  FROM ANIMAL_INS ORDER BY ANIMAL_ID DESC;
```

###  아픈 동물 찾기 

```sql
SELECT ANIMAL_ID , NAME FROM ANIMAL_INS WHERE LOWER(INTAKE_CONDITION) = 'sick' ORDER BY ANIMAL_ID ASC
```

###  어린 동물 찾기
 
```sql
SELECT ANIMAL_ID , NAME FROM ANIMAL_INS WHERE INTAKE_CONDITION !='Aged' ORDER BY ANIMAL_ID ASC;
```

###  동물의 아이디와 이름

```sql
SELECT ANIMAL_ID, NAME FROM ANIMAL_INS ORDER BY ANIMAL_ID ASCC;
```

###  여러 기준으로 정렬하기

```sql
SELECT ANIMAL_ID , NAME , DATETIME FROM ANIMAL_INS ORDER BY NAME ASC , DATETIME DESC
```

###  상위 n개 레코드

```sql
SELECT NAME FROM ANIMAL_INS WHERE DATETIME=(SELECT MIN(DATETIME) FROM ANIMAL_INS);
```