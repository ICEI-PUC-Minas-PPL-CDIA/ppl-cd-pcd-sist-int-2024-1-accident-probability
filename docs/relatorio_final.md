# Probabilidade de acidentes


Matheus Melo Couto, matheus.couto.1525924@sga.pucminas.br

Luan Inaibes Guimarães, liguimaraes@sga.pucminas.br

João Henrique Pereirinha Sorrentino, jhpsorrentino@sga.pucminas.br

Rafael Brandão de Oliveira, rafael.brandao@sga.pucminas.br

Heitor Ramos de Oliveira, heitor.oliveira@sga.pucminas.br

Serena Ferreira Moreira, serena.ferreira@sga.pucminas.br

---

Professores:

hugodepaula


---

_Curso de Ciência de Dados, Unidade Praça da Liberdade_

_Instituto de Informática e Ciências Exatas – Pontifícia Universidade de Minas Gerais (PUC MINAS), Belo Horizonte – MG – Brasil_

---

---

A partir de uma base de dados, com registros de Acidentes Rodoviários, extraída da plataforma Kaggle, e posterior elaboração da seguinte pergunta orientada a dados: "qual é a frequência de acidentes rodoviários que resultam em ferimentos leves, graves ou fatais?", foi realizada uma análise exploratória e preparação dos dados, e então desenvolvidos modelos de aprendizado de máquina. A análise teve enfoque na distribuição de acidentes com base nas condições da superfície da estrada, no tipo de estrada, na área urbana ou rural, na hora do acidente, no tipo de junção, nas condições meteorológicas, e, por fim, nos limites de velocidade (feature selection). Foi utilizada como variável alvo a gravidade dos ferimentos. Em consequência ao grande desbalanceamento de classes (uma limitação) que a base de dados apresenta, foram efetuadas múltiplas tentativas de desenvolvimento de sistemas inteligentes diferentes, usando métodos de Árvore de Decisão, Floresta Aleatória e Rede Neural. Apesar de ajustes e modificações nos códigos, todos os modelos apresentaram resultados de baixa precisão, recall e acurácia, especialmente para a classe 2, slight, a classe majoritária. Isso indica que nenhum modelo foi capaz de apresentar um desempenho ideal para responder à pergunta, dificultando uma conclusão vantajosa para o projeto. 

## Introdução

   Os acidentes nas rodovias representam um grave problema em todo o mundo, resultando em perdas humanas, danos materiais e impactos econômicos significativos. Diante esse contexto, a análise de dados e o desenvolvimento de sistemas inteligentes através da ciência de dados tem se mostrado uma abordagem promissora para a prevenção e diminuição extrema desses acidentes. A capacitação dos sistemas de coletar, processar e analisar grandes volumes de dados em tempo real, juntamente com a capacidade de tomar decisões autônomas e rápidas, torna-os ferramentas essenciais na busca por estratégias mais eficazes de segurança viária. Este trabalho tem como objetivo explorar o papel dos sistemas inteligentes na redução de acidentes nas rodovias, destacando suas potenciais contribuições e desafios a serem superados.  


###    Contextualização

   A crescente disponibilidade de dados e avanços tecnológicos tem permitido o desenvolvimento constante e exponencial no setor automobilístico, tanto para produção de automóveis cada vez mais eficazes e seguros, quanto para a conservação da própria segurança no trânsito. A aplicação da Ciência de Dados se mostra como uma ferramenta necessária para este projeto — com a capacidade de coletar, processar e analisar grandes volumes de dados, permite-se identificar padrões/correlações, e, assim, projetar medidas. Dessa forma, esse trabalho propõe explorar o uso de técnicas avançadas da análise exploratória de dados para 
compreender os motivos que incidem em acidentes rodoviários, de forma a prevê-los e possibilitar o melhoramento das vias e dos sistemas de transportes.  


###    Problema
   O problema que o agente pretende resolver é o alto índice de incidentes que uma certa via pode ter. Certas vias específicas enfrentam dificuldades com altas taxas de colisões, o que impacta diretamente a qualidade de vida da população, gerando, assim, um aumento da mortalidade e do impacto emocional nos indivíduos. De acordo com o PAHO (Pan American Health Organization), "90% das mortes no trânsito ocorrem em países de baixa e média renda. Os acidentes nas vias custam aos países cerca de 3% de seus produtos internos brutos. Quase metade (49%) das pessoas que morrem nas vias em todo o mundo são pedestres, ciclistas e motociclistas." 

   Essa circunstância revela uma série de desafios, entre eles: segurança no trânsito, dificultando a segurança de todos os usuários das vias, incluindo pedestres, ciclistas, motociclistas e motoristas. E também na falta de infraestrutura, muitas regiões enfrentam desafios relacionados à falta de investimento em infraestrutura, estradas mal conservadas, falta de sinalização adequada e projetos viários inadequados.  


