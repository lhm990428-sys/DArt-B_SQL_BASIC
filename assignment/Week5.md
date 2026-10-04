# 📘 SQL_BASIC 5주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 날짜/시간 데이터와 조건문을 학습합니다. 특히 `CASE WHEN`은 SQL 문제 풀이와 데이터 분석에서 자주 사용되므로, 직접 분류 기준을 만들고 결과를 확인하는 연습을 해주세요.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_5th_TIL

### 섹션 5. 데이터 탐색 - 변환

### 4-4. 날짜 및 시간 데이터 이해하기

### 4-6. 조건문(CASE WHEN, IF)

---

## ✨ 선택 강의

- 4-5. 시간 데이터 연습문제: 날짜/시간 함수를 더 연습하고 싶을 때 선택 수강
- 4-7. 조건문 연습문제: CASE WHEN과 IF를 더 연습하고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | ✅ |
| 4주차 | 3-2 ~ 4-3 | 3-4 | ✅ |
| 5주차 | 4-4 ~ 4-6 | 4-5, 4-7 | ✅ |
| 6주차 | 5-2 ~ 5-5 | 5-6 | 🍽️ |
| 7주차 | 필수 강의 없음 | 6-2, 6-3, 6-4, 6-5 | 🍽️ |

---

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념 정리

아래 키워드 중 중요하다고 생각한 개념을 2개 이상 골라 짧게 정리해주세요. 3개보다 더 많이 정리하고 싶다면 자유롭게 항목을 추가해도 좋습니다.

이번 주 키워드:
- DATE
- DATETIME
- TIMESTAMP
- EXTRACT
- DATETIME_TRUNC
- FORMAT_DATETIME
- CASE WHEN
- IF

## 01.

```
개념 이름: 날짜 및 시간 데이터
개념 설명:
- DATE: 날짜만 저장하는 데이터 타입으로 연도, 월, 일을 표현한다.
- DATETIME: 날짜와 시간을 함께 저장하는 데이터 타입이다.
- TIMESTAMP: 특정 시점을 나타내는 데이터 타입으로, 시간대(Time Zone)를 고려할 수 있다.
- EXTRACT: 날짜 및 시간 데이터에서 연도, 월, 일, 시간 등 원하는 부분만 추출할 때 사용한다.
- DATETIME_TRUNC: 날짜·시간 값을 특정 단위(연도, 월, 일, 시간 등)를 기준으로 잘라서 표현한다.
- FORMAT_DATETIME: DATETIME 값을 원하는 문자열 형식으로 변환할 때 사용한다.

예시 쿼리:
SELECT
  CURRENT_TIMESTAMP() AS timestamp_col,
  DATETIME(CURRENT_TIMESTAMP(), 'Asia/Seoul') AS datetime_col;

SELECT 
  EXTRACT(DATE FROM DATETIME "2024-01-02 14:00:00") AS date,
  EXTRACT(YEAR FROM DATETIME "2024-01-02 14:00:00") AS year,
  EXTRACT(MONTH FROM DATETIME "2024-01-02 14:00:00") AS month,
  EXTRACT(DAY FROM DATETIME "2024-01-02 14:00:00") AS day,
  EXTRACT(HOUR FROM DATETIME "2024-01-02 14:00:00") AS hour,
  EXTRACT(MINUTE FROM DATETIME "2024-01-02 14:00:00") AS minute
```

## 02.

```
개념 이름: 조건
개념 설명:
- CASE WHEN: 여러 조건에 따라 서로 다른 값을 반환할 때 사용하는 조건문이다. 조건이 여러 개이거나 복잡한 경우에 유용하다.
- IF: 하나의 조건이 참인지 거짓인지에 따라 두 가지 결과 중 하나를 반환할 때 사용한다.
- CASE WHEN은 여러 조건을 순서대로 판단할 수 있고, IF는 비교적 단순한 조건을 처리할 때 편리하다.
예시 쿼리:
SELECT
  *,
  IF(speed >= 70, '빠름', '느림') AS Speed_Category
FROM basic.pokemon;

SELECT
  id,
  name,
  badge_count,
  CASE
    WHEN badge_count >= 9 THEN 'Advanced'
    WHEN badge_count BETWEEN 6 AND 8 THEN 'Intermediate'
    ELSE 'Beginner'
  END AS trainer_level
FROM basic.trainer;
```

