오류(error):
결함(defects, bug, fault): 장애를 발생시키는 원인
장애(failure):

목적에 따라 테스팅의 방향은 달라진다.
- 개발과정 테스팅
- 인수 테스팅
- 품질을 평가하기 위한 테스팅
- 유지보수 테스팅 -> 변경 위주, regression, 새 결함이 유입되었는지
- 운영 테스팅 -> 신뢰성, 가용성과 같은 시스템의 특성을 평가(잘 모르겠음)

테스팅 != 디버깅
테스팅은 문서(소스 코드 포함)의 리뷰와 [static analysis](https://blog.naver.com/PostView.naver?blogId=melong826&logNo=222201924884)에 의한 테스팅을 포함

2. 리스크 분석과 결정된 우선순위에 따라 테스팅 활동에 집중해야 한다.(Risk-based testing)
3. 개발 초기에 테스팅을 시작
4. Defect clustering
5. pesticide paradox
6. 테스팅은 정황, 문맥(context)에 의존적
7. absence of errors fallacy(그릇된 생각, 궤변)

test harnesses([Tool](https://www.tutorialspoint.com/what-is-a-test-harness-tools-examples)) = test driver + test stub https://www.sten.or.kr/bbs/board.php?bo_table=test_story&wr_id=3717
테스트를 진행하기 위한 환경의 일부분으로, 단위 시험이나 모듈 시험에 사용하기 위해 만든 상위의 임시 모듈이다.
