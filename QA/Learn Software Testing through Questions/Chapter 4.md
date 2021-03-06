# 테스트 설계 기법
트랜잭션(transaction)이란 "쪼갤 수 없는 업무 처리의 최소 단위"를 말한다. 잘 이해가 안된다.

원칙적으로는 결과 판정의 어려움 때문에 테스트 실행 전에 기대결과가 정의되어 있어야 한다.

## 테스트 설계 기법의 종류
- 블랙박스
- 경험기반
- 명세기반



- 구조기반
- 화이트박스

## 명세 기반 기법
### 등가 분할
입력값은 입력의 결과 값이 동일한 경우 하나의 그룹(클래스)로 가정한다.
그리고 이는 내부적으로 같은 방식으로 처리됨을 가정한다.
등가 분할 클래스는 유효한 입력 데이터와 유효하지 않은 입력 데이터(입력되지 말아야 할)를 포함 할 수 있다.

- 출력값(output)
- 내부값(inner values) 모르겠음
- 시간관련 값(Time-related values, 이벤트 이전과 이후) +개인 견해) 단순히 시간 구분(time interval)으로도 구분되는 경우도 있었음
- interface parameter

테스트는 등가로 분할된 영역을 커버하기 위해 설계.


### 경계값 분석
- 적용 용이
- 결합 발견률 높음
- 명시한 명세서 지원되면 적용 수월

등가 분할의 확장이고 동일한 방식으로 커버리지를 보장
트랜잭션 속도 요구사항(초당 조작)

### 결정(decision) 테이블 테스팅
conditions의 True False 조합 테이블; combinations of conditions
사업 규칙 또는 비즈니스 룰(business rule)은 특정한 사업적인 면을 정의하고 제한하는 규칙으로서 늘 참이나 거짓으로 결정된다.[^wiki]
해당 동작은 소프트웨어의 동작이 여러 가지 논리적 조건에 의존적인 모든 경우에 적용이 가능하다.

### 상태 전이 테스팅(state transition)
시스템은 현재 상황(condition)이나 이전의 이력(history)을 반영하는 상태 및 그 변화에따라 다르게 동작할 수 있다. -> 결정 테이블의 일종 아닌가? (전이: 조건들 간의 끼치는 영향이 더욱 명확)
이러한 측면을 상태 전이 다이어그램으로 표현할 수 있다.

- 일반적인 상태의 순서를 커버
- 모든 상태
- 모든 상태 전이를 실행
- 특정한 상태 전이 순서를 실행
- 불가능한 상태 전이를 테스트

임베디드나 자동화가 필요한 부분에서 사용된다.
특정한 상태를 갖는 비즈니스 객체 모델링(?모르겠음)이나 인터넷 앱 또는 비즈니스 시나리오와 같이 화면-대화창 흐름을 테스팅 할 때도 이용 가능


### usecase testing == 시나리오
유즈케이스나 비즈니스 시나리오를 기반으로 테스트를 명세화
시스템이 실제 사용되는 방식에 기반하여 "프로세스 흐름"을 기술. 따라서 생성된 테스트 케이스는 시스템이 실제 사용되는 프로세스 흐름에서 결함을 발견하는데 상당히 유용
시나리오라고도 불리는 유즈케이스는  고객이나 유저 그룹을 참여시키는 인수 테스트를 디자인할 때 유용.
통합 테스트 단계에서 서로 다른 컴포넌트 사이의 상호작용과 간섭으로 발생하는 통합 결함을 찾는데 도움이 된다.

![image](https://user-images.githubusercontent.com/46150052/167295735-80ded94e-c5f0-4a50-84eb-e8b4ba9faacb.png)

## 구조 기반 기법
- 코드 커버리지
- 결정 커버리지
- 구문 커버리지
- 구조기반 테스팅

테스트 케이스 스위트(suite, 묶음)

### 구문(statement 테스팅
테스트 케이스 스위트(suite, 묶음)에 의해 실행된 구문이 몇 퍼센트인지를 측정
### 결정 테스팅
decision points에 해당하는 제어 흐름을 다루므로 제어흐름 테스팅의 한가지 형태이다.

결정 =) 구문. 결정이 구문을 포함한다.