###    Objetivo geral

   Analisar acidentes em determinada via, identificar tendências e extrair informações para implementação de medidas de segurança, necessárias para reduzir o número de vítimas de tais imprudências.  

####    Objetivos específicos

• Identificar os principais motivos para a causa de acidentes de tráfego em uma rodovia específica;

• Analisar os dados estatísticos relacionados aos incidentes;

• Comparar e contrastar os dados obtidos sobre os acidentes, como o horário do dia, o dia da semana, o tipo de veículo envolvido no acidente, as condições das vias, as condições climáticas, etc.; 

###    Justificativas

   A probabilidade de acidentes como tema de estudo é crucial em diversos setores, permitindo avaliar riscos e adotar medidas preventivas. Essa análise não só compreende os potenciais perigos em atividades e ambientes, mas também direciona a implementação de protocolos de segurança eficazes. Ao quantificar a probabilidade de acidentes, é possível identificar áreas vulneráveis, priorizar investimentos em segurança e reduzir eventos indesejados. Integrar essa probabilidade em análises de risco permite decisões mais embasadas, promove uma cultura preventiva e valoriza o bem-estar de todos. Assim, a consideração da probabilidade de acidentes não apenas preserva vidas e recursos, mas também fortalece a sustentabilidade e a eficiência operacional a longo prazo.


##    Público alvo

- Agências de seguros: que utiliza os dados fornecidos para melhor escolha de preço, de acordo com a região de vias de maior ou menor risco.
- Governo Público: responsável pelo reparo e manutenção da via, diminuindo o risco de acidentes, ocasionandos em determinados trechos das vias.


## Análise exploratória dos dados

###    Dicionário de dados

BASE DE DADOS : Acidentes rodoviários

FONTE: Kaggle

Este conjunto de dados fornece registos detalhados dos acidentes rodoviários ocorridos durante o mês de janeiro de 2021. Ele inclui informações como a data do acidente, dia da semana, controle de cruzamento, gravidade do acidente, coordenadas geográficas, condições de iluminação e clima, detalhes do veículo e muito mais. Os dados são valiosos para analisar e compreender os fatores que contribuem para os acidentes de trânsito nessa área urbana, auxiliando no desenvolvimento de estratégias para a melhoria da segurança viária.

|   Variáveis   | Tipo de dado  |                      Descrição                                    |
| ------------- | ------------- |------------------------------------------------------------       |
|Accident_Index |   categórico    |   Um identificador exclusivo para cada registro de acidente.      |
|Accident_Date  |   numérico        | A data em que ocorreu o acidente (formato: DD/MM/AAAA).     |
|Day_of_Week    |   categórico    | O dia da semana em que ocorreu o acidente.                     | 
|Junction_Control |   textual   | Descreve o tipo de controle de cruzamento no local do acidente (por exemplo, "Ceder ou descontrolado").    | 
|Junction_Detail  |   textual    | Fornece detalhes adicionais sobre o cruzamento onde ocorreu o acidente (por exemplo, "T ou cruzamento escalonado").    |
|Accident_Injuries|   categórico  | Indica a gravidade dos ferimentos resultantes do acidente (ex.: “Grave”, "Leve"). |
|Latitude       |   numérico     |   A latitude geográfica do local do acidente.    |
|Light_Conditions |   categórico    | Descreve as condições de iluminação no momento do acidente (por exemplo, "Luz do dia"). 				    |
|Local_Authority_(District)   |   textual | O distrito da autoridade local onde ocorreu o acidente. |
|Carriageway_Hazards  |   categórico  | Descreve quaisquer perigos presentes na faixa de rodagem no momento do acidente (por exemplo, "Nenhum").  |
|Longitude  |   numérico    | A longitude geográfica do local do acidente.	            |
|Number_of_Casualties  |   numérico    | O número total de vítimas envolvidas no acidente.   |
|Number_of_Vehicles   |   numérico  | O número total de veículos envolvidos no acidente.  |
|Police_Force |   textual  | A força policial que tratou do acidente.   |
|Road_Surface_Conditions |   categórico  | Descreve as condições da superfície da estrada no momento do acidente (por exemplo, "Seca").    |
|Road_Type |   categórico  |  Especifica o tipo de estrada onde ocorreu o acidente (por exemplo, “Rua de mão única”).  |
|Speed_limit |   numérico  | O limite de velocidade aplicável à estrada onde ocorreu o acidente. |
|Time  |   numérico    |  A hora do dia em que ocorreu o acidente (formato: HH:MM).  |
|Urban_or_Rural_Area  |   categórico    | Indica se o acidente ocorreu em área urbana ou rural. |
|Weather_Conditions  |   categórico    | Descreve as condições meteorológicas no momento do acidente (por exemplo, "Bom, sem ventos fortes").   |
|Vehicle_Type  |   categórico    | especifica o tipo de veículo envolvido no acidente (por exemplo, "Carro", "Táxi/Carro de aluguel particular").  |

