# 소프트웨어 테스팅의 기초

이양(handover)
검증(validation)
이해관계자(영어: stakeholder)
회귀 테스트(Regression Test) 회귀 버그는 이전에 제대로 작동하던 소프트웨어 기능에 문제가 생기는 것을 가리킨다. 일반적으로 회귀 버그는 프로그램 변경 중 뜻하지 않게 발생한다.

테스팅/디버깅: 결함에 의해 발생된 장애를 드러내는 활동/결함의 원인을 밝히는 개발 활동

## 테스팅의 일반적 원리

### 완벽한 테스팅(exhaustive testing)은 불가능하다.
- 한 프로그램 내의 내부조건이 무수히 많을 수 있음(무한 경로)
- 입력이 가질 수 있는 모든 값의 조합이 무수히 많음(무한 입력값)
- GUI 이벤트 발생 순서에 대한 조합도 무수히 많음(무한 타이밍)
따라서 Risk based testing을 해야 된다.

### 결함 집중(defect clustering)
- 자체적으로 복잡한 구조를 가지고 있는 묘듈
- 상호작용이 많은 모듈(복잡한 인터페이스)

### 살충제 패러독스(pesticide paradox) ?내성이 생긴다?
TC를 새로운 관점으로 계속해서 업데이트
ex)
[탐색적 테스팅](exploratory testing)(https://www.atlassian.com/continuous-delivery/software-testing/exploratory-testing)

Just In Time Testing 적시에("JIT")
장점
낮은 재고량은 보관 공간을 줄여 임대료와 보험 비용을 절감한다는 의미입니다.
단점
불량품의 재작업을 위한 최소한의 재고를 유지하여 실수의 여지가 적습니다.

### absence of errors fallacy
If your software or system is unusable (or does not fulfill users' wishes) then it does not matter how many defects are found and fixed – it is still unusable.
fallacy미국∙영국[ˈfæləsi]
1.(많은 사람들이 옳다고 믿는) 틀린 생각2.(인식상의) 오류 (→pathetic fallacy)

## 테스트 프로세스의 기초
- 계획과 제어(planning and control)
- 분석과 설계(analysis and design)
- 구현과 실행(implementation and execution)
- 완료 조건의 평가와 리포팅(Evaluating exit criteria and reporting) criterion[kraɪtɪriən] 1.(판단이나 결정을 위한) 기준
- 테스트 마감 활동(test closure activities)

### 계획과 제어(planning and control)
호환성(compatibility) 테스팅 범위
5장에서

### 분석과 설계(analysis and design)
요구사항 명세서(Requirement specification)
4장에서

### 구현과 실행(implementation and execution)
Test harnesses == test driver
1.	마구(馬具)
2.	(사람 몸에 매는 마구 비슷한) 벨트[용구] a safety harness
테스트를 진행하기 위한 환경의 일부분으로, 단위 시험이나 모듈 시험에 사용하기 위해 만든 상위의 임시 모듈이다. 시험 드라이버 (test driver)라고도 하며, 단순히 시험을 위한 사용자 인터페이스를 제공하거나 정교하게 제작된 경우, 코드가 변경되었을 때에도 항상 같은 결과를 제공하여 시험을 자동화시킬 수 있도록 디자인되어 있다.

test stub/mock(전체 중 일부/가짜) https://luran.me/343
예상 결과와 실제 결과간의 불일치를 incidents 또는 defects라 한다.
incidents : defects 를 포함하는 개념으로 issues와 거의 유사한 의미
1.(특히 특이하거나 불쾌한) 일[사건]
His bad behaviour was just an isolated incident.
그의 잘못된 행동은 그저 하나의 개별적인 일이었다.
2.(범죄·사고 등의) 사건
There was a shooting incident near here last night.
지난밤 이 인근에서 총격 사건이 있었다.
3.(국가 간의, 흔히 무력이 개입되는) 사건[분쟁]
a border/diplomatic incident
국경/외교 분쟁발음듣기

결과와 현상을 분석
- 테스트 케이스 자체의 결함: (스크립트, 시나리오, 잘못된 test data or input)
- 테스트 정황(context) 결함: (스크립트, 시나리오 등의) 테스트 수행 상의 오류 ,테스트 데이터 입력 오류
- 어플리케이션 결함: 테스트 문서(specification, 명세서), SW/HW, procedure, 설치, 코드 상의 결함
- app contect 결함: 사용자의 오류, 테스트 환경(OS, DBMS( 데이터베이스 관리 시스템 )과 관련된 소프트웨어 결함
조치 후 결과 확인 위해 테스트 활동을 반복
- 실패한 테스트 실행 Confirmation testing
- 수정으로 인한 새로운 버그, 변경되지 않은 부분에서 수정 사항과 연관된 버그 Regression testing

결함 유형
- 기획시 유입된 결함
- 설계시 유입된 결함
- 코딩시 유입(연관 변수 파악 부족, 예외 사항 고려 부족)
- 테스트 부족으로 유입
- 마무리 부족

결함 심각도(severity level)에 따른 분류
- 치명적(show stopper), 매우 심각(fatal), 심각(no workaround), 보통(workaround), 경미(comsmetic) 	겉치레에 불과한, 허울뿐인 cosmetic case 명사 a small piece of luggage especially for cosmetics
- critical defects, major dejects, average defects, minor defects, enhancement
- major, minor, trifle 하찮은 것
- A, B, C
결함 심각도와 결함 우선순위는 별개이다.
- resolve immediately, give high attention, normal queue, low priority

### test exit criteria and reporting
- 테스트 실행 결과(test logs)가 완료조건에 부합하는지
- 추가 테스트 필요한지, 명세된 테스트 완료 조건을 변경해야 하는지에 대한 평가 수행
- 이해관계자에게 배포할 테스트 요약 보고서
5장

[metrics](https://www.tricentis.com/blog/64-essential-testing-metrics-for-measuring-quality-assurance-success/)
Metrics는 흔히 Calculate(계산하다),
Compute(산출하다),
Evaluate(평가하다),
Measure(측정하다)와 같이
'측정을 의미하는 동사'
Metrics는 측정하는 영역을 뜻하는 명사의 수식을 받기도 하는데,
예로 Sales Metrics(판매 측정),
Performance metrics(업무 수행 측정),
Customer relationship metrics
(소비자 관계 측정)
inspection(점검)
