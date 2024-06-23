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
Este trabalho tem como objetivo analisar e realizar um calculo de probabilidade de acidentes que uma certa via oferece, com base nas informações do condutor, condições da via etc..., utilizando modelos estatísticos. Foram coletados dados históricos da taxa de sinistros, bem como variáveis econômicas e sociais relevantes para a região. Utilizamos técnicas de análise de séries temporais e modelos de previsão, como ARIMA e modelos de regressão, para estimar uma probabilidade de um acidente ocorrer em detrimento de algumas condições. Com a breve análise na base de dados, pode-se prever que a alta taxa de acidentes está correlacionado com variáveis como condições das vias e condições do dia. Com base nas previsões obtidas, foi possível identificar tendências e padrões que podem auxiliar na formulação de políticas públicas e estratégias para mitigar os acidentes nas vias em evidência.  


## Introdução

   Os acidentes nas rodovias representam um grave problema em todo o mundo, resultando em perdas humanas, danos materiais e impactos econômicos significativos. Nesse contexto, a aplicação de sistemas inteligentes e da análise dos dados através da ciência de dados tem se mostrado uma abordagem promissora para a prevenção e diminuição extrema desses acidentes. A capacidade desses sistemas de coletar, processar e analisar grandes volumes de dados em tempo real, juntamente com a capacidade de tomar decisões autônomas e rápidas, torna-os ferramentas essenciais na busca por estratégias mais eficazes de segurança viária. Este trabalho tem como objetivo explorar o papel dos sistemas inteligentes na redução de acidentes nas rodovias, destacando suas potenciais contribuições e desafios a serem superados.  


###    Contextualização

   A crescente disponibilidade de dados e avanços tecnológicos tem permitido o desenvolvimento constante e exponencial no setor automobilístico, tanto para produção de automóveis cada vez mais eficazes e seguros, quanto para a conservação da própria segurança no trânsito. A aplicação da Ciência de Dados se mostra como uma ferramenta necessária para este projeto — com a capacidade de coletar, processar e analisar grandes volumes de dados, permite-se identificar padrões/correlações, e, assim, projetar medidas. Dessa forma, esse trabalho propõe explorar o uso de técnicas avançadas da análise exploratória de dados para 
compreender os motivos que incidem em acidentes rodoviários, de forma a prevê-los e possibilitar o melhoramento das vias e dos sistemas de transportes.  


###    Problema
   O problema que o agente pretende resolver é o alto índice de incidentes que uma certa via pode ter. Certas vias específicas enfrentam dificuldades com altas taxas de colisões, o que impacta diretamente a qualidade de vida da população, gerando, assim, um aumento da mortalidade e do impacto emocional nos indivíduos. De acordo com o PAHO (Pan American Health Organization), "90% das mortes no trânsito ocorrem em países de baixa e média renda. Os acidentes nas vias custam aos países cerca de 3% de seus produtos internos brutos. Quase metade (49%) das pessoas que morrem nas vias em todo o mundo são pedestres, ciclistas e motociclistas.":  
https://www.paho.org/pt/topicos/seguranca-no-transito#:~:text=90%25%20das%20mortes%20no%20trânsito,são%20pedestres%2C%20ciclistas%20e%20motociclistas.  

   Essa circunstância revela uma série de desafios, entre eles: segurança no trânsito, dificultando a segurança de todos os usuários das vias, incluindo pedestres, ciclistas, motociclistas e motoristas. E também na falta de infraestrutura, muitas regiões enfrentam desafios relacionados à falta de investimento em infraestrutura, estradas mal conservadas, falta de sinalização adequada e projetos viários inadequados.  


###    Objetivo geral

   Analisar acidentes em certas vias, identificar tendências e extrair informações para implementação de medidas de segurança, necessárias para reduzir o número de vítimas de tais imprudências.  

####    Objetivos específicos

• Identificar os principais motivos para a causa de acidentes de tráfego em um certo lugar;

• Analisar os dados estatísticos relacionados aos incidentes;

• Comparar e contrastar os dados obtidos sobre os acidentes, como o horário do dia, o dia da semana, o tipo de veículo envolvido no acidente, as condições das vias, as condições climáticas, etc.;

• Propor recomendações para políticas sociais ou intervenções na segurança pública visando mitigar os efeitos negativos dessas correlações na sociedade;  