###    Descrição de dados

• DADOS NUMÉRICOS:

- Accident_Date - A data em que ocorreu o acidente (formato: DD/MM/AAAA).
- Latitude - A latitude geográfica do local do acidente.
- Longitude - A longitude geográfica do local do acidente.
- Number_of_Casualties - O número total de vítimas envolvidas no acidente.  		    
- Number_of_Vehicles - O número total de veículos envolvidos no acidente. 
- Speed_limit - O limite de velocidade aplicável à estrada onde ocorreu o acidente.
- Time - A hora do dia em que ocorreu o acidente (formato: HH:MM).

• DADOS CATEGÓRICOS:

- Accident_Index - Um identificador exclusivo para cada registro de acidente.
- Day_of_Week - O dia da semana em que ocorreu o acidente.
- Junction_Control - Descreve o tipo de controle de cruzamento no local do acidente (por exemplo, "Ceder ou descontrolado").
- Junction_Detail - Fornece detalhes adicionais sobre o cruzamento onde ocorreu o acidente (por exemplo, "T ou cruzamento escalonado").
- Accident_Severity - Indica a gravidade do acidente (ex.: “Grave”).
- Light_Conditions - Descreve as condições de iluminação no momento do acidente (por exemplo, "Luz do dia").
- Local_Authority_(District) - O distrito da autoridade local onde ocorreu o acidente.
- Carriageway_Hazards - Descreve quaisquer perigos presentes na faixa de rodagem no momento do acidente (por exemplo, "Nenhum").
- Police_Force - A força policial que tratou do acidente.
- Road_Surface_Conditions - Descreve as condições da superfície da estrada no momento do acidente (por exemplo, "Seca").    
- Road_Type - Especifica o tipo de estrada onde ocorreu o acidente (por exemplo, “Rua de mão única”). 
- Urban_or_Rural_Area - Indica se o acidente ocorreu em área urbana ou rural. 
- Weather_Conditions - Descreve as condições meteorológicas no momento do acidente (por exemplo, "Bom, sem ventos fortes").   
- Vehicle_Type - especifica o tipo de veículo envolvido no acidente (por exemplo, "Carro", "Táxi/Carro de aluguel particular").  


|   Variáveis   | Tipo de dado  |                      Descrição                                    |
| ------------- | ------------- |------------------------------------------------------------       |
|Accident_ID |   categórico não ordinal   |   Um identificador exclusivo para cada registro de acidente.      |
|Accident_Date  |   numérico        | A data em que ocorreu o acidente (formato: DD/MM/AAAA).                 |
|Day_of_Week    |   categórico ordinal   | O dia da semana em que ocorreu o acidente.                     | 
|Junction_Detail| categórico não ordinal | Fornece detalhes adicionais sobre o cruzamento onde ocorreu o acidente (por exemplo, "T ou cruzamento escalonado").  |
|Accident_Injuries| categórico ordinal  | Indica a gravidade do acidente (ex.: “Grave”). |
|Light_Conditions | categórico não ordinal | Descreve as condições de iluminação no momento do acidente (por exemplo, "Luz do dia"). |
|Number_of_Casualties  |   numérico    | O número total de vítimas envolvidas no acidente.  	    |
|Number_of_Vehicles   |   numérico  | O número total de veículos envolvidos no acidente.  |
|Road_Surface_Conditions |   categórico não ordinal | Descreve as condições da superfície da estrada no momento do acidente (por exemplo, "Seca").    |
|Road_Type |   categórico não ordinal |  Especifica o tipo de estrada onde ocorreu o acidente (por exemplo, “Rua de mão única”).  |
|Speed_limit |   numérico  | O limite de velocidade aplicável à estrada onde ocorreu o acidente. |
|Hour_of_Accident|   numérico    |  A hora do dia em que ocorreu o acidente (formato: HH:MM).  |
|Urban_or_Rural_Area  | categórico não ordinal | Indica se o acidente ocorreu em área urbana ou rural. |
|Weather_Conditions  | categórico não ordinal | Descreve as condições meteorológicas no momento do acidente (por exemplo, "Bom, sem ventos fortes").   |
|Vehicle_Type  | categórico não ordinal | especifica o tipo de veículo envolvido no acidente (por exemplo, "Carro", "Táxi/Carro de aluguel particular").  |

