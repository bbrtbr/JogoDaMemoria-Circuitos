# Jogo Da Memória - Circuitos
<p>O jogo da memória 4x4 é uma atividade clássica e divertida que desafia a memória e a concentração dos jogadores. Com uma grade de 4x4, o tabuleiro é composto por 16 displays virados para baixo, organizados em 4 linhas e 4 colunas. Cada display possui um número, que se repete em outro display. O objetivo é encontrar os pares, virando dois displays de cada vez e tentando lembrar onde cada número está posicionado.</p>


# Main
![image](https://github.com/user-attachments/assets/144df2d4-cf3e-4238-86e2-93ae2e13b1af)

Nos botões de linha e coluna é possível alternar as linhas e colunas nas quais o jogador deseja revelar o número, e o botão confirmar é possível realizar a tentiva.
Em cada display contém um LED, sinalizando qual coluna e linha está selecionada.

No circuito na parte inferior temos dois circuitos, no qual o primeiro é o controle de linha e coluna, que recebe como parâmetro os botões de linha e coluna, por meio de um túnel.
E também o circuito Mux_rev, que manipula os 16 displays.

# Control_L_C
![image](https://github.com/user-attachments/assets/fa81608b-263a-4005-9ba1-a8227a4daa45)

Esse circuito recebe os pulsos de linhas e colunas, nas quais passam por um incrementador, para alterar a linha e coluna.

# Incrementa ( CONTROL_L_C)
![image](https://github.com/user-attachments/assets/d1d08268-bace-4649-a908-4e411f116e0d)

Um incrementador feito com dois flip-flop, tipo d, nas quais recebem o pulso, passa por outro incrementador, e dessa forma adiciona mais um ao resultado final, indo de 0 a 3, depois reseta, alternando entre as 4 linhas, ou as 4 colunas.

# Incrementador (Incrementa)
![image](https://github.com/user-attachments/assets/4009e695-3f88-4146-b5c3-609395f7745f)

Consiste em um contador, que dependendo da entrada, a saída será o número adiante.

# Mux-rev
![image](https://github.com/user-attachments/assets/7cbe04de-b79e-46c1-8e92-94fb347adb77)

Nesse circuito temos o sistema do botão de confirmar, que irá revelar o número, e comparar, resetar e trocar o jogador.

![image](https://github.com/user-attachments/assets/fde93046-2200-4644-9585-4062f14c0bf1)

E temos o sistema de cada visor, no qual verifica se o número já foi "acertado", caso for acertado ele sempre irá manter aceso, ou irá resetar e voltar ao estado inicial, e isso será verificado quando o botão de confirmar for apertado.

![image](https://github.com/user-attachments/assets/4d21844e-b4c5-4980-85be-0f21bd845378)

Na parte superior temos o sistema que verifica se os dois números selecionados são iguais, que é um AND, que quando ambos forem acionados, irá modificar o valor de "Certo_x".

![image](https://github.com/user-attachments/assets/158b25d2-6b07-46fa-88b0-2680367c0ab0)

Na parte superior direito determinamos os valores de V1,V2,...,V8.

![image](https://github.com/user-attachments/assets/f99c1ed6-66b2-4e8f-864f-3d08dd4c8ee2)

Na parte inferior direita, temos o sistema de pontuação, que tem como entrada os valores de Certo_x, e qual o jogador que pontuou (que depende do botão de confirmar), e o contador da pontuação, controlado pelo circuito (Pont).

![image](https://github.com/user-attachments/assets/18f6a23c-47b7-4944-b54b-52fd78d1d393)

# Pont
![image](https://github.com/user-attachments/assets/e15f7410-bc30-4847-b4ab-e3bf5645fff6)

Um circuito que recebe o valor de Certo_x, e irá pontuar, mas caso já o valor de certo_x já tenha sido pontuado, não irá fornercer pontuação para o jogador novamente, manipulado por flipflop.

# Inc_pont
![image](https://github.com/user-attachments/assets/4a7de5ba-0a1a-4dd1-8b0f-0b04c0ee96b0)

Circuito de incrementador da pontuação, segue a mesma lógica do incrementa, só que com 4 bits.

![image](https://github.com/user-attachments/assets/891bdf76-0d10-4248-b5b4-15afbf720c97)