---

# 2️⃣ 수행 인증란

아래 중 하나 이상을 첨부해주세요.

- 강의 수강 화면 캡처
- 문제 풀이 정답 화면 캡처
- SQL 실행 결과 화면 캡처
<img width="1917" height="983" alt="image" src="https://github.com/user-attachments/assets/36202b5b-db97-406e-9ccf-ae7dd1934631" />

---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [자동차 대여 기록에서 장기/단기 대여 구분하기](https://school.programmers.co.kr/learn/courses/30/lessons/151138)

풀이 과정:

```
- 장기/단기 대여를 나눈 기준: 대여 기간이 30일 이상이면 '장기 대여', 30일 미만이면 '단기 대여'
- 사용한 날짜 계산 방식: DATEDIFF(END_DATE, START_DATE) + 1로 실제 대여 일수를 계산
- CASE WHEN으로 만든 컬럼: RENT_TYPE
```

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/8e5ec46e-c98a-4abc-90cb-5aae9aa68e6a" />


## 🧩 문제 2

문제 링크: [한 해에 잡은 물고기 수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/298516)

풀이 과정:

```
- 문제에서 요구한 연도: 2021년
- 사용한 날짜 조건: YEAR(TIME) = 2021
- 집계한 대상: 2021년에 잡힌 물고기 전체 행의 개수
```

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/58500ced-168a-430a-8a37-f85c2ce18389" />


## 🧩 문제 3

문제 링크: [조건에 부합하는 중고거래 상태 조회하기](https://school.programmers.co.kr/learn/courses/30/lessons/164672)

풀이 과정:

```
- 날짜 조건:CREATED_DATE = '2022-10-05'
- CASE WHEN으로 바꾼 값:SALE → 판매중, RESERVED → 예약중, DONE → 거래완료
- ELSE에 해당하는 경우:문제에서 주어진 STATUS 값이 SALE, RESERVED, DONE뿐이므로 별도의 ELSE를 사용하지 않음
- 정렬 기준:BOARD_ID 기준 내림차순 정렬
```

<img width="1917" height="1195" alt="image" src="https://github.com/user-attachments/assets/3d71f05e-41e6-448f-9321-ef564074e089" />


## 🧩 문제 4

문제 링크: [자동차 평균 대여 기간 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/157342)

풀이 과정:

```
- GROUP BY 기준:CAR_ID
- 평균을 계산한 방식: DATEDIFF(END_DATE, START_DATE) + 1로 각 대여 기간을 구한 뒤 AVG로 평균 계산
- HAVING에 사용한 조건:평균 대여 기간이 7일 이상인 자동차만 조회
- 처음 헷갈렸던 점:대여 기간 계산 시 시작일과 종료일을 모두 포함해야 해서 DATEDIFF 결과에 +1을 해야 한다는 점
```

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/df260f93-e11f-4213-bdf4-7d66748aec89" />


---

# 4️⃣ 이번 주 회고

```
1. 날짜 함수 중 가장 헷갈린 함수: DATEDIFF로 날짜 차이를 계산할 때 시작일과 종료일을 모두 포함하려면 +1을 해야 한다는 점
2. CASE WHEN을 사용할 때 기억해야 할 문법: CASE로 시작해서 WHEN 조건 THEN 결과를 작성하고, 필요하면 ELSE를 사용한 뒤 END로 마무리해야 함
3. 날짜/시간 데이터나 조건문을 활용해보고 싶은 분석 상황: 월별 이용자 수나 주문 건수를 비교하고, 이용 기간이나 금액에 따라 고객을 여러 그룹으로 나누는 분석
```

수고하셨습니다!