### Distribuição de acidentes com base com base na gravidade dos ferimentos:
![Accident_Injuries](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/e21499bb-af24-45f9-85cc-4bb8b83012f9)

### Distribuição de acidentes com base nas condições da superfície da estrada:
![Road_Surface_Conditions](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/5a669fcd-97f8-4ea2-837f-14c14e9490a9)

### Distribuição de acidentes com base no tipo de estrada:
![Road_Type](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/52f57bb6-6454-40cc-8b67-2f099b075157)

### Distribuição de acidentes com base na área urbana ou rural:
![Urban_or_Rural_Area](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/ada5343c-48d7-405a-9a1a-f86e39075244)

### Distribuição de acidentes com base na hora do acidente:
![Hour_of_Accident](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/d98c1c4a-8698-424c-994c-cbddac1883c8)

### Distribuição de acidentes com base no tipo de junção:
![Junction_Detail](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/6a8f525f-c1bd-4a02-9ffe-c8aebb0dced7)

### Distribuição de acidentes com base nas condições meteorológicas:
![Weather_Conditions](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/4ae93d3e-b418-4d7a-8121-f5bdbfd41963)

### Distribuição de acidentes com base nos limites de velocidade:
![Speed_limit](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/035adeee-889d-48f8-83ea-55308c0a5e57)

### Distribuição de acidentes com base nas condições de luminosisade e dias da semana:
![Light_Day](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/e0174d14-3cf2-4b3e-ad54-edb9971279ab)

[Código Gráficos](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/48fe58c2c6aaa8ed8ffb4f8af143fabe2cf4648c/docs/Projeto_Gr%C3%A1ficos.ipynb)

### Preparação dos dados

PERGUNTA ORIENTADA A DADOS: qual é a frequência de acidentes rodoviários que resultam em ferimentos leves, graves ou fatais?

- Foram alterados os nomes das variáveis Accident_Index e Time para Accident_ID e Hour_of_Accident, a fim de facilitar a compreensão;
- Foram eliminadas as colunas: Junction_Control, Latitude, Local_Authority_(District), Carriageway_Hazards, Longitude e Police_Force;
- As datas foram passadas para o formato DD/MM/AA;
- No horário do acidente, os minutos foram desconsiderados, mantendo apenas a hora em questão;
- No tipo de veículo, foram desconsideradas características específicas dos meios de transporte, como as cilindradas de motos e o peso de transportes de mercadoria;
- Espaços vazios em Road_Surface_Conditions, Road_Type e Weather_Conditions foram substituídos por "other";
- Na coluna "Light_Conditions", Daylight foi substituído por Day;
- Foi verificada a presença de dados nulos/omissos, mas não havia nenhum;
- Foi feita a remoção de outliners conforme a seguinte incoerência/improbabilidade: mais de 10 pessoas envolvidas no acidente causado por apenas 1 veículo.

  TRANSFORMAÇÃO DE DADOS:
- Uma faixa de valores foi estabelecida aos dados da coluna Hour_of_Accident.

[Código do processo de Manipulação dos Dados](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/48fe58c2c6aaa8ed8ffb4f8af143fabe2cf4648c/docs/Projeto_Manipula%C3%A7%C3%A3oDados.ipynb)

## Indução de modelos

### Modelos 1, 2, 3, 4, 5: Árvore de Decisão

A Árvore de Decisão foi escolhida como nosso primeiro modelo induzido, visto sua habilidade em manipular dados não lineares, interações complexas (o impacto de uma variável pode variar dependendo dos valores de outras variáveis no modelo), e dados mistos (mistura de variáveis categóricas e numéricas).

Processo utilizado para amostragem de dados 1 (explicado linha por linha):
[Processo do código](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/main/docs/decisiontree.ipynb)

Processo utilizado para amostragem de dados 2 (explicado linha por linha):
[Processo do código](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/48fe58c2c6aaa8ed8ffb4f8af143fabe2cf4648c/docs/Projeto_DecisionTrees_RandomForest.ipynb)

