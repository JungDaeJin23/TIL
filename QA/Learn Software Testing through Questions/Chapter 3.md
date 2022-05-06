# static techniques

리뷰는 동적 테스팅에서 발견하기 어려운 개발 중간산출물의 누락(omissions; 생략)을 발견할 수 있다.
장애가 아닌 결함을 발견


## phase of a formal review
인스펙션(inspection; 검사) https://devinus.tistory.com/14, [워크스루, 인스펙션, 공식검토](https://noil0816.tistory.com/93)

1. 계획 활동. 시작 및 종료 기준(entry and exit criteria)을 정의. 범위 설정
2. 시작kick off
3. 개별 준비. 사전 리뷰를 통해 질문과 의견(comment) 기록
4. 리뷰 미팅. 토의, 상세 회의록(minutes; 의사록) 작성.
5. 재작업rework. 대상 문서의 작성자가 수정
6. 후속 처리 확인 follow up. 결함 처리되었는지 확인. 관련 측정치(metrics;측정항목)를 수집. 리뷰 종료 기준 점검
 

## type of review
- informal review
- walkthrough. 
  작성자에 의한 진행 및 제어.
  시나리오 사용. 예행 연습(dry run)
  major purpose: 학습, 이해 향상, 결함 발견
- technical review
- inspection
  훈련된 리더에 의한 진행
  시작 종료 조건 있는 체크리스트와 규칙 기반. 
- 동료들 사이에서 진행되면 peer review

## static analysis by tools
사용 제품이나 오픈 소스 있음

# 실전 문제
요구사항 리뷰 중 테스트 엔지니어가 가장 관심을 가져야 하는 것은
테스팅 관점에서 요구사항 검토. SW가 테스팅이 가능한지에 대한 시각에서 리뷰에 참여
요구사항 명세를 보고 조기 테스트 설계 TC도출. 명세의 모호한 부분이나 결함 발견

사업적 리스크가 높은 영역은 워크쓰루가 효과적
기술적 리스크와는 다르다.

정적 분석은 대부분 개발자들에 의해서만 이루어진다.
