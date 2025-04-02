Este é o README dos alunos: Juan Pablo Correa e Gabriel Willers Teixeira; da turma EC1MA, referente ao PROJETO 1° BIMESTRE.

Vou começar explicando as bibliotecas. Como descrito na imagem, além do <stdio.h>, utilizamos:
- <conio.h> (responsável pela possibilidade de uso do comando getch() que nada mais é que usar de qualquer tecla como forma de prosseguir com algum coamndo, como "printf("\n[Pressione qualquer tecla para prosseguir]\n"); getch();";
- <iostream> (Esta que é a bliblioteca que permite o uso de comandos e recursos de C++);
- <stdlib.h> (É utilizado para comandos como "srand(time(NULL))" e "system("cls")", que servem para randomizar e para para limpar o console após a execução de determinados comandos;
- <windows.h> (É usado na personalização do console com cores tanto no texto como no fundo dele, usamos também como forma de distinguir a rodada de cada player no Gousmas War);
- <time.h> (Ele foi usado como complemento do <stdlib.h> para randomizar em função do tempo, ou seja, ele vai definir um tempo o qual vai randomizar os valores de determinadas variáveis.);
- <locale.h> (É a biblioteca que permite o uso de caracteres e acentuações em português.);
- <string.h> e using namespace std (Using namespace std serve para declarar strings de uma forma que "std::" não se faça necessário, juntamente a isso, a biblioteca <string.h> basicamente serve como antecedente de uma determinada variável com o o fim declará-la.);
-"#define" é o comando que nos permite acessar e inserir a biblioteca de cores do <windows.h>.

![image](https://github.com/user-attachments/assets/d0c50806-5617-4a1c-a4c2-aa52b20499e4)




Agora, iremos comentar um pouco sobre nosso menu de seleção dos jogos e algumas das variáveis. O "char start" é uma variável de condição para o início do jogo das perguntas. O "char alt" serve para classificar as alternativas A, B, C e D, também do jogo 1. O "int p=0" é usado na contagem de pontos do jogo 1, somando 1 ponto(p++) a cada acerto. O "char fim" é usado para o caso de retorno ao menu ao finalizar o primeiro jogo. 


O "Int Cai[]" é um vetor onde cada valor de cada Cai é apeans para declarar a randomização dos valores das caixas do jogo 2. JUAN EXPLICA PRA MIM PFF

A variável "int roda=0" é responsável por prosseguir as perguntas no jogo 1 e pelo while principal dele. As "string jogada" e "string jogada2" são para definir a escolha de cada jogador no jogo 3, então para o jogador dois será "jogada" e para o 2 "jogada2". Os "int gou1,gou2,gou11,gou22" são variáveis de ligação a cada jogador no jogo 3, entao as primeiras duas para cada gousma do jogador 1 e as outras duas para o jogador 2. O int "Part" e "Resul" são respectivamente a vez de cada jogador no jogo 3 e o resultado dos pontos "p" nos jogos 1 e 3. O "int Restart=1" e "Esc" são os responsáveis pelo direcionamento do jogo, o Restart sendo == 1, como é no padrão, já nos leva diretamente para o menu de seleção de jogos, nele, temos a opção de escolher entre 3 jogos ou sair do menu (o que fecharia o programa), com base na sua escolha, voce será direcionado a um enorme switch case, este que com um scanf para o Esc, será feita a escolha, e dos "cases" no switch case, em cada switch case, exceto no 1 pois foi feito sem o uso das variáveis padrão, serão usados diferentes valores de restart para definir o while de cada jogo, sendo "restart == 2" para jogo 2, 3 para o jogo 3 e 0 para finalizar o programa.

Sabendo disso, após a seleção do jogo, será apresentada uma mensagem "INICIANDO" com o comando "Sleep(200)", da biblioteca time.h, este que define por milissegundo o tempo de cada coisa. Após isso, o jogo de escolha irá rodar normalmente.

![image](https://github.com/user-attachments/assets/ceb12925-b65d-405e-8731-f59861704c54)





Agora que já temos uma ideia de como funcionam algumas coisas para que o programa se incicie e funciona, iremos começar a explicar os jogos, começando do 1: 
O jogo 1, que é de perguntas e respostas, é bem simples. Após sua seleção no menu, é explicado do que se trata o o jogo, logo em seguida a opção de se você deseja iniciar o jogo ou não (S ou N), com o "cin" (do iostream) como dispositivo de entrada da opção, verifica o valor da variável e classifica se é ou não inválida, se for, você irá entrar em um "Do While", este que irá continuar até que selecione alguma entrada válida; se for válida (Sim(S) ou Não(N)), se sim, você entra no no loop "roda!=0" e o jogo começa, se não, volta ao menu. Após o início do jogo, e o "cls" já tendo limpado as mensagens anteriores, você terá 4 alternativas para cada pergunta, e você poderá fazer sua escolha (alt) com entradas de a-d e A-D (com um scanf), as quais se você utilizar alguma entrada inválida, como "T", o programa solicitará que refaça sua escolha até que ele aceite a entrada; logo em seguida, após a verificação da entrada, se acertar, lhe será apresentado que acertou e você somará 1 ponto, se errar, será apresentada a alternativa correta e você não somará pontos, após isso, será trocado o valor de "roda" a cada fim de pergunta, com resposta certa ou errada. Tendo completado todas as perguntas, será printado no console seu placar de pontos e a mensagem de conclusão do jogo, após isso, será exposta a opção de reiniciar o jogo ou voltar para o menu, onde como nos demais loops, se você entrar com alguma variável inválida, será repetida a opção de escolha até o contrário.
![image](https://github.com/user-attachments/assets/bb9db760-d109-41fb-a2ae-f904bfad066b)
![image](https://github.com/user-attachments/assets/b70b88e1-9003-43b9-b0f0-9a3070c7c07b)