### Modelo 6: Random Forest

Motivos para Escolha: 

- Capacidade de lidar com dados categóricos: Random Forest pode tratar variáveis categóricas com facilidade, convertendo-as internamente em formatos adequados. 
- Desempenho: Agrega múltiplas árvores de decisão, o que melhora a precisão e a generalização do modelo ao reduzir o overfitting. 
- Interpretação das variáveis: Importâncias das características podem ser extraídas, ajudando a entender quais fatores mais influenciam a gravidade dos acidentes. 

### Modelo 7: Rede Neural

Motivos para Escolha: 

- Capacidade de aprender padrões complexos;
- Flexibilidade na representação de dados;
- Tratamento eficaz de grandes volumes de dados;
- Desempenho em tarefas de classificação complexas;
- Capacidade de lidar com características não lineares e interações complexas entre características.

Processo utilizado para amostragem de dados 3 (explicado linha por linha):
[Processo do código](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/48fe58c2c6aaa8ed8ffb4f8af143fabe2cf4648c/docs/Projeto_RedeNeural.ipynb)

## Resultados

### Resultados obtidos com o modelo 1.

#### Acurácia

Treinamento - 0.85 ≅ 85%    
Teste - 0.86 ≅ 86%   

#### Matriz de Confusão

|                | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| Fatal          | 0.00      | 0.00   | 0.00     | 574     |
| Serious        | 0.00      | 0.00   | 0.00     | 5989    |
| Slight         | 0.86      | 1.00   | 0.92     | 39633   |
| **Accuracy**   |           |        | 0.86     | 46196   |
| **Macro Avg**  | 0.29      | 0.33   | 0.31     | 46196   |
| **Weighted Avg** | 0.74    | 0.86   | 0.79     | 46196   |

_______________________________________________________
### Observações:

1- Desequilíbrio nas Classes:

- O modelo está prevendo quase exclusivamente a classe "Slight" (Leve), ignorando as classes "Fatal" (Fatal) e "Serious" (Grave). Isso é evidenciado pelos valores de precisão, recall e F1-Score sendo 0.00 para as classes "Fatal" e "Serious".
2- Macro Average vs. Weighted Average:
- Macro Avg (Média Macro): Calcula a média das métricas de todas as classes, tratando cada classe igualmente. Isso resulta em baixos valores (0.29, 0.33 e 0.31) devido ao desempenho ruim nas classes "Fatal" e "Serious".
- Weighted Avg (Média Ponderada): Calcula a média ponderada das métricas, levando em consideração o número de amostras em cada classe. O valor é mais alto (0.74, 0.86 e 0.79) porque a classe "Slight" domina o conjunto de dados.

### Ações Recomendadas:

1- Balanceamento das Classes:
- Utilizar técnicas de balanceamento de dados, como oversampling (ex.: SMOTE) ou undersampling, para aumentar a representação das classes "Fatal" e "Serious".

2- Ajuste do Modelo:
- Ajustar hiperparâmetros do modelo ou experimentar modelos diferentes, como Random Forest, CatBoost, ou LightGBM, que podem lidar melhor com o desequilíbrio das classes.

3- Coletar Mais Dados:
- Se possível, coletar mais dados para as classes minoritárias ("Fatal" e "Serious") para melhorar a capacidade do modelo de aprender a partir dessas amostras.

### Interpretação do modelo 1

#### Árvore de Decisão

![arvore_decisao](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/main/docs/imagens/tree.png)

##### Interpretação Geral  
A árvore de decisão está utilizando várias características relacionadas a detalhes de junção para prever a gravidade do acidente. Cada nó faz uma decisão binária baseada em uma característica específica e os dados são divididos de acordo com essas decisões. A profundidade da árvore e a complexidade das ramificações indicam que muitos fatores de junção diferentes estão sendo considerados para classificar os acidentes como leves, graves ou fatais.  

##### Pontos Chave  
A maioria das decisões iniciais se concentra em verificar se o acidente ocorreu em diferentes tipos de junções.  
Cada divisão subsequente afina ainda mais os critérios com base em detalhes específicos da junção.  
A classe final atribuída a cada nó folha é "Slight" (Leve), indicando que a maioria dos acidentes nos dados de treinamento foram leves. 

### Resultados obtidos com o modelo 2.
Training Accuracy: 0.35

Test Accuracy: 0.14

Classification Report:

|                | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| Fatal          | 0.01      | 0.27   | 0.02     | 574     |
| Serious        | 0.13      | 0.70   | 0.23     | 5989    |
| Slight         | 0.89      | 0.06   | 0.11     | 39633   |
| **Accuracy**   |           |        | 0.14     | 46196   |
| **Macro Avg**  | 0.34      | 0.34   | 0.12     | 46196   |
| **Weighted Avg** | 0.78    | 0.14   | 0.12     | 46196   |


### Interpretação do modelo 2
![DT_Road_Surface_Conditions](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/8f1bf989-fb87-44ff-9433-bfda804a3226)

### Resultados obtidos com o modelo 3.
Training Accuracy: 0.37

Test Accuracy: 0.20

Classification Report:

|                | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| Fatal          | 0.02      | 0.22   | 0.03     | 574     |
| Serious        | 0.14      | 0.79   | 0.23     | 5989    |
| Slight         | 0.90      | 0.11   | 0.19     | 39633   |
| **Accuracy**   |           |        | 0.20     | 46196   |
| **Macro Avg**  | 0.35      | 0.37   | 0.15     | 46196   |
| **Weighted Avg** | 0.79    | 0.20   | 0.19     | 46196   |


### Interpretação do modelo 3
![DT_Road_Type](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/fbafa745-ee7e-45aa-8eac-dd4cfdfac210)

### Resultados obtidos com o modelo 4.
Training Accuracy: 0.42

Test Accuracy: 0.57

Classification Report:

|                | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| Fatal          | 0.02      | 0.56   | 0.04     | 574     |
| Serious        | 0.00      | 0.00   | 0.00     | 5989    |
| Slight         | 0.87      | 0.66   | 0.75     | 39633   |
| **Accuracy**   |           |        | 0.57     | 46196   |
| **Macro Avg**  | 0.30      | 0.40   | 0.26     | 46196   |
| **Weighted Avg** | 0.75    | 0.57   | 0.64     | 46196   |


### Interpretação do modelo 4
![DT_Urban_or_Rural_Area](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/b2bef5e5-4f7d-4b95-b95c-71cd8c88b771)

### Resultados obtidos com o modelo 5.
Training Accuracy: 0.39

Test Accuracy: 0.67

Classification Report:

|                | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| Fatal          | 0.02      | 0.39   | 0.04     | 574     |
| Serious        | 0.00      | 0.00   | 0.00     | 5989    |
| Slight         | 0.87      | 0.77   | 0.82     | 39633   |
| **Accuracy**   |           |        | 0.67     | 46196   |
| **Macro Avg**  | 0.30      | 0.39   | 0.29     | 46196   |
| **Weighted Avg** | 0.75    | 0.67   | 0.70     | 46196   |


### Interpretação do modelo 5
![DT_Hour_of_Accident](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/6e552249-1aa7-4983-859f-75efa1b8b1f7)

## Árvore de Decisão completa:
Training Accuracy: 0.50

Test Accuracy: 0.52

Classification Report:

|                | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| Fatal          | 0.02      | 0.54   | 0.05     | 574     |
| Serious        | 0.14      | 0.20   | 0.17     | 5989    |
| Slight         | 0.89      | 0.57   | 0.69     | 39633   |
| **Accuracy**   |           |        | 0.52     | 46196   |
| **Macro Avg**  | 0.35      | 0.44   | 0.30     | 46196   |
| **Weighted Avg** | 0.78    | 0.52   | 0.62     | 46196   |


### CONCLUSÃO:

Os resultados mostram que o modelo tem uma baixa precisão e recall, especialmente para a classe 2 (a classe majoritária). A acurácia geral do modelo também é muito baixa. Principais causas: desbalanceamento severo —  o número de exemplos da classe 2 (39633) é muito maior do que das classes 0 (574) e 1 (5989), mesmo após o oversampling e undersampling; e, possivelmente, pela Árvore de Decisão ser um modelo muito simples.

### Modelo 6: Random Forest — tende a ser mais robusto e pode lidar melhor com dados desbalanceados.

### Modificações:

- Pipeline de Reamostragem:

Utilização de um Pipeline para combinar a técnica de reamostragem SMOTE com a classificação por meio de uma Random Forest.

- Normalização dos Dados:

Aplicação do StandardScaler para normalizar os dados de entrada, o que pode melhorar o desempenho do modelo.

- Grade de Hiperparâmetros:
  
Definição de uma grade de hiperparâmetros para ajustar os parâmetros do classificador Random Forest usando a pesquisa em grade GridSearchCV.

