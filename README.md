# Pygame
Inicio de aprendizagem sobre jogos em python.
Vamos analisar o código passo a passo e explicar o que cada linha faz em português:

```python
import pygame
pygame.init()
```

1. **Importando pygame:**
   - `import pygame`: Esta linha importa a biblioteca pygame, que nos fornece ferramentas para criar jogos em Python.
   - `pygame.init()`: Esta linha inicializa a biblioteca pygame, preparando-a para ser utilizada no nosso código.

```python
# Criando a tela
tela = pygame.display.set_mode((800,600))
```

2. **Criando a Tela do Jogo:**
   - `tela = pygame.display.set_mode((800,600))`: Esta linha cria a janela principal do nosso jogo, que será exibida na tela. Ela define a largura (800 pixels) e a altura (600 pixels) da janela.

```python
pygame.display.set_caption("a bola")
```

3. **Definindo o Título da Janela:**
   - `pygame.display.set_caption("a bola")`: Esta linha define o título que aparecerá na barra de título da janela do jogo. No caso, definimos o título como "a bola".

```python
clock = pygame.time.Clock()
```

4. **Criando um Relógio:**
   - `clock = pygame.time.Clock()`: Esta linha cria um objeto `clock` do tipo `pygame.time.Clock`. Esse objeto será usado para controlar a taxa de atualização da tela do jogo, garantindo uma animação suave.

```python
clashed = False
```

5. **Variável para Condição de Saída:**
   - `clashed = False`: Esta linha cria uma variável booleana chamada `clashed` e atribui a ela o valor `False`. Essa variável será usada para controlar o loop principal do jogo. O loop continuará rodando enquanto `clashed` for `False`.

```python
while not clashed:
    for event in pygame.event.get():
          if event.type == pygame.QUIT:
              clashed = True

          print(event)
    pygame.display.update()
    clock.tick(60)
```

6. **Loop Principal do Jogo:**
   - `while not clashed:`: Esta linha inicia um loop `while` que continuará rodando enquanto a variável `clashed` for `False`. Esse loop é o coração do jogo, pois é nele que ocorre a atualização contínua da tela e o processamento de eventos.

      - **Processando Eventos:**
         - `for event in pygame.event.get()`: Este loop `for` itera sobre todos os eventos que ocorreram desde a última iteração do loop principal. Um evento pode ser, por exemplo, o clique do mouse, o pressionamento de uma tecla ou o fechamento da janela.
         - `if event.type == pygame.QUIT:`: Esta instrução condicional verifica se o tipo do evento é `pygame.QUIT`. O evento `pygame.QUIT` é gerado quando o usuário fecha a janela do jogo. Se essa condição for verdadeira, o valor da variável `clashed` é alterado para `True`, o que fará com que o loop principal seja encerrado na próxima iteração.
         - `print(event)`: Esta linha (opcional) imprime informações sobre o evento na janela do console. Pode ser útil para depuração do código.

      - **Atualizando a Tela:**
         - `pygame.display.update()`: Esta linha atualiza a tela do jogo, refletindo as alterações gráficas feitas desde a última atualização. Sem essa linha, as alterações gráficas não seriam visíveis na tela.

      - **Controlando a Taxa de Atualização:**
         - `clock.tick(60)`: Esta linha instrui o relógio (`clock`) a limitar a taxa de atualização da tela a 60 quadros por segundo (FPS). Isso garante que o jogo rode de forma suave e evita que ele fique lento ou rápido demais em computadores diferentes.

```python
pygame.quit()
quit()
```

7. **Finalizando o Jogo:**
   - `pygame.quit()`: Esta linha finaliza a biblioteca pygame, liberando os recursos que ela estava utilizando.
   - `quit()`: Esta linha (opcional) finaliza o programa Python.

Este código básico cria uma janela de jogo simples com o título "a bola". Ele implementa um loop principal que processa eventos (como o fechamento da janela) e atualiza a tela a cada iteração.
