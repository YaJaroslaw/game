import pygame as pg
import sys
import random as rnd

pg.init()
win = pg.display.set_mode((500, 500))
background = pg.image.load("system.png").convert()
#  Рекомендую использовать .convert(), иначе будет сильно лагать


class cam:
    def __init__(self, x, y):
        self.rect = pg.Rect(x, y, 500, 500)

    def move(self, vector):
        self.rect[0] += vector[0]
        self.rect[1] += vector[1]


class Player:
    def __init__(self, x, y):
        self.rect = pg.Rect(x, y, 10, 10)

    def move(self, vector):
        self.rect[0] += vector[0]
        self.rect[1] += vector[1]

    def draw(self):
        #  Игрок на самом окне не двигается, двигается мир вокруг него
        pg.draw.rect(win, (0, 0, 0), (240, 240, 10, 10))


camera = cam(0, 0)


class object:
    #  Это какой-нибудь объект, отличный игрока (к примеру враг или дерево)
    def __init__(self, x, y, width, height):
        self.rect = pg.Rect(x, y, width, height)

    def draw(self):
        #  Чтобы отрисовка соответствовала позиции объекта его нужно отрисовывать
        #  на self.rect[0]-camera.rect[0], self.rect[1]-camera.rect[1]
        pg.draw.rect(win, (255, 0, 0), (self.rect[0] - camera.rect[0], self.rect[1] - camera.rect[1], self.rect[2], self.rect[3]), 2)

# P.S. я указывал переменные rect для того, чтобы можно было проверять коллизию между
# объектами. К примеру: для увеличения производительности, в этой программе отрисовываются лишь те
# объекты, которые попадают в камеру. (Загугли pg.Rect.colliderect для большего)
