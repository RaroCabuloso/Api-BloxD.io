Módulo 01: Introdução

Bem-vindo ao primeiro módulo do curso Bloxd.io API para Iniciantes!

Objetivos

Conhecer o propósito do curso e o que você vai aprender.

Entender como executar scripts dentro do Bloxd.io.

Verificar se você possui as ferramentas básicas para começar.


Pré‑requisitos

Antes de avançar, verifique se você tem:

Acesso ao jogo Bloxd.io (versão atualizada).

Permissão para criar mundos e usar Code Blocks/Code Boards.

Editor de texto (VS Code, Sublime, etc.) e Git instalado.

Noções básicas de JavaScript (variáveis, funções, sintaxe).


Primeiro Exemplo: "Olá, Mundo!"

Vamos criar o nosso primeiro script dentro do Bloxd.io para exibir uma mensagem de boas‑vindas.

1. Abra o Bloxd.io e crie um novo mundo.


2. Pegue um Code Block no inventário criativo.


3. Posicione-o no mundo e clique com o botão direito (PC) ou toque (móvel) para abrir o editor.


4. Apague o comentário padrão e cole o seguinte código:

// Exibe mensagem de boas‑vindas no chat ao clicar no bloco
function tick() {
  // nada aqui ainda
}

// Quando um jogador clicar neste bloco, enviaremos uma mensagem
onPlayerClick = (playerId) => {
  api.sendMessage(playerId, "Olá, Mundo! Bem‑vindo ao seu primeiro script Bloxd!", {
    color: "lightgreen"
  });
};


5. Salve e feche o editor. Clique novamente no bloco com o botão direito para executar.


6. Clique no bloco no mundo e veja a mensagem aparecer no chat!



Explicação do Código

onPlayerClick = (playerId) => { … } define um callback chamado quando alguém clica no bloco.

api.sendMessage(playerId, mensagem, estilo) envia um texto colorido ao jogador.


Próximos Passos

Experimente alterar a cor ou o texto da mensagem.

Leia o próximo módulo: 02‑code‑blocks‑e‑boards para entender as diferenças entre Code Blocks e Code Boards.



---

> Dica: reserve alguns minutos para brincar com esse exemplo até se sentir confortável com o processo de criar, editar e executar scripts no Bloxd.io.