### 다중 조건 테스팅
더 상위 레벨에서의 구조적 커버리지
ex)통합 테스팅에서 모듈, 컴포넌트, 클래스가 실행되었는가를 기준으로 커버리지를 생각가능.

## 경험 기반 기법
- 탐색적 테스팅
- 결점 공격(fault attack)

유사 앱이나 기술로 부터 추출

공식적으로 다루기 어려운 특별한 테스트 케이스를 찾아내고 실행하는데 유용

### 오류 추정
가능한 오류를 모두 나열하고 이런 유형의 결함 또는 오류를 공격할 수 있도록 테스트 설계
이러한 접근법을 결점 공격이라 한다.

### 탐색적 테스팅
테스트 설계, 수행, 기록 그리고 학습이 동시에 진행되는 것으로, 테스트 목적을 담고 있는 테스트 차터(chater)를 기반으로 제한된 시간 내에 수행.
휴리스틱(heuristics) 또는 발견법(發見法)이란 불충분한 시간이나 정보로 인하여 합리적인 판단을 할 수 없거나, 체계적이면서 합리적인 판단이 굳이 필요하지 않은 상황에서 사람들이 빠르게 사용할 수 있게 보다 용이하게 구성된 간편추론의 방법이다.[^wikiHeuristics]

## 테스트 기법의 선택
고려되어야 할 요인
- 시스템의 유형
- 강제적인 표준 또는 법적 기준의 존재 여부
- 고객 또는 계약상의 요구 사항
- 리스크 수준(level of risk)
- 리스크 유형(type of risk)
- 테스트 목표
- 문서의 존재 유무
- 테스터의 지식 수준
- 시간과 예산
- 테스트 레벨
- 개발 수명 주기
- 유즈케이스, 상태 다이어그램 등 모델 존재 유무
- 발견된 결함 유형에 대한 이전의 경험


[^wiki]:[Wikipedia](https://ko.wikipedia.org/wiki/%EC%82%AC%EC%97%85_%EA%B7%9C%EC%B9%99)
[^wikiHeuristics]:[Wikipedia](https://ko.wikipedia.org/wiki/%ED%9C%B4%EB%A6%AC%EC%8A%A4%ED%8B%B1_%EC%9D%B4%EB%A1%A0)


# 실전 문제
2. 테스트 프로세저: TC를 효율적으로 수행하기 위해 실행이 용이한 순서대로 배치한다.
3. 요구사항에 언급되어 있지 않더라도 test oracle을 경쟁 제품이나 사용자의 도메인 지식을 활용하여 TC 도출 가능
4. TC를 수행하는 스텝이 상세하면 장단점이 있다.
7. 네거티브 테스트; 정상적으로 작동하지 않음을 보여주는 것을 목적으로 한다.
10. 이해 못함
13. Test harness = driver + stub
17. [pairwise](https://www.sten.or.kr/bbs/board.php?bo_table=test_story&wr_id=9667) 똑똑하게 조합하여 최대한 적게 모든 경우를 테스트 하는 것.
    [직교 배열](https://www.sten.or.kr/bbs/board.php?bo_table=test_story&wr_id=1049)
    각 행의 조합은 다른행과 서로 다르죠?
각 열의 조합도 다른열과 서로 다르죠?
행과 열이 페어와이즈하드는 것은 어느 행의 조합도 서로 다른 행의 조합과 서로 다르고, 어느 열의 조합도 서로 다른 열의 조합과 서로 다르다는 것을 의미한다. 그리고 직교 배열은 각 행 및 열에 선택 가능한 입력값들이 반드시 한번 이상은 들어가게 되어있다.
직교 한다. => 벡터 곱 0
18. 등가분할 어디에든 적용 가능
22. 스위치 커버리지: 각 상태(N번 state)에서 전이 가능한 상태. N번으로 distinct한 경로 조합하면 n-1 스위치 커버리지라고한다.

26.
27.

29. 상태 전이 테스팅
32. MC/DC = modified condition/ decision coverage
33. 결정, 다중 조건, 경로 
