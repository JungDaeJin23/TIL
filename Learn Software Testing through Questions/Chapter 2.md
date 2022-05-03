# 소프트웨어 개발 모델
모델 별 테스트 방벙이 다르다.
1. [V-model(순차적 개발 모델)](https://ko.wikipedia.org/wiki/V_%EB%AA%A8%EB%8D%B8)


![image](https://user-images.githubusercontent.com/46150052/166460470-4c358ab1-d9d4-4c4d-92d5-4eeed52478db.png)
테스트 설계와 같은 테스트 활동을 코딩 이후가 아닌 프로젝트 시작 시에 함께 시작

2. 반복적-점증적 개발 모델(iterative incremental)
agile(민첩)
점증적인 특성으로 인해 regression testing의 중요성이 커진다.

3. life cycle model
개발 활동과 테스팅 활동 대응

반문: 수명주기가 없는 모델도 있나?

# 테스트 레벨
컴포넌트 테스팅 == 코드 리뷰

통합테스팅 https://itwiki.kr/w/%ED%86%B5%ED%95%A9_%ED%85%8C%EC%8A%A4%ED%8A%B8#.EB.B9.85.EB.B1.85_.ED.86.B5.ED.95.A9
매 통합 마다 테스팅 하는 것이 바람직
상향식, 하향식, 백본(backbone; 중추) 통합.

트랜잭션(transaction)이란 "쪼갤 수 없는 업무 처리의 최소 단위"를 말한다 http://wiki.hash.kr/index.php/%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98
아키텍처(Architecture)는 시스템의 물리적 또는 기능적 구조를 말한다. http://wiki.hash.kr/index.php/%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98

시스템 테스팅
기능적/비기능적(구조적: 메뉴 구조나 웹 페이지 네비게이션 요소)인 시스템의 요구 사항을 모두 포함

하나의 제품 == 시스템?

인수(acceptance) testing
확신을 얻는 과정.
배포나 실제 사용할 준비가 되었는지 평가.

테스트 유형
