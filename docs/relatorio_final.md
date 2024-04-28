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
Este trabalho tem como objetivo analisar e realizar um calculo de probabilidade de acidentes que uma certa via oferece, com base nas informações do condutor,condições da via etc..., utilizando modelos estatísticos. Foram coletados dados históricos da taxa de sinistros, bem como variáveis econômicas e sociais relevantes para a região. Utilizamos técnicas de análise de séries temporais e modelos de previsão, como ARIMA e modelos de regressão, para estimar uma probabilidade de um acidente ocorrer em detrimento de algumas condições. Com a breve analise na base de dados pode até se prever que a alta taxa de acidentes Brasil está correlacionado com variáveis como condições das vias, idade dos condutores,condição dos veículos. Com base nas previsões obtidas, foi possível identificar tendências e padrões que podem auxiliar na formulação de políticas públicas e estratégias para mitigar os acidentes em determinadas regiões.  


## Introdução

	Os acidentes nas rodovias representam um grave problema em todo o mundo, resultando em perdas humanas, danos materiais e impactos econômicos significativos. Nesse contexto, a aplicação de sistemas inteligentes e da análise dos dados através da ciência de dados, tem se mostrado uma abordagem promissora para a prevenção e da diminuição extrema desses acidentes. A capacidade desses sistemas de coletar, processar e analisar grandes volumes de dados em tempo real, juntamente com a capacidade de tomar decisões autônomas e rápidas, torna-os ferramentas essenciais na busca por estratégias mais eficazes de segurança viária. Este trabalho tem como objetivo explorar o papel dos sistemas inteligentes na redução de acidentes nas rodovias, destacando suas potenciais contribuições e desafios a serem superados.  


###    Contextualização

	A crescente disponibilidade de dados e avanços tecnológicos tem permitido o desenvolvimento constante e exponencial no setor automobilístico, tanto para produção de automóveis cada vez mais eficazes e seguros, 
quanto para a conservação da própria segurança no trânsito. A aplicação da Ciência de Dados se mostra como uma ferramenta necessária para este projeto — com a capacidade de coletar, processar e analisar grandes 
volumes de dados, permite-se identificar padrões/correlações, e, assim, projetar medidas. Dessa forma, esse trabalho se propõe a explorar o uso de técnicas avançadas da análise exploratória de dados para 
compreender os motivos que incidem em acidentes rodoviários, de forma a prevê-los e possibilitar o melhoramento das vias e dos sistemas de transportes.  


###    Problema
	O problema que o agente pretende resolver é o alto índice de incidentes que uma certa via pode ter. Certas vias específicas enfrentam dificuldades com altas taxas de colisões, o que impacta diretamente a qualidade 
de vida da população, assim gerando um aumento da mortalidade e no impacto emocional dos indivíduos. De acordo com o PAHO (Pan American Health Organization), "90% das mortes no trânsito ocorrem em países de baixa e 
média renda. Os acidentes nas vias custam aos países cerca de 3% de seus produtos internos brutos. Quase metade (49%) das pessoas que morrem nas vias em todo o mundo são pedestres, ciclistas e motociclistas.":  
https://www.paho.org/pt/topicos/seguranca-no-transito#:~:text=90%25%20das%20mortes%20no%20trânsito,são%20pedestres%2C%20ciclistas%20e%20motociclistas.  

	Essa circunstância revela uma série de desafios, que são: segurança no trânsito, dificultando a segurança de todos os usuários das vias, incluindo pedestres, ciclistas, motociclistas e motoristas. E também na falta
de infraestrutura, muitas regiões enfrentam desafios relacionados à falta de investimento em infraestrutura, estradas mal conservadas, falta de sinalização adequada e projetos viários inadequados.  


###    Objetivo geral

	Analisar acidentes nas vias, identificar tendências e extrair informações para implementação de medidas de segurança, necessárias para reduzir o número de vítimas de tais imprudências.  

####    Objetivos específicos

• Identificar os principais centros urbanos que apresentam um aumento significativo em acidentes de tráfego;    
• Analisar os dados estatísticos relacionados ao incidentes em estradas em cada um dos centros urbanos identificados;  
• Comparar e contrastar os dados obtidos sobre os acidentes, as condições climáticas e os fatores humanos como: fadiga, psicológico, etc;  
• Propor recomendações para políticas sociais ou intervenções na segurança pública visando mitigar os efeitos negativos dessas correlações na sociedade;  
• Impulsionar um aumento da qualidade de vida da população através de iniciativas abrangentes em áreas da segurança, educação, habitação e bem-estar social.  


