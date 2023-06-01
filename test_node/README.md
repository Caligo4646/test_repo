# AIFFEL Campus Online 4th Code Peer Review Templete
- 코더 : 코더 1인의 이름을 작성하세요.
- 리뷰어 : 본인의 이름을 작성하세요.


# PRT(PeerReviewTemplate)
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.
- [ ] 1.코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
        마지막 코드 실행 셀이 에러가 나서 정상적으로 동작하지 않는다고 판단했습니다.  
'''
TclError: no display name and no $DISPLAY environment variable
'''

- [x] 2.주석을 보고 작성자의 코드가 이해되었나요?
  > 위 항목에 대한 근거 작성 필수
        게임 시작 전 규칙에 대한 부분을 상세하게 설명해주셨고, 핵심 코드 부분에 대한 설명이 잘 적혀있었습니다.

- [x] 3.코드가 에러를 유발할 가능성이 있나요?
  > 위 항목에 대한 근거 작성 필수
        GUI 환경으로 구현해주셨는데, DISPLAY 환경변수에 대한 부분을 참조하지 못하고 있는 것 같습니다.
'''
TclError: no display name and no $DISPLAY environment variable
'''

- [x] 4.코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 위 항목에 대한 근거 작성 필수
        '''
        게임판은 가로 10칸, 세로 10칸 10x10 행렬로 이루어져 있고, 각 칸은 1부터 100까지 정수로 채운다.

        유저 수를 입력받는다. 4명까지 입력받을 수 있다.

        유저 수만큼 player 객체를 생성한다. 변수 이름은 알파벳 순서로 한다.

        player 객체는 1부터 6까지 주사위를 굴려 나온 값과 현재 위치값을 더한 값으로 이동한다.

        각 말의 위치 초깃값은 0으로 한다

        Key:Value -> 현재위치:이동할위치

        팀 갯수에 맞춰서 말을 객체로 생성 ->

        [] 그래픽 라이브러리

        인터페이스 구성
        현재위치 position 을 10으로 나눠서 (나머지, ) 로 좌표 표시
        거북이를 좌표로 이동 turtle.goto(x,y)
        '''
- [x] 5.코드가 간결한가요?
  > 위 항목에 대한 근거 작성 필수
        함수화 및 클래스화 해서 코드를 작성해주셔서 간결하게 코드를 작성해주신 것 같습니다.
```Python
 class player():
  def __init__(self):
    self.pos = 0   # 현재 위치 메모리

  def roll_dice(self):
      # 현재위치에서 주사위 만큼 이동하는 함수 
    print(self.pos)
    self.pos += dice()
```

# 예시
1. 코드의 작동 방식을 주석으로 기록합니다.
2. 코드의 작동 방식에 대한 개선 방법을 주석으로 기록합니다.
3. 참고한 링크 및 ChatGPT 프롬프트 명령어가 있다면 주석으로 남겨주세요.
```python
# 사칙 연산 계산기
class calculator:
    # 예) init의 역할과 각 매서드의 의미를 서술
    def __init__(self, first, second):
        self.first = first
        self.second = second
    
    # 예) 덧셈과 연산 작동 방식에 대한 서술
    def add(self):
        result = self.first + self.second
        return result

a = float(input('첫번째 값을 입력하세요.')) 
b = float(input('두번째 값을 입력하세요.')) 
c = calculator(a, b)
print('덧셈', c.add()) 
```

# 참고 링크 및 코드 개선
```python
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```