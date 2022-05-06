# software lifecycle and testing

~~~
~~~
## 구조적 테스팅(structural testing)
https://blog.naver.com/PostView.nhn?blogId=suresofttech&logNo=221833396343&parentCategoryNo=&categoryNo=155&viewDate=&isShowPopularPosts=false&from=postView
커버리지 coverage : 필요한 회선 품질을 유지하면서 양호한 통신을 할 수 있는 영역
구조적/코드 커버리지는 소프트웨어의 테스트 케이스가 얼마나 충족되었는지를 나타내는 지표
블랙 박스 테스트(Black-box test)
- 소프트웨어의 내부 구조나 작동 원리를 모르는 상태에서 동작을 검사하는 방식이다.
- 올바른 입력과 올바르지 않은 입력을 입력하여 올바른 출력이 나오는지 테스트하는 기법이다.
- 사용자 관점의 테스트 방법이라 볼 수 있다.

화이트 박스 테스트(White-box test)
- 응용 프로그램의 내부 구조와 동작을 검사하는 테스트 방식이다.
- 소프트웨어 내부 소스 코드를 테스트하는 기법이다.
- 개발자 관점의 단위 테스트 방법이라 볼 수 있다.

구조적인(화이트 박스) 테스트 기법은 ㅌ특정 유형의 구조 커버리지를 평가하여 테스팅의 보장성 또는 충분함(Thoroughness)을 측정, 이를 위해 명세 기반 기법을 적용한 다음에 사용할 때 가장 좋은 결과.
thoroughness[θə́:rounis]
명사
1.[U] 완전, 철저함; 순전함
4장

코드 뿐만 아니라 호출 체계(구조, Hierarchy[haɪərɑːrki])와 같은 시스템의 아키텍처에 기반을 두고 수행될 수 있다.
구조적 테스팅 접근법: 시스템, 시스템 통합, 인수 테스팅으 ㅣ테스트 레벨(ex, 비즈니스 모델이나 메뉴 구조)

## Confirmation(re-testing) and regression (퇴행, 퇴보; 회귀) testing
위험성이 높으면 테스팅을 intensive and higher depth로 한다.
해당 테스팅은 자동화에 적합한 후보이다.

## maintenace testing
[migration](http://www.terms.co.kr/migration.htm)
영향도 분석(impact analysis)
명세(specifications)
유지보수는 중요성에 비해 기간이 매우 적게 주어진다.
