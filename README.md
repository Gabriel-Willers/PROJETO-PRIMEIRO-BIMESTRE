Esse é o README dos alunos: Juan Pablo Correa e Gabriel Willers Teixeira; da turma EC1MA, referente ao PROJETO 1° BIMESTRE.

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




Agora, iremos comentar um pouco sobre nosso menu de seleção dos jogos e algumas das variáveis. O "char start" é uma variável de condição para o início do jogo das perguntas. O "char alt" serve para classificar as alternativas A, B, C e D, também do jogo 1. O "int p=0" é usado na contagem de pontos do jogo 1, somando 1 ponto(p++) a cada acerto. O "char fim" é usado para o caso de retorno ao menu ao finalizar o primeiro jogo. O "Int Cai[]" é um vetor onde cada valor de cada Cai é apeans para declarar a randomização dos valores das caixas do jogo 2. Cada vetor de Cai[] guarda um valor que irá ser definido durante a randomização dos númenos para o jogo dois. Assim dentro de uma unica variável, podemos guardar valores diferentes que poderão ser acessados sepadaramentes. A variável "int roda=0" é responsável por prosseguir as perguntas no jogo 1 e pelo while principal dele. As "string jogada" e "string jogada2" são para definir a escolha de cada jogador no jogo 3, então para o jogador dois será "jogada" e para o 2 "jogada2". Os "int gou1,gou2,gou11,gou22" são variáveis de ligação a cada jogador no jogo 3, entao as primeiras duas para cada gousma do jogador 1 e as outras duas para o jogador 2. O int "Part" e "Resul" são respectivamente a vez de cada jogador no jogo 3 e o resultado dos pontos "p" nos jogos 1 e 3. O "int Restart=1" e "Esc" são os responsáveis pelo direcionamento do jogo, o Restart sendo == 1, como é no padrão, já nos leva diretamente para o menu de seleção de jogos, nele, temos a opção de escolher entre 3 jogos ou sair do menu (o que fecharia o programa), com base na sua escolha, voce será direcionado a um enorme switch case, este que com um scanf para o Esc, será feita a escolha, e dos "cases" no switch case, em cada switch case, exceto no 1 pois foi feito sem o uso das variáveis padrão, serão usados diferentes valores de restart para definir o while de cada jogo, sendo "restart == 2" para jogo 2, 3 para o jogo 3 e 0 para finalizar o programa.

Sabendo disso, após a seleção do jogo, será apresentada uma mensagem "INICIANDO" com o comando "Sleep(200)", da biblioteca time.h, este que define por milissegundo o tempo de cada coisa. Após isso, o jogo de escolha irá rodar normalmente.

