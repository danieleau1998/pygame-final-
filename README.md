# pygame-final-
proyecto final pygame
import pygame
from pygame.locals import *
import time

 
pygame.init()


 
pantalla = pygame.display.set_mode((800,600),0,32)


king = pygame.image.load("don.png")
x1 = 100
y2 = 25
imagen = pygame.image.load("m1.png")
x = 0
y = 555
princesa = pygame.image.load("princesa.png")
x9 = 500
y9 = 50

escaleras = pygame.image.load("escalera.png")
x3 = 500
y3 = 510
escalera = pygame.image.load("escalera.png")
x4 = 300


y4 = 310
escalerass = pygame.image.load("escalera.png")
x5 = 550
y5 = 210
escaler = pygame.image.load("escalera.png")
x6 = 200
y6 = 110
sprite2 = pygame.sprite.Sprite()
sprite2.image = king
sprite2.rect = imagen.get_rect()



sprite1 = pygame.sprite.Sprite()
sprite1.image = imagen
sprite1.rect = imagen.get_rect()
 
sprite1.rect.top = y
sprite1.rect.left = x
 

sprite2.rect.top = y2
sprite2.rect.left = x1
 
rectangulo = pygame.Rect(0, 400, 700, 10)
linea = pygame.Rect(100, 500, 800, 10)
jojo = pygame.Rect(0, 590, 800, 50)
hu = pygame.Rect(100, 300, 700, 10)
dd = pygame.Rect(0, 200, 700, 10)
ko = pygame.Rect(100, 100, 500, 10)


reloj = pygame.time.Clock()
while True:
    for eventos in pygame.event.get():
        if eventos.type == pygame.QUIT:
            exit()
            
    pulsada = pygame.key.get_pressed()
    if pulsada[K_UP]:
        sprite1.rect.top -= 5
    if pulsada[K_DOWN]:
        sprite1.rect.top += 5
    if pulsada[K_LEFT]:
        sprite1.rect.left -= 5
    if pulsada[K_RIGHT]:
        sprite1.rect.left += 5
    if rectangulo.colliderect(sprite1):
        sprite1.rect.left = oldx
        sprite1.rect.top = oldy
    if linea.colliderect(sprite1):
        sprite1.rect.left = oldx
        sprite1.rect.top = oldy
    if jojo.colliderect(sprite1):
        sprite1.rect.left = oldx
        sprite1.rect.top = oldy
    if dd.colliderect(sprite1):
        sprite1.rect.left = oldx
        sprite1.rect.top = oldy
    if hu.colliderect(sprite1):
        sprite1.rect.left = oldx
        sprite1.rect.top = oldy
    if pulsada[K_w]:
        sprite2.rect.top -= 5
    if pulsada[K_s]:
        sprite2.rect.top += 5
    if pulsada[K_a]:
        sprite2.rect.left -= 5
    if pulsada[K_d]:
        sprite2.rect.left += 5
        
    print(pygame.time.get_ticks()/1000)

        
    
    oldx1 = sprite2.rect.left
    oldy2 = sprite2.rect.top 
    oldx = sprite1.rect.left
    oldy = sprite1.rect.top
    reloj.tick(50)

    pantalla.fill((0,0,0))
    pantalla.blit(sprite1.image, sprite1.rect)
    pantalla.blit(sprite2.image, sprite2.rect)
    pantalla.blit(escaleras, (x3, y3))
    pantalla.blit(princesa, (x9, y9))
    pantalla.blit(escalera, (x4, y4))
    pantalla.blit(escalerass, (x5, y5))
    pantalla.blit(escaler, (x6, y6))
    pygame.draw.rect(pantalla, (255, 0, 0), rectangulo )
    pygame.draw.rect(pantalla, (255, 0, 0), linea )
    pygame.draw.rect(pantalla, (255, 0, 0), jojo )
    pygame.draw.rect(pantalla, (255, 0, 0), hu )
    pygame.draw.rect(pantalla, (255, 0, 0), dd )
    pygame.draw.rect(pantalla, (255, 0, 0), ko )
    pygame.display.update()



   
                

pygame.quit()
