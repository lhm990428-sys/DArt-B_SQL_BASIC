# 📘 SQL_BASIC 3주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 집계 함수와 `GROUP BY`, `HAVING`을 학습합니다.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_3rd_TIL

### 섹션 3. 데이터 탐색 - 조건, 추출, 요약

### 2-5. 집계(GROUP BY + HAVING + SUM/COUNT)

### 2-7. 정리

### 2-8. 새로운 집계 함수 소개(GROUP BY ALL, 2024-02-26에 나온 함수)

---

## ✨ 선택 강의

- 2-6. 연습 문제: 집계와 조건 조회를 더 연습하고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | ✅ |
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
- COUNT
- SUM
- AVG
- MAX
- MIN
- GROUP BY
- HAVING
- 집계 기준

## 01.

```
개념 이름: GROUP BY
개념 설명: 특정 컬럼을 기준으로 데이터를 그룹화하여 그룹별 집계값을 구할 때 사용한다.
예시 쿼리:
SELECT type1, COUNT(*) AS cnt
FROM `basic.pokemon`
GROUP BY type1;
```

## 02.

```
개념 이름: HAVING
개념 설명: GROUP BY로 집계한 결과에 조건을 적용할 때 사용한다. WHERE가 집계 전 조건이라면 HAVING은 집계 후 조건이다.
예시 쿼리:
SELECT type1, COUNT(*) AS cnt
FROM `basic.pokemon`
GROUP BY type1
HAVING COUNT(*) >= 10;
```


---

# 2️⃣ 수행 인증란

아래 중 하나 이상을 첨부해주세요.

- 강의 수강 화면 캡처
<img width="1915" height="1197" alt="image" src="https://github.com/user-attachments/assets/d7d11433-1927-41a0-be67-583352696444" />
<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/c39b938d-bcb7-4467-8886-a3fc6e560161" />

- 문제 풀이 정답 화면 캡처
- SQL 실행 결과 화면 캡처
<img width="1917" height="1191" alt="image" src="https://github.com/user-attachments/assets/48c12a04-31f4-47a8-827e-a1d76b9c2271" />
<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/6e916e30-dcfe-46b9-9a59-deec64a9dcd5" />
<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/bf11097e-7892-4aab-a356-c6bb644895b8" />

---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [최댓값 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/59415)

풀이 과정:

```
- 문제 요구사항: 가장 최근에 들어온 동물은 언제 들어왔는지 조회하는 SQL 문을 작성해주세요.
- 사용한 SQL 절: max 절을 이용함.
- 새로 배운 점: 문제의 요구사항이 max 절만 사용하는 건지 모르고 animal_id도 같이 추출해서 오답처리됨. 문제를 정확히 이해하고 필요한 부분만 추출해야겠다고 생각함.
그리고 datatime같은 컬럼에도 max절을 쓸 수 있다는 것을 알게됨.
```

<img width="1902" height="1198" alt="image" src="https://github.com/user-attachments/assets/b52503d1-70f9-4b2d-9f1a-692eb45f6862" />


## 🧩 문제 2

문제 링크: [가장 비싼 상품 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/131697)

풀이 과정:

```
- 사용한 집계 함수:
- 집계 대상 컬럼:
- 결과를 검증한 방법:
```

<!-- 정답을 맞추게 되면, 정답입니다. 이 부분을 캡처해서 이 주석을 지우시고 첨부해주시면 됩니다. -->

## 🧩 문제 3

문제 링크: [고양이와 개는 몇 마리 있을까](https://school.programmers.co.kr/learn/courses/30/lessons/59040)

풀이 과정:

```
- 그룹화 기준:
- WHERE와 HAVING 중 사용한 절:
- 처음 틀렸다면 틀린 이유:
- 새로 배운 SQL 패턴:
```

<!-- 정답을 맞추게 되면, 정답입니다. 이 부분을 캡처해서 이 주석을 지우시고 첨부해주시면 됩니다. -->

---

# 4️⃣ 이번 주 회고

```
1. 문제를 SQL로 옮길 때 가장 어려웠던 부분:
2. WHERE와 HAVING의 차이를 어떻게 이해했는지:
3. 다음 주에 더 연습하고 싶은 문제 유형:
```

수고하셨습니다!
