## 기능 요구 사항
    목적 : 1부터 9까지 서로 다른 수로 이루어진 3자리 수 맞추기 게임
    입력 : 서로 다른 3자리의 수
           게임이 끝난 경우 재시작/종료를 구분하는 1과 2중 하나의 수
              -- 그 외의 입력 : 오류
    출력 : 입력한 수에 대한 결과
      1. 볼, 스트라이크 개수로 표시 : O볼 O스트라이크
      2. 맞춘 숫자가 하나도 없을 시 : 낫싱
      3. 3개 숫자를 모두 맞힐 경우 : 3스트라이크
           -> 게임 종료, 게임 재시작 및 프로그램 종료

## 구현할 기능 정리
#### 흐름에 따른 기능 정리
    1. 게임시작
    2. 서로 다른 임의의 수 3개 생성
    3. 사용자가 3자리 숫자 입력
      - 같은 수, 같은 자리 : 스트라이크
      - 같은 수, 다른 자리 : 볼
      - 같은 수가 없음 : 낫싱
         -- 잘못된 값을 입력할 경우 애플리케이션 종료
     4. 컴퓨터가 선택한 3개 숫자를 모두 맞추면 게임 종료
     5. 게임 재시작 및 종료

#### MVC 패턴에 따른 기능 정리
##### model
      1. 컴퓨터가 만든 숫자
      2. 사용자가 입력한 숫자
##### view
      1. 사용자 숫자 입력 뷰
      2. 사용자 게임 재시작 및 종료 입력 뷰
      3. 몇 개의 숫자를 맞춘지 확인하는 뷰
      4. 게임 재시작 및 종료 여부를 묻는 뷰
##### controller
      1. 조건에 맞는 숫자가 입력되었는지 확인
      2. 숫자 힌트
         - 해당 숫자와 해당 자리가 맞으면 스트라이크
         - 숫자만 맞으면 볼
         - 같은 수가 없으면 낫싱
      3. 숫자를 모두 맞히면 게임 종료
      4. 게임 재시작 및 프로그램 종료
