# 기상청 기상 시간자료 시각화  
  
...  
# Python3 샘플 코드  
# 서비스키에 디코딩키 복사하여 붙여넣기  
  
import requests  
  
url = 'http://apis.data.go.kr/1360000/AsosHourlyInfoService/getWthrDataList'  
para ={'serviceKey' : '서비스키', 'pageNo' : '1', 'numOfRows' : '990', 'dataType' : 'JSON', 'dataCd' : 'ASOS', 'dateCd' : 'HR', 'startDt' : '20100101', 'startHh' : '01', 'endDt' : '20100601', 'endHh' : '01', 'stnIds' : '108' }  
  
res = requests.get(url, params=para)  
print(res.content)  
...
  
...  
import json  
json_file = json.loads(res.text)  
...
  
...  
import pandas as pd  
from pandas import json_normalize  
  

df = json_normalize(json_file['response']['body']['items']['item'])  
df  
...
  
# 한글 폰트 설치  
  
...  
!sudo apt-get install -y fonts-nanum  
!sudo fc-cache -fv  
!rm ~/.cache/matplotlib -rf  
...
  
...  
# 폰트 갯수 확인  
import matplotlib.font_manager as fm  
  
sys_font=fm.findSystemFonts()  
print(f"sys_font number: {len(sys_font)}")  
print(sys_font)  
  
nanum_font = [f for f in sys_font if 'Nanum' in f]                              
print(f"nanum_font number: {len(nanum_font)}")  
nanum_font  
...
  
# 시각화  
  
...  
# 한글 1  
import matplotlib as mpl  
import matplotlib.pyplot as plt  
import matplotlib.font_manager as fm # 폰트 관련 용도  
  
plt.rc('font', family='NanumGothic')  
mpl.rcParams['axes.unicode_minus'] = False  
  
df['tm'] = pd.to_datetime(df['tm'])  
df['ts'] = pd.to_numeric(df['ts'], downcast='float')  
fig = plt.figure(figsize=(14,6))  
  
ax = plt.subplot(1,1,1)  
ax.plot(df['tm'],df['ts'],color='r',lw=1.5, alpha=0.7)  
  
ax.set_ylabel('Surface Temperature', fontweight='bold', fontsize=12)  
ax.set_xlabel('Date 일자', fontweight='bold', fontsize=12)  
ax.set_title('OPEN API ASOS 온도 데이터', fontweight='bold', fontsize=14)  
...
  
...  
# 한글 2  
import matplotlib.pyplot as plt  
  
# 한글 폰트 사용을 위해서 세팅  
from matplotlib import font_manager, rc  
font_path = "/usr/share/fonts/truetype/nanum/NanumGothic.ttf"  
font = font_manager.FontProperties(fname=font_path).get_name()  
rc('font', family=font)  
  
df['tm'] = pd.to_datetime(df['tm'])  
df['ts'] = pd.to_numeric(df['ts'], downcast='float')  
fig = plt.figure(figsize=(14,6))  
  
ax = plt.subplot(1,1,1)  
ax.plot(df['tm'],df['ts'],color='r',lw=1.5, alpha=0.7)  
  
ax.set_ylabel('Surface Temperature', fontweight='bold', fontsize=12)  
ax.set_xlabel('Date 일자', fontweight='bold', fontsize=12)  
ax.set_title('OPEN API ASOS 온도 데이터', fontweight='bold', fontsize=14)  
...
  
...  
df['ta'] = pd.to_numeric(df['ta'], downcast='float')  
fig = plt.figure(figsize=(14,6))  
  
ax = plt.subplot(1,1,1)  
ax.plot(df['tm'],df['ts'],color='b',lw=1.5, alpha=0.7)  
  
ax.set_ylabel('Surface Temperature', fontweight='bold', fontsize=12)  
ax.set_xlabel('Date 일자', fontweight='bold', fontsize=12)  
ax.set_title('OPEN API ASOS 온도 데이터', fontweight='bold', fontsize=14)  
...
  