• Impulsionar um aumento da qualidade de vida da população através de iniciativas abrangentes em áreas da segurança, educação, habitação e bem-estar social.  


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

## Indução de modelos

### Modelos 1, 2, 3, 4, 5: Árvore de Decisão

A Árvore de Decisão foi escolhida como nosso primeiro modelo induzido, visto sua habilidade em manipular dados não lineares, interações complexas (o impacto de uma variável pode variar dependendo dos valores de outras variáveis no modelo), e dados mistos (mistura de variáveis categóricas e numéricas).

Processo utilizado para amostragem de dados 1 (explicado linha por linha):
[Processo do código](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/main/docs/decisiontree.ipynb)

Processo utilizado para amostragem de dados 2 (explicado linha por linha):


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

Justifique a escolha do modelo.
Apresente o processo utilizado para amostragem de dados (particionamento, cross-validation).
Descreva os parâmetros utilizados. 
Apresente trechos do código utilizado comentados. Se utilizou alguma ferramenta gráfica, apresente imagens
com o fluxo de processamento.

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

#### Estrutura da Árvore de Decisão  

##### Nó Raiz  
• Junction_Detail_Not at junction or within 20 metres <= 0.5  
• Gini: 0.251  
• Samples: 165373  
• Value: [33424, 34646, 223783]  
• Class = Slight  

Este nó raiz indica que a árvore inicialmente divide os dados com base em se o acidente ocorreu em um cruzamento ou não (ou dentro de 20 metros de um cruzamento). Se for verdadeiro (<= 0.5), vá para a esquerda, caso contrário, vá para a direita.  

##### Nível 1  
• Esquerda: Junction_Detail_T or staggered junction <= 0.5  
• Gini: 0.222  
• Samples: 92922  
• Value: [12631, 84662, 137175]  
• Class = Slight  

Esta divisão é feita com base em se o acidente ocorreu em uma junção em T ou em uma junção escalonada. Se for verdadeiro, vá para a esquerda, caso contrário, vá para a direita.  

##### Direita:  
• Gini: 0.294  
• Samples: 66512  
• Value: [2079, 16184, 86608]  
• Class = Slight  

Aqui, a árvore lida com acidentes que não ocorreram em um cruzamento (ou não estão dentro de 20 metros de um cruzamento).  

##### Nível 2 (Esquerda)  
• Esquerda: Junction_Detail_More than 4 arms (not roundabout) <= 0.5  
• Gini: 0.223  
• Samples: 32699  
• Value: [451, 6902, 45133]  
• Class = Slight  

A divisão considera se a junção tem mais de 4 braços (não uma rotatória). Se for verdadeiro, vá para a esquerda, caso contrário, vá para a direita.  

##### Direita:  
• Gini: 0.238  
• Samples: 51838  
• Value: [731, 10468, 70744]  
• Class = Slight  

Esta parte da árvore trata dos acidentes em junções com T ou junções escalonadas.  

##### Nível 3 (Esquerda)  
• Esquerda: Junction_Detail_Mini-roundabout <= 0.5  
• Gini: 0.225  
• Samples: 30513  
• Value: [433, 5727, 42066]  
• Class = Slight  

A árvore agora está lidando com junções com mais de 4 braços que não são rotatórias. Este nó verifica se é uma mini-rotatória.  

##### Direita:  
• Gini: 0.198  
• Samples: 2186  
• Value: [118, 365, 3067]  
• Class = Slight  

Este nó cobre acidentes em junções com mais de 4 braços.  

##### Nível 4 (Esquerda)  
• Esquerda: Junction_Detail_Private drive or entrance <= 0.5  
• Gini: 0.229  
• Samples: 2864  
• Value: [421, 5497, 39467]  
• Class = Slight  

Este nó verifica se a junção inclui uma entrada privada ou de garagem.  

##### Direita:  
• Gini: 0.157  
• Samples: 1829  
• Value: [12, 230, 2599]  
• Class = Slight  

Este nó cobre mini-rotatórias.  

##### Continuação  
A árvore continua dividindo os dados com base em outras características de junção até chegar a nós folha que indicam a classificação final.  

