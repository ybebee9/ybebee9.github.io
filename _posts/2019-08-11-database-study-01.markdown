---
layout: post
title:  "1.1 SQL 파싱과 최적화"
date:   2019-08-11
categories: Database
---
<br>
## 1.1.1 구조적, 집합적, 선언적 질의언어<br>
<br>
### SQL<br>
-  'Structured Query Language'의 줄임말로 구조적 질의 언어다.<br>
- 기본적으로 구조적(Structured)이고 집합적(set-based)이고 선언적(declarative)인 질의 언어다.<br>
<br>
<br>
### SQL 옵티마이저<br>
- 프로시저를 만들어 내는 DBMS 내부 엔진이 바로 SQL 옵티마이저이며, 프로그래밍을 대신 해주는 셈이다.<br>
<br>
<br>
### SQL최적화<br>
- DBMS 내부에서 프로시저를 작성하고 컴파일해서 실행 가능한 상태로 만드는 전 과정을 'SQL 최적화'라고 한다.<br>
<br>
<br>
## 1.1.2 SQL 최적화<br>
최적화 과정을 세분화 하면 'SQL파싱 - SQL 최적화 - 로우소스 생성' 3단계로 나눌 수 있다.<br>
<br>
<br>
### (1) SQL파싱<br>
사용자로부터 SQL을 전달받으면 가장 먼저 SQL 파서(Parser)가 파싱을 진행한다. SQL파싱을 요약하면 아래와 같다.<br>
- 파싱 트리 생성 : SQL 문을 이루는 개별 구성요소를 분석해서 파싱 트리 생성<br>
- Syntax 체크 : 문법적 오류가 없는지 확인<br>
- Semantic 체크 : 의미상 오류가 없는지 확인(ex. 존재하지 않는 테이블 또는 컬럼을 사용했는지, 사용한 오브젝트에 대한 권한이 있는지 확인)<br>
<br>
<br>
### (2) SQL최적화<br>
SQL 옵티마이저는 미리 수집한 시스템 및 오브젝트 통계정보를 바탕으로 다양한 실행경로를 생성해서 비교한 후 가장 효율적인 하나를 선택한다. 데이터베이스 성능을 결정하는 가장 핵심적인 엔진이다.<br>
<br>
<br>
### (3) 로우 소스 생성<br>
SQL 옵티마이저가 선택한 실행경로를 실제 실행 가능한 코드 또는 프로시저 형태로 포맷팅 하는 단계다. 로우 소스 생성기(Row-Source Generator)가 그 역할을 맡는다.<br>
<br>
<br>
## 1.1.3 SQL 옵티마이저<br>
SQL 옵티마이저는 사용자가 원하는 직업을 가장 효율적으로 수행할 수 있는 최적의 데이터 액세스 경로를 선택해주는 DBMS의 핵심 엔진이다. 옵티마이저의 최적화 단계를 요약하면 아래와 같다.
- 사용자로부터 전달받은 쿼리를 수행하는데 후보군이 될만한 실행계획들을 찾아낸다.
- 데이터 딕셔너리(Data Dictionary)에 미리 수집해 둔 오브젝트 통계 및 시스템 통계정보를 이용해 각 실행계획의 예상 비용을 산정한다.
- 최저비용을 나타내는 실행계획을 선택한다.
<br>
※ 옵티마이저, SQL파서, 로우소스생성기는 별도 프로세스가 아니라 서버 프로세스가 가진 기능(Function)일 뿐이다. <br>
<br>
<br>
## 1.1.4 실행계획과 비용<br>
<br>
SQL 옵티마이저는 자동차 내비게이션과 여러모로 흡사하다. 일례로, 경로요약이나 모의주행 같은 기능이 그렇다. <br>
경로를 검색하고 나서 이동 경로를 미리 확인하는 기능이며, 내비게이션이 선택한 경로가 마음에 들지 않으면 검색모드를 변경하거나 경유지를 추가해서 운전자가 원하는 경로로 바꿀 수 있다. 
<br>
DBMS에도 'SQL 실행경로 미리보기' 기능이 있다. 실행계획(Execution Plan)이 바로 그것이다.<br>
SQL 옵티마이저가 생성한 처리절차를 사용자가 확인할 수 있게 트리구조로 표현한것이 실행계획이다.<br>
<br>
미리보기 기능을 통해 자신이 작성한 SQL이 테이블을 스캔하는지 인덱스를 스캔하는지, 인덱스를 스캔한다면 어떤 인덱스인지 확인할 수 있고, 예상과 다른 방식으로 처리된다면 실행경로를 변경할 수 있다.<br>
<br>
비용(Cost)은 쿼리를 수행하는 동안 발생할 것으로 예상하는 I/O 횟수 또는 예상 소요시간을 표현한 값이다.<br>
<br>
SQL 실행계획에 표시되는 Cost는 어디까지나 예상치다.<br>
실행경로를 선택하기 위해 옵티마이저가 여러 통계정보를 활용해서 계산해 낸 값이다. 실측치가 아니므로 실제 수행할 때 발생하는 I/O 또는 시간과 많은 차이가 난다.
<br>
<br>
## 1.1.5 옵티마이저 힌트<br>
SQL옵티마이저는 대부분 좋은 선택을 하지만, 완벽하진 않다. SQL이 복잡할수록 실수할 가능성도 크다.<br>
통계정보에 담을 수 없는 데이터 또는 업무 특성을 활용해 개발자가 직접 더 효율적인 액세스 경로를 찾아낼 수도 있다.<br>
이럴 때 옵티마이저 힌트를 이용해 데이터 액세스 경로를 바꿀 수 있다.<br>
<br>
```SQL
// 힌트 사용법(주석 기호에 '+'를 붙이면 된다)
SELECT 	/*+ INDEX(A 고객_PK) */
		고객명, 연락처, 주소, 가입일시
FROM	고객 A
WHERE	고객ID = '000000008';
```
<br>
<br>
아래와 같은 방식도 있지만 줄바꿈 오류가 발생할 수 있기 때문에 가급적 쓰지 않는걸 추천한다.<br>
```SQL
// 비추천
SELECT 	--+ INDEX(A 고객_PK)
		고객명, 연락처, 주소, 가입일시
FROM	고객 A
WHERE	고객ID = '000000008';
```
<br>
<br>
## ※ 주의사항<br>
<br>
1. 힌트 안에 인자를 나열할 땐 ','(콤마)를 사용할 수 있지만, 힌트와 힌트 사이에 사용하면 안된다.<br>
<br>
```SQL
/*+ INDEX(A A_X01) INDEX(B, B_X03) */	→ 모두 유효
/*+ INDEX(C), FULL(D) */			   → 첫 번째 힌트만 유효
```
<br>
<br>
2. 테이블을 지정할 때 아래와 같이 스키마명까지 명시하면 안 된다.<br>
<br>
```SQL
SELECT 	/*+ FULL(SCOTT.EMP) */  → 무효
FROM 	EMP
```
<br>
<br>
3. FROM 절 테이블명 옆에 ALIAS를 지정했다면, 힌트에도 반드시 ALIAS를 사용해야한다. FROM절에 ALIAS를 지정했는데 힌트에는 아래와 같이 테이블명을 사용하면, 그 힌트는 무시된다.<br>
<br>
```sql
SELECT /*+ FULL(EMP) */	→ 무효 
FROM	EMP E
```
<br>
<br>
### 힌트를 부분적으로 지정할지, 빈틈없이 지정할지 개발자가 결정할 수 있다.<br>
<br>
```SQL
SELECT	/*+ INDEX(A (주문일자)) */
		A.주문번호, A.주문금액, B.고객명, B.연락처, B.주소
FROM	주문 A, 고객 B
WHERE	A.주문일자 = :ORD_DT
AND		A.고객ID = B.고객ID
```
- 힌트를 부분적으로 지정한 예제. 주문 테이블을 액세스할 때 주문일자 컬럼이 선두인 인덱스를 사용하도록 힌트로 지정했다.조인 방식과 순서, 고객 테이블 액세스 방식은 옵티마이저가 알아서 판단하도록 남겨뒀다.<br>
<br>
<br>
```SQL
SELECT 	/*+ LEADING(A) USE_NL(B) INDEX(A (주문일자)) INDEX(B 고객_PK) */
		A.주문번호, B.주문금액, B.고객명, B.연락처, B.주소
FROM	주문 A, 고객 B
WHERE	A.주문일자 = :ORD_DT
AND		A.고객ID = B.고객ID
```
- 힌트를 빈틈없이 지정한 예제. 옵티마이저가 절대 다른 방식을 선택하지 못하도록 힌트를 빈틈없이 지정했다.<br>
<br>
<br>
 어떤 방식이 옳은지는 애플리케이션 환경에 따라 다르다. 기왕에 힌트를 쓸 거면, 빈틈없이 기술해야 한다.<br>