...  
fig = plt.figure(figsize=(14,6))  
ax = fig.add_subplot(1, 1, 1)  
  
ax.plot(df['tm'],df['ts'],color='b', lw=1.5, alpha=0.8, label= 'Surface Temperature')  
ax.plot(df['tm'],df['ta'],color='r', lw=1.5, alpha=0.8, label= 'Air Temperature')  
ax.legend()  
plt.show()  
...
  

...  
# 파일로 저장  
df.to_excel("output.xlsx")  
df.to_csv("output.csv")  
...
  
# 1인용 핑퐁 게임 만들기

...  
import pygame  
from pygame.locals import *  
  
# 게임 화면 설정  
WIDTH = 640  
HEIGHT = 480  
BALL_RADIUS = 10  
PADDLE_WIDTH = 60  
PADDLE_HEIGHT = 10  
FPS = 60  
  
# 색깔 정의  
BLACK = (0, 0, 0)  
WHITE = (255, 255, 255)  
  
# 초기화  
pygame.init()  
screen = pygame.display.set_mode((WIDTH, HEIGHT))  
clock = pygame.time.Clock()  
  
# 공 객체 생성  
ball = pygame.Rect(WIDTH // 2 - BALL_RADIUS, HEIGHT // 2 - BALL_RADIUS, BALL_RADIUS * 2, BALL_RADIUS * 2)  
ball_speed_x = 3  
ball_speed_y = 3  
  
# 패들 객체 생성  
paddle = pygame.Rect(WIDTH // 2 - PADDLE_WIDTH // 2, HEIGHT - PADDLE_HEIGHT - 10, PADDLE_WIDTH, PADDLE_HEIGHT)  
  
# 점수 변수  
score = 0  
font = pygame.font.Font(None, 36)  
  
# 기회 횟수  
chances = 3  
  
# 게임 루프  
running = True  
game_over = False  
while running:  
    for event in pygame.event.get():  
        if event.type == QUIT:  
            running = False  
  
    if not game_over:  
        # 패들 이동 처리  
        mouse_x = pygame.mouse.get_pos()[0]  
        paddle.x = mouse_x - PADDLE_WIDTH // 2  
  
        # 공 이동 처리  
        ball.x += ball_speed_x  
        ball.y += ball_speed_y  
  
        # 벽과 충돌 감지  
        if ball.left <= 0 or ball.right >= WIDTH:  
            ball_speed_x *= -1  
        if ball.top <= 0:  
            ball_speed_y *= -1  
        if ball.bottom >= HEIGHT:  
            chances -= 1  
            if chances <= 0:  
                # 게임 오버 처리  
                game_over = True  
            else:  
                # 게임 재시작  
                ball.center = (WIDTH // 2, HEIGHT // 2)  
                ball_speed_x *= -1  
                ball_speed_y *= -1  
  
        if ball.colliderect(paddle):  
            ball_speed_y *= -1  
            score += 10  
  
    # 점수 업데이트  
    score_text = font.render("Score: " + str(score), True, WHITE)  
    chances_text = font.render("Chances: " + str(chances), True, WHITE)  
  
    # 화면 업데이트  
    screen.fill(BLACK)  
    pygame.draw.ellipse(screen, WHITE, ball)  
    pygame.draw.rect(screen, WHITE, paddle)  
    screen.blit(score_text, (10, 10))  
    screen.blit(chances_text, (10, 50))  
  
    if game_over:  
        game_over_text = font.render("Game Over", True, WHITE) 
        screen.blit(game_over_text, (WIDTH // 2 - game_over_text.get_width() // 2, HEIGHT // 2 - game_over_text.get_height() // 2))  
  
    pygame.display.flip()  
    clock.tick(FPS)  
  
# 게임 종료  
pygame.quit()  
...
