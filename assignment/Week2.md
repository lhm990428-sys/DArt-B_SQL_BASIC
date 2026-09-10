# 📘 SQL_BASIC 2주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 저장된 데이터를 확인하는 방법과 `SELECT`, `FROM`, `WHERE`의 기본 구조를 학습합니다.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_2nd_TIL

### 섹션 3. 데이터 탐색 - 조건, 추출, 요약

### 2-2. 저장된 데이터 확인하기(데이터베이스, 데이터 웨어하우스, ERD)

### 2-3. 데이터 탐색(SELECT, FROM, WHERE)

---

## ✨ 선택 강의

- 2-4. SELECT 연습 문제: SELECT, FROM, WHERE를 더 연습하고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | 🍽️ |
| 4주차 | 3-2 ~ 4-3 | 3-4 | 🍽️ |
| 5주차 | 4-4 ~ 4-6 | 4-5, 4-7 | 🍽️ |
| 6주차 | 5-2 ~ 5-5 | 5-6 | 🍽️ |
| 7주차 | 필수 강의 없음 | 6-2, 6-3, 6-4, 6-5 | 🍽️ |

---

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념 정리

아래 키워드 중 중요하다고 생각한 개념을 2개 이상 골라 짧게 정리해주세요. 3개보다 더 많이 정리하고 싶다면 자유롭게 항목을 추가해도 좋습니다.

이번 주 키워드:
- SELECT
- FROM
- WHERE
- 조건식
- ORDER BY
- LIMIT
- 테이블 구조 확인

## 01.

```
개념 이름: SELECT
개념 설명: 테이블의 어떤 컬럼을 선택(출력)할 것인가? , 여러 컬럼 명시 가능
예시 쿼리: SELECT * (모든 컬럼을 출력하겠다)
           SELECT * EXCEPT (제외할 컬럼)
           SELECT 
             id as pokemon_id, (as는 별칭을 지어줄 때 사용한다)
             kor_name,
             type1,
             total

```

## 02.

```
개념 이름: FROM
개념 설명: 어떤 테이블에서 데이터를 확인할 것인가? 너무 길다면 as를 사용하여 별칭 지정 가능
예시 쿼리: FROM basic.pokemon
           FROM table1 as t1
```


---

# 2️⃣ 수행 인증란

아래 중 하나 이상을 첨부해주세요.

- 강의 수강 화면 캡처
<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/55e5dc72-ad18-4097-9bbb-a7ec4e7e225d" />

- 문제 풀이 정답 화면 캡처
<img width="1917" height="1196" alt="image" src="https://github.com/user-attachments/assets/46775e5c-e346-4a82-b92c-ce95c8fffdf5" />
<img width="1917" height="1197" alt="image" src="https://github.com/user-attachments/assets/30ad7109-1327-4771-868d-b74166b927df" />
<img width="1917" height="1188" alt="image" src="https://github.com/user-attachments/assets/de9215bc-d020-4735-927a-95fabe56a9d5" />
<img width="1917" height="1191" alt="image" src="https://github.com/user-attachments/assets/b5ac66af-25ca-478a-a506-7ace0eee6ad9" />
<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/91163814-4e39-4b7a-8948-5deb7bdcfb46" />



- SQL 실행 결과 화면 캡처
<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/1ed20359-8600-4c7b-8dc3-1f3c85758061" />

---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [모든 레코드 조회하기](https://school.programmers.co.kr/learn/courses/30/lessons/59034)

풀이 과정:

```
- 테이블에서 확인한 컬럼: ANIMAL_ID, ANIMAL_TYPE, DATETIME, INTAKE_CONDITION, NAME, SEX_UPON_INTAKE
- SELECT와 FROM을 작성한 방식: SELECT * FROM ANIMAL_INS
- 새로 배운 점 : ANIMAL_INS 이란 TABLE 에서 모든 정보를 추출하는 방법
```

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/1d0c886c-a098-4112-b969-b7441e043c1e" />


## 🧩 문제 2

문제 링크: [아픈 동물 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/59036)

풀이 과정:

```
- 문제에서 요구한 조건: 동물 보호소에 들어온 동물 중 아픈 동물의 아이디와 이름을 조회하는 SQL 문법을 요구함.
- WHERE 절로 옮긴 방식: INTAKE_CONDITION = 'Sick' 조건절을 사용하여 상태가 'Sick'인 행만 필터링함.
- 정렬 기준이 있다면 사용한 기준: 정렬 기준을 따로 두고 사용하지 않았음.
- 새로 배운 점: WHERE 절을 활용한 특정 문자열 조건 필터링 및 SELECT 절을 통한 필요한 컬럼 추출 방법
```

<img width="1917" height="1196" alt="image" src="https://github.com/user-attachments/assets/1832b11a-1500-4890-a204-0ff37e8c50de" />


---

# 4️⃣ 이번 주 회고

```
1. SELECT, FROM, WHERE 중 가장 헷갈린 개념: SQL 문법의 적용 순서가 헷갈렸음.
2. 문제를 풀 때 가장 자주 확인하게 된 부분: 여러 컬럼을 추출할 때 ','를 기재하였는지, 그리고 WHERE 절에서 문자열 추출할 때 ""를 잘 기재하였는지
3. 다음 주 문제 풀이에서 의식하고 싶은 습관: SQL문법의 적용 순서에 따라 자연스럽게 쿼리문 작성하기
```

수고하셨습니다!
