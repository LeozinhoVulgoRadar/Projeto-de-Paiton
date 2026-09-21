# World Invaders

**Feito por:**
* Abner G.
* Leonardo S. Cipriano

**Tema:**
Um jogo inspirado no clássico Space Invaders, mantendo as mesmas mecânicas e objetivos originais rs.

---

## Objetivo do Jogo
Atingir o alvo com seu projétil antes que elas consigam avançar e alcançar a linha limite do jogador.

## Como Jogar
* Seta para a Esquerda / Direita: Movimenta a nave do jogador.
* Barra de Espaço: Dispara os "projéteis" contra os alvos.

---

## Funcionamento do Sistema

O jogo integra a biblioteca Pygame para renderizar gráficos em tempo real, gerenciar eventos do teclado e controlar a física do loop principal.

* Interface e Visual: Define uma janela de jogo com dimensões de 800x600 pixels e taxa de quadros limitada a 60 FPS (via pygame.time.Clock). O sistema carrega os elementos gráficos a partir de arquivos externos para o jogador, tiros, naves inimigas e o ícone da janela.
* Mecânicas do Jogador: A nave possui movimentação horizontal limitada pelas bordas laterais da tela (entre as posições X 0 e 736), impedindo que o jogador saia do cenário. O disparo utiliza uma máquina de estados simples (ready e fire) para garantir que apenas um projétil seja disparado por vez.
* Alvos e Inteligência Artificial: São gerados 6 inimigos simultâneos em posições horizontais e verticais aleatórias. Eles se movem horizontalmente e, sempre que colidem com as paredes laterais da janela, invertem o sentido do movimento e descem 40 pixels em direção ao jogador.
* Sistema de Colisão: O código utiliza a fórmula de distância euclidiana via teorema de Pitágoras (math.sqrt e math.pow) para calcular a aproximação exata entre o projétil e os inimigos. Caso a distância seja menor que 27 pixels, a colisão é confirmada, o inimigo ressurge no topo da tela e a pontuação aumenta.
* Fim de Jogo: Caso qualquer uma das naves inimigas ultrapasse a coordenada vertical limite de 440 pixels, todos os inimigos são movidos para fora do mapa, a tela exibe a mensagem de derrota e a execução é encerrada.

---

## Pré-requisitos e Instalação

Para rodar este projeto localmente, você precisa ter o Python instalado e a biblioteca pygame.

1. Instale o Pygame:
   python -m pip install pygame-ce

   O comando pip sozinho não estava mapeado nas Variáveis de Ambiente do seu sistema operacional, então utilizamos esse comando.

3. Organização dos Arquivos:
   Certifique-se de que os arquivos de imagem do projeto estejam na mesma pasta do arquivo de código.

4. Execução:
   Execute o script principal via terminal:
   python main.py


## 67