##### Interpretação Geral  
A árvore de decisão está utilizando várias características relacionadas a detalhes de junção para prever a gravidade do acidente. Cada nó faz uma decisão binária baseada em uma característica específica e os dados são 
divididos de acordo com essas decisões. A profundidade da árvore e a complexidade das ramificações indicam que muitos fatores de junção diferentes estão sendo considerados para classificar os acidentes como leves, graves 
ou fatais.  

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

Como dito anteriormente, fizemos com base em 3 tipos diferentes de métodos, e 7 modelos: os modelos de 1 a 5 foram feitos com base em decision tree (árvore de decisão), sendo o mais simples pensado capaz de executar a tarefa, feitos de forma frangmentada que, após isso, se complementam e foram unificados em uma única árvore. O modelo 6 foi feito com random forest (floresta aleatória), sendo uma variação mais complexa da primeira, utilizando de várias árvores geradas aleatoriamente de acordo com os dados fornecidos para interpretar e chegar a um resultado e, por fim o 7, feito com o método de rede neural, que simula a partir de uma matriz de confusão o funcionamento do cérebro humano para processar as informações, tendo uma capacidade por vezes maior que a random forest. Obviamente, não pode-se generalizar sobre qual é o melhor ou pior método, pois em outros casos, pode ser que um seja mais útil que outro, que talvez não serviria ou demoraria muito mais para a situação.

Comparando por método, analisando-os por completo, podemos ver que, a partir dos resultados obtidos, o modelo mais preciso foi a rede neural, devido à sua acurácia ser a maior dentre os modelos criados, pois apresenta um valor mais crível para sistemas inteligentes, com 63% de acurácia, sem desconsiderar nenhum dado fornecido ao sistema e mantendo certa consistência em seus resultados, obtendo, nos recalls, 51% de acerto em fatal e 77% em slight, mas apenas 11% em serious. Em segundo lugar dentre os parâmetros de eficiência, se enquadra a random forest, que apresenta uma precisão e recall maiores que o resultado da árvore, tendo seus 59% de acurácia, porém baixa se comparado à rede neural. Esta, também analisando pelo recall, obteve 52% em fatal e 65% em slight, porém seguiu com serious sendo a menor taxa de acerto, com 19%. Assim, é possível definir que a decision tree não é capaz de processar os dados fornecidos e definir com qualidade e precisão os resultados a partir deles, tendo em vista sua acurácia final, e apesar de ser o que foi mais preciso nas classes de menor peso,não teve tanta diferença em relação aos outros, com 54% em fatal e 20% em serious, mas falhou na slight, com 57%.


Analisando por partes a árvore, cada modelo apresenta uma falha diferente, com o modelo 1 desconsiderando as classes fatal e serious e colocando as respostas apenas na de maior peso (slight), os modelos 2 e 3 tendo um desequilíbrio absurdo entre sua precisão e recall (1% para 27% em fatal, 13% para 70% em serious e 89% para 6% em slight no modelo 2, e 2% para 22% em fatal, 14% para 79% em serious e 90% para 11% em slight no modelo 3), e os modelos 4 e 5 sendo muito incisivos, definindo apenas os acidentes leves e fatais, desconsiderando totalmente os sérios. Dentre os modelos da árvore, o que apresentou maior precisão foi o modelo de número 5, com 67% de acurácia final, sendo maior até mesmo que o resultado da rede neural. Obteve 39% em fatal, menor que os 51% da rede neural, e 77% em slight, maior que os 71%. Estas falhas somadas culminam em um produto não tão agradável e que tende a aproximadamente 50% de falhas em seus testes, provando-se ineficiente para o caso em questão. Todos os modelos tiveram dificuldades devido ao desequilíbrio dos dados da base que, mesmo com oversampling e undersampling dos dados, estão numa escala desproporcional e desbalanceada, tendo a classe 2 (slight) quase 7 vezes mais que 1 (serious) e 70 vezes mais que 0 (fatal), e não conseguimos encontrar uma forma viável de balancear para obter melhores resultados.

## Ameaça a Validade

Interna: a ameaça à validade interna poderia surgir do viés nos dados coletados. Este viés pode ocorrer devido a falhas na precisão ou na integridade dos dados, influenciando negativamente a confiabilidade dos resultados. Além disso, a possibilidade de os dados coletados estarem modificados intencional ou acidentalmente representa uma ameaça significativa, comprometendo a precisão e a validade das conclusões do estudo. Essas questões destacam a importância da coleta cuidadosa e da verificação rigorosa dos dados para garantir a validade interna do projeto.