<br>
<br>
### 자주 사용하는 힌트 목록<br>
<br>
|      분류       |       힌트       |                             설명                             |
| :-------------: | :--------------: | :----------------------------------------------------------: |
|   최적화 목표   |     ALL_ROWS     |                     전체 처리속도 최적화                     |
|        "        |  FIRST_ROWS(N)   |                   최소 N건 응답속도 최적화                   |
|   액세스 방식   |       FULL       |                   Table Full Scan으로 유도                   |
|        "        |      INDEX       |                     Index Scan으로 유도                      |
|        "        |    INDEX_DESC    |               Index를 역순으로 스캔하도록 유도               |
|        "        |    INDEX_FFS     |                Index Fast Full Scan으로 유도                 |
|        "        |     INDEX_SS     |                   Index Skip Scan으로 유도                   |
|    조인순서     |     ORDERED      |                FROM 절에 나열된 순서대로 조인                |
|        "        |     LEADING      | LEADING 힌트 괄호에 기술한 순서대로 조인. ex) LEADING(T1 T2) |
|        "        | SWAP_JOIN_INPUTS | 해시 조인 시, BUILD INPUT을 명시적으로 선택. ex) SWAP_JOIN_INPUTS(T1) |
|    조인방식     |      USE_NL      |                       NL 조인으로 유도                       |
|        "        |    USE_MERGE     |                   소트 머지 조인으로 유도                    |
|        "        |     USE_HASH     |                      해시 조인으로 유도                      |
|        "        |      NL_SJ       |                     NL 세미조인으로 유도                     |
|        "        |     MERGE_SJ     |                 소트 머지 세미조인으로 유도                  |
|        "        |     HASH_SJ      |                    해시 세미조인으로 유도                    |
| 서브쿼리 팩토링 |   MATERIALIZE    | WITH 문으로 정의한 집합을 물리적으로 생성하도록 유도. ex) WITH /*+ MATERIALIZE */ T AS (SELECT ···) |
|        "        |      INLINE      | WITH 문으로 정의한 집합을 물리적으로 생성하지 않고 INLINE으로 처리하도록 유도. ex)  WITH /*+ INLINE */ T AS (SELECT ···) |
|    쿼리변환     |      MERGE       |                         뷰 머징 유도                         |
|        "        |     NO_MERGE     |                         뷰 머징 방지                         |
|        "        |     UNINEST      |                   서브쿼리 Unnesting 유도                    |
|        "        |    NO_UNINEST    |                   서브쿼리 Unnesting 방지                    |
|        "        |    PUSH_PRED     |                    조인조건 Pushdown 유도                    |
|        "        |   NO_PUSH_PRED   |                    조인조건 Pushdown 방지                    |
|        "        |    USE_CONCAT    |         OR 또는 IN-List 조건을 OR-Expansion으로 유도         |
|        "        |    NO_EXPAND     |        OR 또는 IN-List 조건에 대한 OR-Expansion 방지         |
|    병렬처리     |     PARALLEL     | 테이블 스캔 또는 DML을 병렬방식으로 처리하도록 유도. ex) PARALLEL(T1 2) PARALLEL(T2 2) |
|        "        |  PARALLEL_INDEX  |          인덱스 스캔을 병렬방식으로 처리하도록 유도          |
|        "        |  PQ_DISTRIBUTE   | 병렬 수행 시 데이터 분배 방식 결정. ex) PQ_DISTRIBUTE(T1 HASH HASH) |
|      기타       |      APPEND      |                  Direct-Path Insert 로 유도                  |
|        "        |   DRIVING_SITE   | DB Link Remote 쿼리에 대한 최적화 및 실행 주체 지정(Local 또는 Remote) |
|        "        |    PUSH_SUBQ     |           서브쿼리를 가급적 빨리 필터링하도록 유도           |
|        "        |   NO_PUSH_SUBQ   |          서브쿼리를 가급적 늦게 필터링 하도록 유도           |
<br>
<br>
<br>
<br>
<br>
![img01]({{ site.baseurl }}/images/post/sqlTuning/book/bookCover.PNG)<br>
<br>
본 포스팅은 친절한 SQL 튜닝 책을 공부하여 작성한 내용입니다.<br>
<br>
<br>
<br>
<br>