![image](https://github.com/user-attachments/assets/ceb12925-b65d-405e-8731-f59861704c54)





Agora que já temos uma ideia de como funcionam algumas coisas para que o programa se inicie e funciona, iremos começar a explicar os jogos: 

O jogo 1, que é de perguntas e respostas, é bem simples. Após sua seleção no menu, é explicado do que se trata o o jogo, logo em seguida a opção de se você deseja iniciar o jogo ou não (S ou N), com o "cin" (do iostream) como dispositivo de entrada da opção, verifica o valor da variável e classifica se é ou não inválida, se for, você irá entrar em um "Do While", este que irá continuar até que selecione alguma entrada válida; se for válida (Sim(S) ou Não(N)), se sim, você entra no no loop "roda!=0" e o jogo começa, se não, volta ao menu. Após o início do jogo, e o "cls" já tendo limpado as mensagens anteriores, você terá 4 alternativas para cada pergunta, e você poderá fazer sua escolha (alt) com entradas de a-d e A-D (com um scanf), as quais se você utilizar alguma entrada inválida, como "T", o programa solicitará que refaça sua escolha até que ele aceite a entrada; logo em seguida, após a verificação da entrada, se acertar, lhe será apresentado que acertou e você somará 1 ponto, se errar, será apresentada a alternativa correta e você não somará pontos, após isso, será trocado o valor de "roda" a cada fim de pergunta, com resposta certa ou errada. Tendo completado todas as perguntas, será printado no console seu placar de pontos e a mensagem de conclusão do jogo, após isso, será exposta a opção de reiniciar o jogo ou voltar para o menu, onde como nos demais loops, se você entrar com alguma variável inválida, será repetida a opção de escolha até o contrário.


![image](https://github.com/user-attachments/assets/bb9db760-d109-41fb-a2ae-f904bfad066b)
![image](https://github.com/user-attachments/assets/b70b88e1-9003-43b9-b0f0-9a3070c7c07b)

O jogo 2, que é Cobra na Caixa, usa rand() para embaralhar o valor de Cai[], que vai guardar cinco valores diferentes referentes ao valor de status de cada uma das cinco caixas, depois esses valores serão verifivados e reembaralhados caso algum valor se repita em caixas diferentes. Esses valores vão de 1 a 5, e representam o esdado de cada caixa, sendo, as caixas que receberem o valor de 3, 4 e 5, serão as caixas vazias, 1 quando está com a cobra, e 2 quando está com o botão. Esses números não serão exibidos para os jogadores durante a partida e também não se relacionam com a ordem das caixas. Logo depois, vem os primeiros códigos relacionados com a interação com o jogador, que é o switch case, que neste primeiro momento será usado para permitir que o jogador escolha o nome de seu personagem. O comando strcpy() é usado para gravar o nome escolhido nos status do jogador. Depois que os dois jogadores esclherem os seus personagens, o sistema irá sortear um valor entre 0 e 1 e salvará na variável Ver que será importante neste momento em que o jogo entrará em dois while{}, o primeiro é importante para verificar se o jogo ainda não acabou, que funcionará enquanto Ver for 0 ou 1, o segundo roda a jogada do jogador sorteado, sendo Ver=0 para iniciar com primeiro jogador e Ver=1 para começar com o segundo.O jogo começará mostrando cinco caixinhas enumeradas de 1 à 5, esses valores são apenas representativos e não interferem no estado de cada caixa, apenas sinalizando quando elas já foram escolhidas quando o valor mostrado é zero. Para o jogador escolher uma das caixas, ele deverá digitar o valor referente da caixa. Quando ocorrer o input desse valor, ele será lido pelo switch case, que irá zerar esse valor para sinalizar que a caixa foi escolhida, depois o sistema verificará o valor referente a caixa no vetor Cai[], e logo em seguida gera o resultado, prosseguindo a partida ou finalizando depedendo do valor de Cai[] referente. Caso o valor de Cai[] exija que o jogo continue, Ver será alterado para a vez do jogador seguinte, dando sequência ao jogo, e caso Cai[] exija que o jogo pare, Ver será alterado para 3,6,2 ou 4, saindo do while principal e finalizando o jogo dando a opção de reiniciar a partida e de voltar ao menu inicial. Os valores 3,6,2 e 4 do Ver são referente a como o jogo deve reagir com cada situação de finalização do jogo, com 3 e 6 sendo responsáveis para definir o jogador 1 como vencedor e 2 e 4 para o jogador 2 como vencedor. Os valores também darão mais detalhes sobre a condição de virória, 2 para dizer que o segundo ganhou porque escolheu a caixa com o botão, 3 para dizer que o primeiro ganhou porque o segundo escolheu a caixa com a cobra, 4 para dizer que o segundo ganhou porque o primeiro escolheu a caixa com a cobra e 6 para dizer que o primeiro ganhou porque escolheu a caixa com o botão, e todas essas informações aparecerão no fim do jogo para os jogadores. Caso a escolha do jogador para interagir seja inválida (se a caixa escolhida já tiver sido aberta ou o input não corresponda com os comandos do jogo), o valor de Ver não alterará, dando a oportunidade do jogador fazer outra escolha. 

![image](https://github.com/user-attachments/assets/d099d431-6819-4597-a662-a9c62613ebe7)

![image](https://github.com/user-attachments/assets/a12fb351-d365-4c06-8e7c-2d7725bb7d9d)

![image](https://github.com/user-attachments/assets/d7705b24-ec3d-4b3a-8104-91cb4af47913)

Falando agora do último jogo, nós o iniciamos com um texto explicando os comandos do jogo, como LR, LL, RL etc, que tem como função definir qual gousma inimiga atacar e qual gousma fará a ação, sendo L (left>>>esquerda) e R(right>>>direita), também contamos com o comando de divisão de fúria para reviver ou redistribuir a fúria de suas gousmasa entre si. Após a introdução, o jogo começa com o jogador azul e alterna após cada jogada. Há as limitações como a impossibilidade de divisão e ataque de gousmas desintegradas e também não há como atacar com um gousma já derrotada, a não ser que ela seja revivida, além disso, se você tentar algum destes comandos não válidos, ou simplesmente utilizar qualquer tipo de entrada inválida, será apresentada uma mensagem dizendo que o comando é errado e dirá para tentar novamente. A interface das gousmas foi feita primordialmente sem system cls e sem os defines, então antes ela invertia a cada rodada respectiva a vez de cada jogador, porém, agora ela se mantém igual alterando apenas as cores referentes aos jogadores (vermelho para o jogador  2 e azul para o 1). Em questão de códigos, o Gousmas War tem um while{} principal, dentro dele terá um while que tem a única serventia de mostrar um texto contextualizando o jogo e que nunca mais aparecerá enquanto o usuário não sair do jogo. Os dois ultimos while são responsáveis para ditar a vez de cada jogador. Cada um desses while{} são definidos pela variável part, que guia cada jogada. A maior parte do sistema responsável pela interação com o jogador está dentro deste while que dita a vez de cada jogador, sendo usado cin>>jogada ou (cin>>jogada2 para o jogador 2) para permitir o input do usuário. A leitura deste imput é lido por uma rede de if else if que definem cada resposta equivalente para a jogada depedendo da situação do jogo. Quando um jogador faz uma jogada válida, o jogo executa seu comando e depois redefine part para permitir a vez do próximo jogador, caso a jogada seja inválida, part permanecerá com o mesmo valor, deixando o jogador escolher uma outra jogada. Comandos referentes ao ataque de Gousmas funcionam atribuindo a soma do seu valor com o valor da gousma atacada à essa gousma atacada. Comandos referentes à divisão de gousma funciona subtraindo o valor de uma unidade da gousma que irá doar, e soma um para a gousma que receberá. A interface tem cores diferentes para ser mais visual para os jogadores de quando será a sua vez e quais são suas gousmas, e essas cores são geradas pelos defines que reduziram os códigos referentes para palavras mais curtas. Esses códigos tem a capacidade de mudar a cor do texto e do fundo do texto de tudo que será gerado abaixo desta linha, por isso foi necessário criar também uma variável do código para voltar as cores de texto e fundo para padrão. Quando um dos jogadores perdem as suas duas gousmas, part é definido para um valor que não sejá referente ao while de nenhum dos dois jogadores, retornando ao while principal do jogo, um valor será definido para a variável Resul que imprimirá o resultado da partida para os jogadores, e logo em seguida, dará a opção de sair do jogo ou reiniciar a partida, ao qual retornará todos os valores do jogo para o padrão para dar inicio à uma nova partida.


![image](https://github.com/user-attachments/assets/141e7fd0-cf31-418e-a75e-a03d10b262af)


![image](https://github.com/user-attachments/assets/d6fe7076-5903-4dc9-9951-3cf5cf7f9de0)


![image](https://github.com/user-attachments/assets/495a9cc8-5d85-4db1-981d-d1a72a42b383)








Referências:
Usado para mudar a cor dos textos:
https://youtu.be/Hl-7xMl7bn0?si=6n4UkFvXkU-FCgLi
https://pt.stackoverflow.com/questions/68872/c-mudar-cor-de-letras-v%C3%A1rias-cores-em-uma-s%C3%B3-tela

Usado para entender as funcionalidades de Sleep() e system("cls") e suas respectivas bibliotecas:
https://www.ufsm.br/pet/sistemas-de-informacao/2020/03/10/melhorando-suas-aplicacoes-em-c

Uso de vetores:
Aprendido no projeto Feynman.

Uso da biblioteca conio.h e o código getch():
https://pt.stackoverflow.com/questions/254652/qual-%C3%A9-a-fun%C3%A7%C3%A3o-do-getch-e-da-biblioteca-conio-h e aulas da monitoria.