Externa: a ameaça à validade externa se manifesta quando os resultados não podem ser generalizados para todas as regiões devido a discrepâncias nas leis de trânsito, na infraestrutura rodoviária e nos comportamentos dos motoristas. Essas disparidades regionais podem limitar a aplicabilidade dos achados do estudo em contextos geográficos distintos, comprometendo a capacidade de extrapolação e ampliação dos resultados para uma escala mais ampla. Portanto, a consideração desses fatores é essencial para avaliar corretamente a validade externa do projeto e sua relevância em diferentes cenários rodoviários.

## Conclusão

Este trabalho teve como objetivo analisar e realizar um cálculo de probabilidade de acidentes que uma certa via oferece, com base nas informações do condutor, condições da via etc..., utilizando modelos estatísticos. Foram coletados dados históricos da taxa de sinistros, bem como variáveis econômicas e sociais relevantes para a região. Utilizamos técnicas de análise de séries temporais e modelos de previsão, como ARIMA e modelos de regressão, para estimar uma probabilidade de um acidente ocorrer em detrimento de algumas condições. Com a breve análise na base de dados, pode-se prever que a alta taxa de acidentes está correlacionado com variáveis como condições das vias e condições do dia. Com base nas previsões obtidas, foi possível identificar tendências e padrões que podem auxiliar na formulação de políticas públicas e estratégias para mitigar os acidentes nas vias em evidência. 

Os resultados obtidos apresentam através dos gráficos, diversos dados que propõem analisar os detalhes de variadas situações, como, distribuição de acidentes com base na gravidade dos ferimentos, distribuição de acidentes com base nas condições da superfície da estrada, distribuição de acidentes com base no tipo de estrada, distribuição de acidentes com base na área urbana ou rural, distribuição de acidentes com base na hora do acidente, distribuição de acidentes com base no tipo de junção, distribuição de acidentes com base nas condições meteorológicas, distribuição de acidentes com base nos limites de velocidade e distribuição de acidentes com base nas condições de luminosidade da semana.

A vantagem é a capacidade de apresentar os resultados obtidos a quem pode prevenir os acidentes, como, órgãos públicos, agentes de publicidade e jornais. A desvantagem é não apresentar dados 100% precisos. 
Limitação e possibilidade de melhoria podemos citar o desbalanceamento dos modelos e causando uma baixa acurácia  


# REFERÊNCIAS

Como um projeto de sistema inteligente não requer revisão bibliográfica, 
a inclusão das referências não é obrigatória. No entanto, caso você 
tenha utilizado referências na introdução ou deseje 
incluir referências relacionadas às tecnologias, padrões, ou metodologias 
que serão usadas no seu trabalho, relacione-as de acordo com a ABNT.

Verifique no link abaixo como devem ser as referências no padrão ABNT:

http://www.pucminas.br/imagedb/documento/DOC\_DSC\_NOME\_ARQUI20160217102425.pdf

Por exemplo:

**[1]** - _ELMASRI, Ramez; NAVATHE, Sham. **Sistemas de banco de dados**. 7. ed. São Paulo: Pearson, c2019. E-book. ISBN 9788543025001._

**[2]** - _COPPIN, Ben. **Inteligência artificial**. Rio de Janeiro, RJ: LTC, c2010. E-book. ISBN 978-85-216-2936-8._

**[3]** - _CORMEN, Thomas H. et al. **Algoritmos: teoria e prática**. Rio de Janeiro, RJ: Elsevier, Campus, c2012. xvi, 926 p. ISBN 9788535236996._

**[4]** - _SUTHERLAND, Jeffrey Victor. **Scrum: a arte de fazer o dobro do trabalho na metade do tempo**. 2. ed. rev. São Paulo, SP: Leya, 2016. 236, [4] p. ISBN 9788544104514._

**[5]** - _RUSSELL, Stuart J.; NORVIG, Peter. **Inteligência artificial**. Rio de Janeiro: Elsevier, c2013. xxi, 988 p. ISBN 9788535237016._



# APÊNDICES

**Colocar link:**

Do código (armazenado no repositório);

Dos artefatos (armazenado do repositório);

Da apresentação final (armazenado no repositório);

Do vídeo de apresentação (armazenado no repositório).