###    Justificativas

	A probabilidade de acidentes como tema de estudo é crucial em diversos setores, permitindo avaliar riscos e adotar medidas preventivas. Essa análise não só compreende os potenciais perigos em atividades e ambientes, mas também direciona a implementação de protocolos de segurança eficazes. Ao quantificar a probabilidade de acidentes, é possível identificar áreas vulneráveis, priorizar investimentos em segurança e reduzir eventos indesejados. Integrar essa probabilidade em análises de risco permite decisões mais embasadas, promove uma cultura preventiva e valoriza o bem-estar de todos. Assim, a consideração da probabilidade de acidentes não apenas preserva vidas e recursos, mas também fortalece a sustentabilidade e a eficiência operacional a longo prazo.


##    Público alvo

- Agências de seguros: Que tem como objetivo utilizar os dados, fornecidos para melhor escolha de preço, de acordo com a região de vias de maior ou menor risco.
- Governo Público: Têm como função guiar para o reparo ou manutenção da via, diminuindo o risco de acidentes, ocasionandos em determinados trechos das vias.


## Análise exploratórida dos dados

###    Dicionário de dados

BASE DE DADOS : Acidentes rodoviários

FONTE: Kaggle

Este conjunto de dados fornece registos detalhados dos acidentes rodoviários ocorridos durante o mês de janeiro de 2021. Ele inclui informações como a data do acidente, dia da semana, controle de cruzamento, gravidade do acidente, coordenadas geográficas, condições de iluminação e clima, detalhes do veículo e muito mais. Os dados são valiosos para analisar e compreender os fatores que contribuem para os acidentes de trânsito nessa área urbana, auxiliando no desenvolvimento de estratégias para a melhoria da segurança viária.

|   Variáveis   | Tipo de dado  |                      Descrição                                    |
| ------------- | ------------- |------------------------------------------------------------       |
|Accident_Index |   categórico    |   Um identificador exclusivo para cada registro de acidente.      |
|Accident Date  |   numérico        | A data em que ocorreu o acidente (formato: DD/MM/AAAA).     |
|Day_of_Week    |   categórico    | O dia da semana em que ocorreu o acidente.                     | 
|Junction_Control |   textual   | Descreve o tipo de controle de cruzamento no local do acidente (por exemplo, "Ceder ou descontrolado").    | 
|Junction_Detail  |   textual    | Fornece detalhes adicionais sobre o cruzamento onde ocorreu o acidente (por exemplo, "T ou cruzamento escalonado").    |
|Accident_Severity|   categórico  | Indica a gravidade do acidente (ex.: “Grave”). |
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

- Accident Date - A data em que ocorreu o acidente (formato: DD/MM/AAAA).
- Latitude - A latitude geográfica do local do acidente.
- Longitude - A longitude geográfica do local do acidente.
- Number_of_Casualties - O número total de vítimas envolvidas no acidente.  		    
- Number_of_Vehicles - O número total de veículos envolvidos no acidente. 
- Speed_limit - O limite de velocidade aplicável à estrada onde ocorreu o acidente.
- Time - A hora do dia em que ocorreu o acidente (formato: HH:MM).

• DADOS CATEGÓRICOS:

- Accident_Index - Um identificador exclusivo para cada registro de acidente.
- Day_of_Week - O dia da semana em que ocorreu o acidente.
- Accident_Severity - Indica a gravidade do acidente (ex.: “Grave”).
- Light_Conditions - Descreve as condições de iluminação no momento do acidente (por exemplo, "Luz do dia").
- Carriageway_Hazards - Descreve quaisquer perigos presentes na faixa de rodagem no momento do acidente (por exemplo, "Nenhum").
- Road_Surface_Conditions - Descreve as condições da superfície da estrada no momento do acidente (por exemplo, "Seca").    
- Road_Type - Especifica o tipo de estrada onde ocorreu o acidente (por exemplo, “Rua de mão única”). 
- Urban_or_Rural_Area - Indica se o acidente ocorreu em área urbana ou rural. 
- Weather_Conditions - Descreve as condições meteorológicas no momento do acidente (por exemplo, "Bom, sem ventos fortes").   
- Vehicle_Type - especifica o tipo de veículo envolvido no acidente (por exemplo, "Carro", "Táxi/Carro de aluguel particular").  

• DADOS TEXTUAIS:

- Junction_Control - Descreve o tipo de controle de cruzamento no local do acidente (por exemplo, "Ceder ou descontrolado").            
- Junction_Detail - Fornece detalhes adicionais sobre o cruzamento onde ocorreu o acidente (por exemplo, "T ou cruzamento escalonado").
- Local_Authority_(District) - O distrito da autoridade local onde ocorreu o acidente.
- Police_Force - A força policial que tratou do acidente. 


