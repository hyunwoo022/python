import pygame  
from pygame.locals import *  
import time  
import sys  
  
# 게임 화면 크기  
SCREEN_WIDTH = 320  
SCREEN_HEIGHT = 480  
  
# 색깔 정의  
BLACK = (0, 0, 0)  
WHITE = (255, 255, 255)  
  
# 패들 크기  
PADDLE_WIDTH = 60  
PADDLE_HEIGHT = 15  
PADDLE_SPEED = 5  
  
# 공 크기  
BALL_WIDTH = 10  
BALL_HEIGHT = 10  
BALL_SPEED_X = 3  
BALL_SPEED_Y = 3  
  
def main():  
    pygame.init()  
    screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))  
    pygame.display.set_caption("Ping Pong Game")  
  
    clock = pygame.time.Clock()  
  
    # 패들 초기 위치  
    player_paddle = pygame.Rect(SCREEN_WIDTH // 2 - PADDLE_WIDTH // 2, SCREEN_HEIGHT - PADDLE_HEIGHT, PADDLE_WIDTH, PADDLE_HEIGHT)  
  
    # 공 초기 위치 및 속도  
    ball = pygame.Rect(SCREEN_WIDTH // 2 - BALL_WIDTH // 2, SCREEN_HEIGHT // 2 - BALL_HEIGHT // 2, BALL_WIDTH, BALL_HEIGHT)  
    ball_speed_x = BALL_SPEED_X  
    ball_speed_y = BALL_SPEED_Y  
  
    # 게임 변수 초기화  
    score = 0  
    play_count = 3  
  
    while play_count > 0:  
        for event in pygame.event.get():  
            if event.type == QUIT:  
                pygame.quit()  
                sys.exit()  
  
        keys = pygame.key.get_pressed()  
        if keys[K_LEFT] and player_paddle.x > 0:  
            player_paddle.x -= PADDLE_SPEED  
        if keys[K_RIGHT] and player_paddle.x < SCREEN_WIDTH - PADDLE_WIDTH:  
            player_paddle.x += PADDLE_SPEED  
  
        ball.x += ball_speed_x  
        ball.y += ball_speed_y  
  
        # 공과 패들 충돌 감지  
        if ball.colliderect(player_paddle):  
            ball_speed_y *= -1  
            score += 1  
  
        # 벽과 공 충돌 감지  
        if ball.left < 0 or ball.right > SCREEN_WIDTH:  
            ball_speed_x *= -1  
        if ball.top < 0 or ball.bottom > SCREEN_HEIGHT:  
            ball_speed_y *= -1  
  
        # 화면 업데이트  
        screen.fill(BLACK)  
        pygame.draw.rect(screen, WHITE, player_paddle)  
        pygame.draw.ellipse(screen, WHITE, ball)  
  
        # 점수 표시  
        font = pygame.font.Font(None, 36)  
        text = font.render("Score: " + str(score * 10), True, WHITE)  
        screen.blit(text, (10, 10))  
  
        # 플레이 횟수 표시  
        play_count_text = font.render("Play Count: " + str(play_count), True, WHITE)  
        screen.blit(play_count_text, (10, 50))  
  
        pygame.display.flip()  
   
        clock.tick(60)  
  
        # 플레이 횟수 체크 및 게임 종료 
        if ball.bottom > SCREEN_HEIGHT:  
            play_count -= 1  
            if play_count > 0:  
                ball.x = SCREEN_WIDTH // 2 - BALL_WIDTH // 2  
                ball.y = SCREEN_HEIGHT // 2 - BALL_HEIGHT // 2  
                ball_speed_y *= -1  
                pygame.time.wait(1000)  # 1초 동안 대기  
            else:  
                pygame.time.wait(3000)  # 3초 동안 대기 (게임 종료 시간)  
                print("Game Over")  
  
if __name__ == "__main__":  
    main()  
