# 📘 SQL_BASIC 6주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 SQL 입문 과정의 핵심 고비인 `JOIN`을 학습합니다.

JOIN은 여러 테이블을 연결해서 분석 질문에 답하기 위해 반드시 필요한 개념입니다. 이번 주 과제에서는 정답 코드뿐 아니라 **어떤 테이블을 어떤 키로 연결했는지**를 꼭 기록해주세요.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_6th_TIL

### 섹션 6. 다량의 자료를 연결 : JOIN

### 5-2. JOIN 이해하기

### 5-3. 다양한 JOIN 방법

### 5-4. JOIN 쿼리 작성하기

### 5-5. JOIN을 처음 공부할 때 헷갈리는 부분

---

## ✨ 선택 강의

- 5-6. JOIN 연습문제: JOIN 문제를 더 연습하고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | ✅ |
| 4주차 | 3-2 ~ 4-3 | 3-4 | ✅ |
| 5주차 | 4-4 ~ 4-6 | 4-5, 4-7 | ✅ |
| 6주차 | 5-2 ~ 5-5 | 5-6 | ✅ |
| 7주차 | 필수 강의 없음 | 6-2, 6-3, 6-4, 6-5 | 🍽️ |

---

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념 정리

아래 키워드 중 중요하다고 생각한 개념을 2개 이상 골라 짧게 정리해주세요. 3개보다 더 많이 정리하고 싶다면 자유롭게 항목을 추가해도 좋습니다.

이번 주 키워드:
- JOIN
- INNER JOIN
- LEFT JOIN
- JOIN key
- alias
- NULL
- 다중 JOIN

## 01.

```
개념 이름: JOIN
개념 설명: 두 개 이상의 테이블을 공통된 컬럼(Key)을 기준으로 연결하여 데이터를 결합하는 기능이다.
JOIN 종류에 따라 결합되는 데이터의 범위와 결과가 달라진다.
예시 쿼리:
SELECT
    A.col1,
    A.col2,
    B.col11,
    B.col12
FROM table1 AS A
LEFT JOIN table2 AS B
ON A.key = B.key;
```

## 02.

```
개념 이름: LEFT JOIN
개념 설명: 왼쪽 테이블의 모든 데이터를 유지하면서 오른쪽 테이블에서 JOIN 조건에 일치하는 데이터를 결합한다.
오른쪽 테이블에 일치하는 데이터가 없으면 해당 컬럼은 NULL로 표시된다.
예시 쿼리:
SELECT
    tp.id,
    tp.trainer_id,
    tp.pokemon_id, 
    t.age,
    t.hometown
FROM basic.trainer_pokemon AS tp
LEFT JOIN basic.trainer AS t
ON tp.trainer_id = t.id
# ON : Join KEY를 기입
```


---

# 2️⃣ 수행 인증란

아래 중 하나 이상을 첨부해주세요.

- 강의 수강 화면 캡처
- JOIN 문제 풀이 정답 화면 캡처
- JOIN 전후 결과 row 수를 비교한 캡처 또는 메모
<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/012e2988-b5b1-4932-b680-f7beb284411a" />

---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [조건에 맞는 도서와 저자 리스트 출력하기](https://school.programmers.co.kr/learn/courses/30/lessons/144854)

풀이 과정:

```
- 사용한 테이블:BOOK, AUTHOR
- JOIN key: BOOK.AUTHOR_ID = AUTHOR.AUTHOR_ID
- 날짜를 출력한 형식: YYYY-MM-DD (DATE_FORMAT 함수 사용)

```

<img width="1917" height="1153" alt="image" src="https://github.com/user-attachments/assets/dbeea4b7-1cf5-4ffe-b950-c04b57b37407" />


## 🧩 문제 2

문제 링크: [상품 별 오프라인 매출 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/131533)

풀이 과정:

```
- 연결한 테이블: PRODUCT, OFFLINE_SALE
- JOIN key: PRODUCT.PRODUCT_ID = OFFLINE_SALE.PRODUCT_ID
- 집계한 값: 상품코드별 매출액 합계 (PRICE * SALES_AMOUNT)
```

<img width="1917" height="1196" alt="image" src="https://github.com/user-attachments/assets/c689cf14-7389-4b45-a810-8552f2465ca8" />


## 🧩 문제 3

문제 링크: [없어진 기록 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/59042)

풀이 과정:

```
- 기준이 되는 왼쪽 테이블: ANIMAL_OUTS
- LEFT JOIN이 필요한 이유: 입양 기록은 있지만 보호소에 들어온 기록이 없는 동물을 찾기 위해 사용한다.
- NULL이 발생하는 경우: ANIMAL_OUTS의 ANIMAL_ID와 일치하는 값이 ANIMAL_INS에 존재하지 않는 경우이다.

```

<img width="1917" height="1197" alt="image" src="https://github.com/user-attachments/assets/bff3ed25-891c-40a9-9385-a49b037943bb" />


## 🧩 문제 4

문제 링크: [있었는데요 없었습니다](https://school.programmers.co.kr/learn/courses/30/lessons/59043)

풀이 과정:

```
- 사용한 테이블: ANIMAL_INS, ANIMAL_OUTS
- JOIN key: ANIMAL_INS.ANIMAL_ID = ANIMAL_OUTS.ANIMAL_ID
- 비교한 날짜 컬럼: ANIMAL_INS.DATETIME(보호 시작일), ANIMAL_OUTS.DATETIME(입양일)
- 정렬 기준: 보호 시작일(ANIMAL_INS.DATETIME) 오름차순
```

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/98f3e9e9-1189-48ea-a632-eed7305d5bd2" />


---

# 4️⃣ 참고 자료

JOIN 개념이 헷갈린다면 아래 자료를 함께 참고해도 좋습니다.

1. https://data-marketing-bk.tistory.com/entry/SQL-JOIN-%ED%95%9C-%EB%B0%A9%EC%97%90-%EC%A0%95%EB%A6%AC-%EA%B0%9C%EB%85%90%EB%B6%80%ED%84%B0-%EC%BD%94%EB%93%9C%EA%B9%8C%EC%A7%80-%EC%9D%B4%EA%B2%83%EB%A7%8C-%EB%B3%B4%EC%9E%90
2. https://velog.io/@wijoonwu/JOIN

---

# 5️⃣ 이번 주 회고

```
1. INNER JOIN과 LEFT JOIN의 차이를 어떻게 이해했는지:
INNER JOIN은 두 테이블에서 JOIN 조건에 일치하는 데이터만 반환하고, LEFT JOIN은 왼쪽 테이블의 모든 데이터를 유지한다.따라서 일치하는 데이터만 필요한지, 일치하지 않는 데이터까지 확인해야 하는지에 따라 선택해야 한다.
2. JOIN 문제를 풀 때 가장 먼저 확인해야 할 것:
연결할 테이블과 공통된 JOIN KEY가 무엇인지 먼저 확인해야 한다.
이후 문제에서 요구하는 데이터의 범위를 파악하여 적절한 JOIN 방식을 선택해야 한다.
3. JOIN 결과가 예상과 달랐던 경험이 있다면:
LEFT JOIN 이후 WHERE절에서 NULL 조건을 활용하면 연결되지 않은 데이터만 추출할 수 있다는 점이 헷갈렸다.
JOIN 자체는 데이터를 결합하는 역할이고, WHERE절은 결합된 결과를 필터링한다는 점을 이해했다.
```

수고하셨습니다!
