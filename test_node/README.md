# AIFFEL Campus Online 4th Code Peer Review Templete
- 코더 : 나융
- 리뷰어 : 김경민


# PRT(PeerReviewTemplate)
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.
- [ ] 1.코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 마지막 코드셀 실행 결과 TclError가 출력되었습니다.
```Python
---------------------------------------------------------------------------
TclError                                  Traceback (most recent call last)
<ipython-input-42-8911fdd04cc0> in <cell line: 4>()
      2 
      3 # 게임판 생성
----> 4 board = turtle.Screen()
      5 board.setup(width=500, height=500)
      6 
```

- [x] 2.주석을 보고 작성자의 코드가 이해되었나요?
  > 게임 시작 전 코드 앞부분에 규칙에 대한 부분을 상세하게 설명해주셨고, 핵심 코드 부분에 대한 설명이 주석으로 잘 적혀있었습니다.
```Python
# 게임판 생성
board = turtle.Screen()
board.setup(width=500, height=500)

# 플레이어 객체 생성
players = []
for i in range(4):
  player = Player()
  player.name = chr(ord('A') + i)
  players.append(player)

# 주사위 굴리는 함수
def roll_dice():
  dice = random.randint(1, 6)
  print(dice)
  return dice

# 플레이어 객체가 게임판 위에서 움직이는 함수
def move_player(player, dice):
  player.pos += dice

  # 단축키 확인
  try:
    player.pos = shortcut[player.pos]
  except:
    pass

  # 플레이어 위치 이동
  player.turtle.goto(player.pos, 0)

# 게임 시작
while True:
  # 주사위 굴리기
  dice = roll_dice()

  # 플레이어 객체 이동
  for player in players:
    move_player(player, dice)

  # 게임 종료 여부 확인
  if any(player.pos == 100 for player in players):
    break

# 게임 종료
board.mainloop()
```

- [x] 3.코드가 에러를 유발할 가능성이 있나요?
  > GUI 환경으로 구현해주셨는데, DISPLAY 환경변수에 대한 부분을 참조하지 못하고 있는 것 같습니다.
```Python
---------------------------------------------------------------------------
TclError                                  Traceback (most recent call last)
<ipython-input-42-8911fdd04cc0> in <cell line: 4>()
      2 
      3 # 게임판 생성
----> 4 board = turtle.Screen()
      5 board.setup(width=500, height=500)
      6 

...

TclError: no display name and no $DISPLAY environment variable
```

- [x] 4.코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 게임에 대한 설명을 독스트링 형태로 잘 정리해주셨고, 해당 기능을 수행하는 모듈부분을 함수화하여 구현하였습니다.
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
```Python
 class player():
  def __init__(self):
    self.pos = 0   # 현재 위치 메모리

  def roll_dice(self):
      # 현재위치에서 주사위 만큼 이동하는 함수 
    print(self.pos)
    self.pos += dice()

    try:
      self.pos = shortcut[self.pos]   # Key:Val 을 검색해서 shorcut 딕셔너리 키에 해당되면 밸류로 이동
      print(self.pos)
    #  shorcut 딕셔너리 키에 없으면 현재위치 유지
    except:
      return self.pos
    print(self.pos)
    return self.pos

def turtle_move(user, pos):
  a = turtle.Turtle()
  a.goto(user.pos%10, user.pos//10)


# 주사위 굴리는 함수
def dice(min_number=1, max_number=6):
  dice = random.randint(min_number, max_number)
  print(dice)
  return dice


```
- [x] 5.코드가 간결한가요?
  > 함수화 및 클래스화 해서 코드를 작성해주셔서 코드가 간결하게 잘 읽힙니다.
```Python
 class player():
  def __init__(self):
    self.pos = 0   # 현재 위치 메모리

  def roll_dice(self):
      # 현재위치에서 주사위 만큼 이동하는 함수 
    print(self.pos)
    self.pos += dice()
```


# 참고 링크 및 코드 개선
```python
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# _tkinter.TclError: no display name and no $DISPLAY environment variable 에러 해결
# https://fishpoint.tistory.com/5556

# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
