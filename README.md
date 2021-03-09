# War-Card-Game
Pygame/Python, unfinished

import pygame
pygame.init() #initializes pygame
print(pygame.font.get_fonts()) 

screen=pygame.display.set_mode((700,500))#creates game screen
pygame.display.set_caption("Card game: War") #sets the window title
doExit = False #variable to quit game loop
clock= pygame.time.Clock()#timer for game 

class Card:
  def __init__(self, suit, number):
    self.suit= suit
    self.number= number 
  def draw(self, x, y):
    pygame.draw.rect(screen,(255,255,255), (x, y, 100, 180))#white rectangle
    pygame.draw.rect(screen,(0,0,0),(x,y,100,180),3)#outline
    font=pygame.font.Font('freesansbold.ttf', 24)
    text1= font.render(str(self.number), 1, (0,0,0))
    text2= font.render(str(self.suit),1,(250, 0,0))
    screen.blit(text1, (x+30 ,y+30))
    screen.blit(text2, (x+10, y+60))

c1= Card(10,10)
c2= Card(20,20)
c3= Card(30,30)

Deck= list()
for j in range (4):
  
#######game loop########
while not doExit:
  clock.tick(60)#FPS 
 

###render section  
  screen.fill((0,150,0))#screen color

  c1.draw(250,100)
  c2.draw(100,200)
  c3.draw(400,200)
  
  #update the screen
  pygame.display.flip()

pygame.quit()#closes game completely
