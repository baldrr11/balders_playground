# Velkommen til
import pygame
import random

# Initialize pygame
pygame.init()

# Game constants
SCREEN_WIDTH = 400
SCREEN_HEIGHT = 600
GRAVITY = 0.25
FLAP_STRENGTH = -7
PIPE_WIDTH = 60
PIPE_GAP = 150
BIRD_WIDTH = 40
BIRD_HEIGHT = 40
FPS = 60

# Set up the screen
screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))
pygame.display.set_caption("Flappy Bird")

# Load assets
bird_img = pygame.Surface((BIRD_WIDTH, BIRD_HEIGHT))
bird_img.fill((255, 255, 0))  # Yellow bird
font = pygame.font.SysFont(None, 36)

# Colors
WHITE = (255, 255, 255)
GREEN = (0, 255, 0)
BLACK = (0, 0, 0)

# Bird class
class Bird:
    def __init__(self):
        self.x = 50
        self.y = SCREEN_HEIGHT // 2
        self.vel = 0

    def update(self):
        self.vel += GRAVITY
        self.y += self.vel
        if self.y < 0:
            self.y = 0
        if self.y > SCREEN_HEIGHT - BIRD_HEIGHT:
            self.y = SCREEN_HEIGHT - BIRD_HEIGHT

    def flap(self):
 

