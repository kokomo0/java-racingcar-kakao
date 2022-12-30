# java-racingcar-kakao

### 리팩터링 요구사항
- 핵심 비지니스 로직을 가지는 객체를 domain 패키지, UI 관련한 객체를 view 패키지에 구현한다.
- MVC 패턴 기반으로 리팩토링해 view 패키지의 객체가 domain 패키지 객체에 의존할 수 있지만, domain 패키지의 객체는 view 패키지 객체에 의존하지 않도록 구현한다.
- 테스트 가능한 부분과 테스트하기 힘든 부분을 분리해 테스트 가능한 부분에 대해서만 단위 테스트를 진행한다.

### 기능 요구사항

기능 요구사항

- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다. 
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 random 값을 구한 후 random 값이 4 이상일 경우 전진하고, 3 이하의 값이면 멈춘다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.

### 기능 목록
자동차
- 5자 이하로 이루어진 이름을 가진다
- 현재 자동차의 위치 정보를 가진다
- 자동차는 한 번에 한 칸 전진할 수 있다
  - 랜덤 값이 4 이상일 경우 한 칸 전진한다
  - 랜덤 값이 3 이하일 경우 정지한다

레이싱
- 여러대의 자동차 정보를 가지고 있다
- 각 라운드마다 자동차를 전진하거나 정지한다 
  - 랜덤 값이 4 이상일 경우 자동차를 전진한다 
  - 랜덤 값이 3 이하일 경우 자동차를 정지한다 
- 라운드가 종료될 때 마다 결과를 확인할 수 있다 
- 게임이 종료된 후 우승자를 확인할 수 있다

입력
- 쉼표로 구분된 이름 목록을 입력받는다
- 라운드 진행 횟수를 입력받는다
- 예외처리:
  - 5자 초과로 이루어진 입력은 예외처리한다
  - 1이상의 정수가 아닌 이동 횟수 입력은 예외처리한다

출력
- 각 이동마다 현재 진행상황을 출력한다
- 경주가 종료 된 후 우승자를 출력한다

