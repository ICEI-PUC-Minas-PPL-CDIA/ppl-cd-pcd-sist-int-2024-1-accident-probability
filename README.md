# probabilidade de acidentes rodoviários

A partir de uma base de dados extraída da plataforma Kaggle e posterior elaboração da seguinte pergunta orientada a dados: "qual é a frequência de acidentes rodoviários que resultam em ferimentos leves, graves ou fatais?", foi realizada uma análise exploratória e preparação dos dados, e então desenvolvidos modelos de aprendizado de máquina. A análise teve enfoque na distribuição de acidentes com base nas condições da superfície da estrada, no tipo de estrada, na área urbana ou rural, na hora do acidente, no tipo de junção, nas condições meteorológicas, e, por fim, nos limites de velocidade (feature selection). Foi utilizada como variável alvo a gravidade dos ferimentos. Em consequência ao grande desbalanceamento de classes (uma limitação) que a base de dados apresenta, foram efetuadas múltiplas tentativas de desenvolvimento de sistemas inteligentes diferentes, usando métodos de Árvore de Decisão, Floresta Aleatória e Rede Neural. Apesar de ajustes e modificações nos códigos, todos os modelos apresentaram resultados de baixa precisão, recall e acurácia, especialmente para a classe 2, slight, a classe majoritária. Isso indica que nenhum modelo foi capaz de apresentar um desempenho ideal para responder à pergunta, dificultando uma conclusão vantajosa para o projeto.

## Integrantes

* Matheus Melo Couto, matheus.couto.1525924@sga.pucminas.br
* Luan Inaibes Guimarães, liguimaraes@sga.pucminas.br
* João Henrique Pereirinha Sorrentino, jhpsorrentino@sga.pucminas.br
* Rafael Brandão de Oliveira, rafael.brandao@sga.pucminas.br
* Serena Ferreira Moreira, serena.ferreira@sga.pucminas.br
* Heitor Ramos de Oliveira, heitor.oliveira@sga.pucminas.br

## Professor

* Hugo Bastos de Paula

## Instruções de utilização

Assim que a primeira versão do sistema estiver disponível, deverá complementar com as instruções de utilização. Descreva como instalar eventuais dependências e como executar a aplicação.

## Histórico de versões

* 0.1.1
    * CHANGE: Atualização das documentacoes. Código permaneceu inalterado.
* 0.1.0
    * Indução do primeiro modelo do agente inteligente.
* 0.0.1
    * Trabalhando na preparação dos dados.

