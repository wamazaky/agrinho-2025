
elementosCampoe elementosCidade: Matrizes que armazenam os objetos que representam os elementos das áreas rural e urbana, respectivamente (ex.: 'Trator', 'Supermercado'). Cada objeto possui propriedades como id, name, x, ycoordenadas, width, e height.
conexoesCorretas: Uma matriz que define todos os pares corretos para a fase atual (por exemplo, 'vaca' conectado a 'laticinio').
conexoesFeitas: Uma matriz que rastreia as conexões que o jogador fez com sucesso .
arrastando: Um sinalizador booleano que aparece truequando o jogador está arrastando uma linha.
elementoSelecionado: Armazena o elemento rural do qual o jogador está arrastando no momento.
pontuacao: A pontuação atual do jogador.
fase: O nível ou fase atual do jogo.
setup():

Inicializa a tela p5.js (a área de desenho) e chama inicializarFase()para configurar o primeiro nível.
draw():

Esta função é executada continuamente, redesenhando tudo na tela.
Ele desenha o fundo.
Ele itera elementosCampoe elementosCidadedesenha cada elemento retangular com seu nome. Os elementos rurais são verdes e os elementos urbanos são azul-acinzentados.
Ele desenha todas asconexoesFeitas linhas azuis.
Se o jogador estiver arrastando ( arrastandois true), ele desenha uma linha vermelha do elemento rural selecionado até a posição atual do mouse.
Ele exibe o atual pontuacaoefase .
Quando todas as conexões corretas para uma fase são feitas, a mensagem "Fase Concluída!" é exibida , solicitando que o jogador clique para avançar.
mousePressed():

Detecta se o jogador clica em um elemento rural. Em caso afirmativo, define arrastandoe truearmazena o elemento clicado em elementoSelecionado.
Se a fase atual for concluída, clicar avança o jogo para a próxima fase e concede pontos de bônus.
mouseReleased():

Quando o jogador solta o botão do mouse, esta função verifica se o elementoSelecionado(elemento rural que está sendo arrastado) foi solto em um elCidade(elemento urbano).
Caso ocorra uma queda, ele liga tentarConectar()para verificar se a conexão está correta.
tentarConectar(campoEl, cidadeEl):

Esta é a lógica central para verificar conexões.
Ele itera conexoesCorretaspara ver se campoEle cidadeElformam um par válido.
Ele também verifica se a conexão já foi feita para evitar linhas duplicadas.
Se a conexão estiver correta e for nova, ela será adicionada a conexoesFeitas, e o jogador ganha pontos.
Se a conexão estiver incorreta, o jogador perde alguns pontos.
inicializarFase(numeroFase):

Redefine o estado do jogo para uma nova fase (limpa elementos e conexões).
Com base em numeroFase, ele preenche elementosCampo, elementosCidade, e conexoesCorretascom itens específicos para aquele nível.
For example, Fase 1 connects 'Trator' to 'Supermercado', 'Vaca' to 'Laticínio', and 'Plantação' to 'Restaurante'.
Fase 2 introduces new concepts like 'Algodão' to 'Fábrica Têxtil' and 'Apicultor' to 'Farmácia'.
If there are no more defined phases, it displays a "Parabéns! Você conectou o Campo e a Cidade!" message with the final score.
