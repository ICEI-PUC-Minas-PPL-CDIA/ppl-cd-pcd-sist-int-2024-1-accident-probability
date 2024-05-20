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


## Análise exploratórida dos dados

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


### Distribuição da quantidade de acidentes por dia:

![__results___13_1](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/main/docs/imagens/graph%201.png)

### Distribuição da quantidade de acidentes por horas:

![__results___14_1](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/main/docs/imagens/graph%202.png)

### Distribuição de números e das porcentagens por dias de semana e fins-de-semanas:

![__results___15_1](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/main/docs/imagens/graph%203.png)

### Distribuição da quantidade por tipos de acidentes:

![__results___16_0](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/main/docs/imagens/graph%204.png)

### Distribuição por tipos de lesões:

![__results___17_2](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/main/docs/imagens/graph%205.png)

### Distribuição das top 10 causas dos acidentes:

![__results___18_1](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/main/docs/imagens/graph%206.png)


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

### Modelo 1: Árvore de Decisão

A Árvore de Decisão foi escolhida como nosso primeiro modelo induzido, visto sua habilidade em manipular dados não lineares, interações complexas (o impacto de uma variável pode variar dependendo dos valores de outras variáveis no modelo), e dados mistos (mistura de variáveis categóricas e numéricas).

Processo utilizado para amostragem de dados (explicado linha por linha).
[Processo do código](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/main/docs/Projeto_%C3%81rvoreDecis%C3%A3o.ipynb)

### Modelo 2: Rede Neural

A Rede Neural foi escolhida como nosso segundo modelo induzido, uma vez que, visando prever a gravidade dos ferimentos em acidentes rodoviários, é de notável relevância a sua capacidade de lidar com dados complexos, adaptar-se a diferentes tipos de dados e aprender a partir de grandes conjuntos de dados. 

Justifique a escolha do modelo.
Apresente o processo utilizado para amostragem de dados (particionamento, cross-validation).
Descreva os parâmetros utilizados. 
Apresente trechos do código utilizado comentados. Se utilizou alguma ferramenta gráfica, apresente imagens
com o fluxo de processamento.

## Resultados

### Resultados obtidos com o modelo 1.

#### Acurácia

Treinamento - Coeficiente de Determinação (R²): 0.9889122346333568 ≅ 98.89%  
Teste - Coeficiente de Determinação (R²): 0.9558860637331806 ≅ 95.55%  

MAE (Erro Médio Absoluto): 24.066471023556392 ≅ 24.07  
RMSE (Raiz do Erro Quadrático Médio): 46.11082794174601 ≅ 46.11  

##### Coeficiente de Determinação (R²):  

Este é um valor entre 0 e 1 que indica a proporção da variância na variável dependente que é previsível a partir das variáveis independentes. Um valor de 1 indica um ajuste perfeito, enquanto valores mais baixos indicam 
que o modelo explica menos variabilidade nos dados.  

No conjunto de treinamento, o R² é aproximadamente 0.989, o que indica que o modelo de Random Forest explica cerca de 98.9% da variabilidade nos dados de treinamento.  
No conjunto de teste, o R² é aproximadamente 0.956, o que significa que o modelo explica cerca de 95.6% da variabilidade nos dados de teste.  
Esses valores indicam que o modelo de Random Forest tem um desempenho bastante bom tanto no conjunto de treinamento quanto no conjunto de teste, mostrando uma capacidade de generalização satisfatória.  

##### MAE (Erro Médio Absoluto):  
 Este valor indica que, em média, as previsões do modelo estão desviando aproximadamente 24.07 unidades da quantidade real de incidentes.  

##### RMSE (Raiz do Erro Quadrático Médio):  
 Essa métrica é a raiz quadrada do erro médio dos quadrados das diferenças entre as previsões do modelo e as quantidades reais de incidentes. O valor de 46.11 indica que, em média, as previsões estão desviando 
aproximadamente 46.11 unidades da quantidade real de incidentes.  

Ambas as métricas são usadas para avaliar o quão bem o modelo está performando em termos de previsão, sendo que valores menores indicam melhor desempenho.  


### Interpretação do modelo 1

#### Árvore de Decisão

![arvore_decisao](https://github.com/ICEI-PUC-Minas-PPL-CD/ppl-cd-pcd-sist-int-2024-1-accident-probability/blob/main/docs/imagens/arvore%20decisao.png)

• Entropy: É a medida de impureza do nó, que indica quão bem as amostras são separadas em suas classes. Quanto menor a entropia, mais puras são as amostras  

• Samples: Mostra o número de amostras no nó.  

• Value:  Mostra a distribuição das classes no nó. Por exemplo, [0.791, 0.826, 0.842] significa que 79.1% das amostras são da classe 'Fatal', 82.6% são da classe 'Serious' e 84.2% são da classe 'Slight'.  

As linhas subsequentes mostram as divisões adicionais e os nós subsequentes na árvore, seguindo o mesmo padrão.  

##### Interpretação 

• A primeira divisão dos dados é feita com base na feature '0-3' (0-3 horas do acidente), onde o valor é menor ou igual a 0.5.  

• Se o valor da feature '0-3' for menor ou igual a 0.5, o sistema classifica a amostra como 'Fatal' e continua a avaliação dos outros nós.  

• Se o valor da feature '0-3' for maior que 0.5, o sistema passa para o próximo nível de decisão.  

##### Raciocínio do Sistema Inteligente:

• O sistema inteligente começa avaliando se o acidente ocorreu nas primeiras 3 horas do dia.  

• Se sim (TRUE), o sistema classifica o acidente como 'Fatal' com base na alta probabilidade (79.1%) de lesões fatais nesse intervalo de tempo (18-21 horas).  

• Se não (FALSE), o sistema classifica o acidente como 'Slight' com base na distribuição de probabilidade das lesões em um intervalo de tempo diferente.  

##### Regras Utilizadas no Raciocínio:

• Se '0-3h' <= 0.5, classificar como 'Fatal'.  
• Se '0-3h' > 0.5, verificar a condição '18-21h' <= 0.5.  
• Se '18-21h' <= 0.5, classificar como 'Fatal'.  
• Se '18-21h' > 0.5, classificar como 'Slight'.  

### Resultados obtidos com o modelo 2.

Repita o passo anterior com os resultados do modelo 2.

### Interpretação do modelo 2

Repita o passo anterior com os parâmetros do modelo 2.


## Análise comparativa dos modelos

Discuta sobre as forças e fragilidades de cada modelo. Exemplifique casos em que um
modelo se sairia melhor que o outro. Nesta seção é possível utilizar a sua imaginação
e extrapolar um pouco o que os dados sugerem.


### Distribuição do modelo (opcional)

Tende criar um pacote de distribuição para o modelo construído, para ser aplicado 
em um sistema inteligente.


## 8. Conclusão

Apresente aqui a conclusão do seu trabalho. Discussão dos resultados obtidos no trabalho, 
onde se verifica as observações pessoais de cada aluno.

Uma conclusão deve ter 3 partes:

   * Breve resumo do que foi desenvolvido
	 * Apresenação geral dos resultados obtidos com discussão das vantagens e desvantagens do sistema inteligente
	 * Limitações e possibilidades de melhoria


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




