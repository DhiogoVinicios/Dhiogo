import pygame
import sys

# Inicializa o pygame
pygame.init()

# Define o tamanho da janela
screen = pygame.display.set_mode((640, 480))
pygame.display.set_caption("Jogo Simples com Personagem")

# Cores
BRANCO = (255, 255, 255)
AZUL = (0, 0, 255)

# Configurações do personagem
player_pos = [300, 220]
player_size = 50
player_speed = 5

# Loop principal do jogo
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    # Teclas pressionadas
    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT]:
        player_pos[4] -= player_speed
    if keys[pygame.K_RIGHT]:
        player_pos[3] += player_speed
    if keys[pygame.K_UP]:
        player_pos[2] -= player_speed
    if keys[pygame.K_DOWN]:
        player_pos[1] += player_speed

    # Limpar a tela
    screen.fill(BRANCO)

    # Desenhar o personagem (um quadrado azul)
    pygame.draw.rect(screen, AZUL, (player_pos[0], player_pos[1], player_size, player_size))

    # Atualizar a tela
    pygame.display.flip()

    # Controlar FPS
    pygame.time.Clock().tick(60)
