# 📘 SQL_BASIC 4주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 SQL 쿼리를 작성하는 흐름, 쿼리 작성 템플릿, 데이터 타입 변환, 문자열 함수를 학습합니다.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_4th_TIL

### 섹션 4. SQL 쿼리 잘 작성하기, 쿼리 작성 템플릿 및 오류를 잘 디버깅하기

### 3-2. SQL 쿼리를 작성하는 흐름

### 3-3. 쿼리 작성 템플릿과 생산성 도구

### 섹션 5. 데이터 탐색 - 변환

### 4-1. INTRO

### 4-2. 데이터 타입과 데이터 변환(CAST, SAFE_CAST)

### 4-3. 문자열 함수(CONCAT, SPLIT, REPLACE, TRIM, UPPER)

---

## ✨ 선택 강의

- 3-4. 오류를 디버깅하는 방법: 오류 메시지 해석과 디버깅 흐름을 더 익히고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | ✅ |
| 4주차 | 3-2 ~ 4-3 | 3-4 | ✅ |
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
- 쿼리 작성 순서
- 쿼리 작성 템플릿
- 데이터 타입
- CAST
- SAFE_CAST
- CONCAT
- REPLACE
- TRIM

## 01.

```
개념 이름: CAST / SAFE_CAST
개념 설명: 데이터의 타입을 다른 타입으로 변환하는 함수이다.
CAST는 변환 실패 시 오류가 발생하고, SAFE_CAST는 NULL을 반환한다.
예시 쿼리:SELECT SAFE_CAST('123' AS INT64);
```

## 02.

```
개념 이름:CONCAT
개념 설명:여러 문자열을 하나의 문자열로 이어 붙이는 함수이다.
예시 쿼리:SELECT CONCAT('Hello', ' ', 'SQL');
```


---

# 2️⃣ 수행 인증란

아래 중 하나 이상을 첨부해주세요.

- 강의 수강 화면 캡처
<img width="1840" height="1198" alt="image" src="https://github.com/user-attachments/assets/b2a1a81f-d431-4c41-805d-0a81094396b1" />


---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [특정 옵션이 포함된 자동차 리스트 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/157343)

풀이 과정:

```
- 찾으려는 문자열 조건: OPTIONS에 '네비게이션'이 포함된 자동차
- 사용한 문자열 조건 문법: LIKE '%네비게이션%'
- 정렬 기준: CAR_ID 기준 내림차순 정렬 (DESC)
```

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/ad3eb96c-62cd-49c3-ae31-4a4898b9a091" />


## 🧩 문제 2

문제 링크: [강원도에 위치한 생산공장 목록 출력하기](https://school.programmers.co.kr/learn/courses/30/lessons/131112)

풀이 과정:

```
- 문제에서 요구한 조건: 강원도에 위치한 식품공장의 공장 ID, 공장 이름, 주소 조회
- WHERE 절로 옮긴 방식: ADDRESS LIKE '강원도%'
- 정렬 기준: FACTORY_ID 기준 오름차순 정렬 (ASC)
```

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/3abf6318-8983-4f9c-8e45-18e1affc2a19" />

## 🧩 문제 3

문제 링크: [이름에 el이 들어가는 동물 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/59047)

풀이 과정:

```
- 찾으려는 문자열 패턴: 이름에 'EL'이 포함된 개
- 대소문자를 처리한 방식: MySQL의 LIKE는 기본적으로 영문 대소문자를 구분하지 않아 그대로 비교
- 정렬 기준:NAME 기준 오름차순, 이름이 같으면 ANIMAL_ID 기준 오름차순
```

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/80cf2419-79f6-4bd6-ac74-89def9dcf7fc" />


## 🧩 문제 4

문제 링크: [카테고리 별 상품 개수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/131529)

풀이 과정:

```
- 추출한 문자열 범위: PRODUCT_CODE의 앞 2자리
- 그룹화 기준: PRODUCT_CODE 앞 2자리인 카테고리 코드
- 정렬 기준: 카테고리 코드 기준 오름차순 정렬
```

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/3d085264-c6c1-44c0-ac66-bdcf94af003f" />


---

# 4️⃣ 이번 주 회고

```
1. 쿼리 작성 흐름을 잡을 때 도움이 된 방법: SELECT → FROM → WHERE → GROUP BY → ORDER BY 순서로 필요한 조건을 정리하기
2. 타입 변환이나 문자열 처리에서 조심해야 할 점: 데이터 타입과 문자열의 위치, 대소문자, 공백 여부를 확인하기
3. 앞으로 문제 풀이 때 먼저 확인할 것: 어떤 컬럼을 조회해야 하는지, 조건과 정렬 기준이 무엇인지 먼저 확인하기
```

수고하셨습니다!