### Resultados obtidos com o modelo 6.

Accurácia: 0.59

Relatório de Classificação:

|                | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| Fatal          | 0.03      | 0.52   | 0.06     | 617     |
| Serious        | 0.16      | 0.19   | 0.17     | 6085    |
| Slight         | 0.88      | 0.65   | 0.75     | 39494   |
| Macro Avg      | 0.36      | 0.45   | 0.33     | 46196   |
| Weighted Avg   | 0.78      | 0.59   | 0.66     | 46196   |


### Modelo 7: Rede Neural

### Interpretação do modelo 7
![RedeNeural](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/assets/164661514/73947a9e-15f9-4968-8160-976b57aae8a2)

### Resultados obtidos com o modelo 7.

Acurácia: 0.63

Relatório de Classificação:

|                | Precision | Recall | F1-Score | Support |
|----------------|-----------|--------|----------|---------|
| Fatal          | 0.03      | 0.51   | 0.06     | 617     |
| Serious        | 0.15      | 0.10   | 0.12     | 6085    |
| Slight         | 0.88      | 0.71   | 0.79     | 39494   |
| Macro Avg      | 0.35      | 0.44   | 0.32     | 46196   |
| Weighted Avg   | 0.77      | 0.63   | 0.69     | 46196   |



## Análise comparativa dos modelos

Para a elaboração do projeto, foram usados 3 métodos de aprendizado supervisionado distintos, resultando na execução de 7 modelos de aprendizado de máquina ao total: do modelo 1 ao 5, foi usado o método da Árvore de Decisão, sendo ele o mais simples. A princípio, foram elaborados códigos separados, cada um específico para cada uma das 5 features - inicialmente - selecionadas (Junction_Detail, Road_Surface_Conditions, Road_Type, Urban_or_Rural_Area, Hour_of_Accident), tendo a variável "Accident_Injuries" como target. Em seguida, o modelo 6 foi desenvolvido usando o método de Floresta Aleatória, uma variação mais complexa da Árvore de Decisão, mas com complexidade e performance mais significativas. Foram acrescentadas as features Weather_Conditions e Speed_limit, a fim de chegar a um resultado mais favorável. Por fim, o último modelo foi elaborado usando como método a Rede Neural, que, para processar as informações, simula o funcionamento do cérebro humano a partir de uma matriz de confusão.

Com base nos resultados obtidos, pode-se concluir que o modelo mais preciso foi a Rede Neural. Com 63% de acurácia, sem desconsiderar nenhum dado fornecido ao sistema, manteu certa consistência em seus resultados, tendo obtido, nos recalls, 51% de acerto em fatal e 77% em slight, mas apenas 11% em serious. Em segundo lugar, dentre os parâmetros de eficiência, o modelo de Random Forest apresenta precisão e recall maiores que os resultados das Árvores, tendo 59% de acurácia. Já a Rede Neural, obteve recall de 52% em fatal e 65% em slight, seguindo com serious sendo a menor taxa de acerto, com 19%. Dessa forma, é possível definir que a Árvore de Decisão não foi capaz de processar os dados fornecidos e definir, com qualidade e precisão, os resultados a partir deles, vista a sua acurácia final, que, apesar de ter sido a mais precisa nas classes de menor peso, não apresentou tanta diferença em relação às outras, com 54% em fatal, 20% em serious e 57% em slight.

Analisando por partes, todos os modelos apresentam falhas: o modelo 1 desconsidera as classes fatal e serious, operando apenas a classe de maior peso (slight); os modelos 2 e 3 tem um desequilíbrio significativo entre sua precisão e recall (1% para 27% em fatal, 13% para 70% em serious e 89% para 6% em slight - modelo 2; e 2% para 22% em fatal, 14% para 79% em serious e 90% para 11% em slight - modelo 3); os modelos 4 e 5 consideram apenas os acidentes leves e fatais,  ignorando os sérios. Dentre os modelos da Árvore de Decisão, o que apresentou maior precisão foi o modelo 5, com 67% de acurácia final, sendo maior até mesmo que o resultado da rede neural. Obteve 39% em fatal, menor que os 51% da rede neural, e 77% em slight, maior que os 71%. Essas falhas somadas resultam em um produto incapaz, que tende a, aproximadamente, 50% de falhas em seus testes, provando-se, assim, ineficiente. Todos os modelos tiveram dificuldades, principalmente devido ao desequilíbrio dos dados da base que, mesmo com métodos de oversampling e undersampling, continuaram em uma escala desproporcional e desbalanceada, tendo a classe 2 (slight) quase 7 vezes mais que a classe 1 (serious), e 70 vezes mais que a classe 0 (fatal). 

