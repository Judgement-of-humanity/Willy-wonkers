import pygame, sys, time, random, colorsys, math
from pygame.math import Vector2
from pygame.locals import *


class Player:
    position = pygame.Vector2()
    position.xy = 295, 100
    velocity = pygame.Vector2()
    velocity.xy = 3, 0
    acceleration = 0.1
    rightSprite = pygame.image.load('data/gfx/player.png')
    leftSprite = pygame.transform.flip(rightSprite, True, False)
    currentSprite = rightSprite

class Background:
    def __init__(self):
        self.sprite = pygame.image.load('data/gfx/bg.png')
        self.position = 0
        self.uncoloredSprite = pygame.image.load('data/gfx/bg.png') 
    def setSprite(self, tint):  
        copy = self.uncoloredSprite.copy()
        color = colorsys.hsv_to_rgb(tint,1,1)
        copy.fill((color[0]*255, color[1]*255, color[2]*255), special_flags=pygame.BLEND_ADD)
        self.sprite = copy

class Button:
    def __init__(self):
        self.price = 3
        self.level = 1   
    sprite = pygame.image.load('data/gfx/button.png')
    typeIndicatorSprite = pygame.image.load('data/gfx/null_indicator.png')

class Bean: 
    def __init__(self):
        self.sprite = pygame.image.load('data/gfx/bean.png')
        self.position = pygame.Vector2()
        self.position.xy

def clamp(value, min, max):
    if value < min:
        return min
    if value > max:
        return max
    return value

def checkCollisions(a_x, a_y, a_width, a_height, b_x, b_y, b_width, b_height):
    return (a_x + a_width > b_x) and (a_x < b_x + b_width) and (a_y + a_height > b_y) and (a_y < b_y + b_height)


def main():
    pygame.init()
    
main()