|   Variáveis   | Tipo de dado  |                      Descrição                                    |
| ------------- | ------------- |------------------------------------------------------------       |
|Accident_Index |   categórico    |   Um identificador exclusivo para cada registro de acidente.      |
|Accident Date  |   numérico        | A data em que ocorreu o acidente (formato: DD/MM/AAAA).                 |
|Day_of_Week    |   categórico    | O dia da semana em que ocorreu o acidente.                     | 
|Junction_Detail  |   textual    | Fornece detalhes adicionais sobre o cruzamento onde ocorreu o acidente (por exemplo, "T ou cruzamento escalonado").          |
|Accident_Severity|   categórico  | Indica a gravidade do acidente (ex.: “Grave”). |
|Light_Conditions |   categórico    | Descreve as condições de iluminação no momento do acidente (por exemplo, "Luz do dia"). |
|Number_of_Casualties  |   numérico    | O número total de vítimas envolvidas no acidente.  	    |
|Number_of_Vehicles   |   numérico  | O número total de veículos envolvidos no acidente.  |
|Road_Surface_Conditions |   categórico  | Descreve as condições da superfície da estrada no momento do acidente (por exemplo, "Seca").    |
|Road_Type |   categórico  |  Especifica o tipo de estrada onde ocorreu o acidente (por exemplo, “Rua de mão única”).  |
|Speed_limit |   numérico  | O limite de velocidade aplicável à estrada onde ocorreu o acidente. |
|Time  |   numérico    |  A hora do dia em que ocorreu o acidente (formato: HH:MM).  |
|Urban_or_Rural_Area  |   categórico    | Indica se o acidente ocorreu em área urbana ou rural. |
|Weather_Conditions  |   categórico    | Descreve as condições meteorológicas no momento do acidente (por exemplo, "Bom, sem ventos fortes").   |
|Vehicle_Type  |   categórico    | especifica o tipo de veículo envolvido no acidente (por exemplo, "Carro", "Táxi/Carro de aluguel particular").  |


### A distribuição dos acidentes com base nas condições do pavimento rodoviário

![__results___13_1](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/164661514/6b98ebd9-0819-4ab6-837a-0af0c67355b3)

### Gráfico de pizza para exibir a porcentagem de acidentes por dia

![__results___14_1](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/164661514/8ebc4c74-b9f8-498e-a013-ad33a48d00f6)

### Gráfico de barras para exibir o número de acidentes por hora no dia

![__results___15_1](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/164661514/85baefb2-dbd8-402f-93e6-4d47cd0adaa4)

### Acidente por tipo de veículo & Acidente por condição de luz

![__results___16_0](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/164661514/5ff309bc-a41e-4f6c-b2c7-1acc8bc0dc8f)

### Gráfico de linhas para calcular a porcentagem de acidentes para cada data

![__results___17_2](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/164661514/946aa34d-4798-4c30-a551-357f1e29cdba)

### Gráfico de contagem para mostrar o número de acidentes por Accident_Severity

![__results___18_1](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/164661514/f6801c2e-6f0e-455f-a186-12b1ab498bb8)

### Gráfico de barras para mostrar qual é o limite de velocidade de acidente mais comum

![__results___19_1](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/164661514/b9241252-f1f1-4df7-869a-3ab08034896d)

### Contagem de acidentes por cruzamento para cada dia da semana

![__results___20_1](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/164661514/b79c6574-5c0c-4645-b1cf-509e61025520)

### Preparação dos dados

## Indução de modelos

### Modelo 1: Algoritmo

Substitua o título pelo nome do algoritmo que será utilizado. P. ex. árvore de decisão, rede neural, SVM, etc.
Justifique a escolha do modelo.
Apresente o processo utilizado para amostragem de dados (particionamento, cross-validation).
Descreva os parâmetros utilizados. 
Apresente trechos do código utilizado comentados. Se utilizou alguma ferramenta gráfica, apresente imagens
com o fluxo de processamento.

### Modelo 2: Algoritmo

Repita os passos anteriores para o segundo modelo.


## Resultados

### Resultados obtidos com o modelo 1.

Apresente aqui os resultados obtidos com a indução do modelo 1. 
Apresente uma matriz de confusão quando pertinente. Apresente as medidas de performance
apropriadas para o seu problema. 
Por exemplo, no caso de classificação: precisão, revocação, F-measure, acurácia.

### Interpretação do modelo 1

Apresente os parâmetros do modelo obtido. Tentre mostrar as regras que são utilizadas no
processo de 'raciocínio' (*reasoning*) do sistema inteligente. Utilize medidas como 
o *feature importances* para tentar entender quais atributos o modelo se baseia no
processo de tomada de decisão.


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