## Ameaça à validade

Interna: a ameaça à validade interna pode surgir do viés nos dados coletados. Este viés pode ocorrer devido a falhas na precisão ou na integridade dos dados, influenciando negativamente a confiabilidade dos resultados. Além disso, a possibilidade dos dados coletados estarem modificados intencional ou acidentalmente representa uma ameaça significativa, comprometendo a precisão e a validade das conclusões do estudo. Essas questões destacam a importância da coleta cuidadosa e da verificação rigorosa dos dados para garantir a validade interna do projeto.

Externa: a ameaça à validade externa se manifesta quando os resultados não podem ser generalizados para todas as regiões devido a discrepâncias nas leis de trânsito, na infraestrutura rodoviária e nos comportamentos dos motoristas. Essas disparidades regionais podem limitar a aplicabilidade dos achados do estudo em contextos geográficos distintos, comprometendo a capacidade de extrapolação e ampliação dos resultados para uma escala mais ampla. Portanto, a consideração desses fatores é essencial para avaliar corretamente a validade externa do projeto e sua relevância em diferentes cenários rodoviários.

## Conclusão

A partir de uma base de dados, com registros de Acidentes Rodoviários, e posterior elaboração da seguinte pergunta orientada a dados: "qual é a frequência de acidentes rodoviários que resultam em ferimentos leves, graves ou fatais?", foi realizada uma análise exploratória e preparação dos dados, e então desenvolvidos modelos de aprendizado de máquina. É assertivo afirmar que acidentes rodoviários acontecem em função de variáveis externas, como as condições das vias, do clima, do motorista, entre outras. Portanto, a análise teve enfoque na distribuição de acidentes com base nas condições da superfície da estrada, no tipo de estrada, na área urbana ou rural, na hora do acidente, no tipo de junção, nas condições meteorológicas, e, por fim, nos limites de velocidade (feature selection). Foi utilizada como variável alvo a gravidade dos ferimentos.

Em consequência ao grande desbalanceamento de classes (uma limitação) que a base de dados apresenta, foram efetuadas múltiplas tentativas de desenvolvimento de sistemas inteligentes diferentes, usando métodos de Árvore de Decisão, Floresta Aleatória e Rede Neural. Apesar de ajustes e modificações nos códigos, todos os modelos apresentaram resultados de baixa precisão, recall e acurácia, especialmente para a classe 2, slight, a classe majoritária. Isso indica que nenhum modelo foi capaz de apresentar um desempenho ideal para responder à pergunta, dificultando uma conclusão vantajosa para o projeto. Em contrapartida, é possível assegurar que qualquer algoritmo pode ser aperfeiçoado — sempre há possibilidade de melhoria e consequente retorno positivo.

# REFERÊNCIAS


**[1]** - _NEXTMILLIONAIRE. **Car Accident Dataset**. Disponível em: https://www.kaggle.com/datasets/nextmillionaire/car-accident-dataset. Acesso em: 10 mar. 2024._

**[2]** - _ORGANIZAÇÃO PAN-AMERICANA DA SAÚDE. **Segurança no trânsito**. Disponível em: https://www.paho.org/pt/topicos/seguranca-no-transito#:~:text=90%25%20das%20mortes%20no%20trânsito,são%20pedestres%2C%20ciclistas%20e%20motociclistas. Acesso em: 15 mar. 2024._

**[3]** - _OPENAI. **ChatGPT**: Conversational AI model. Disponível em: https://www.openai.com/chatgpt. Acesso em: 29 jun. 2024._


# APÊNDICES

**Links:**

Do código (armazenado no repositório):
https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability.git

Dos artefatos (armazenado do repositório):
https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/48fe58c2c6aaa8ed8ffb4f8af143fabe2cf4648c/assets/README.md

Da apresentação final (armazenado no repositório):
<iframe src="https://1drv.ms/p/c/eba5f480b87391fa/IQPQv5xDsI33RLeycuvUnOCeAd3lBTNor7BVgP7aZBq0i5w?em=2&amp;wdAr=1.7777777777777777" width="476px" height="288px" frameborder="0">Este é um apresentação do <a target="_blank" href="https://office.com">Microsoft Office</a> incorporado, da plataforma <a target="_blank" href="https://office.com/webapps">Office</a>.</iframe>

Do vídeo de apresentação (armazenado no repositório):




