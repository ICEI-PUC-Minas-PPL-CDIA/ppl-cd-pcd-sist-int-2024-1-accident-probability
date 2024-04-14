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

Agências de seguros: Que tem como objetivo utilizar os dados, fornecidos para melhor escolha de preço, de acordo com a região de vias de maior ou menor risco.


Governo Público: Têm como função guiar para o reparo ou manutenção da via, diminuindo o risco de acidentes, ocasionandos em determinados trechos das vias.


## Análise exploratórida dos dados

###    Dicionário de dados

BASE DE DADOS : Acidentes rodoviários

FONTE: Kaggle

|   Variáveis   | Tipo de dado  |                      Descrição                                    |
| ------------- | ------------- |------------------------------------------------------------       |
|   índice_coli |   numérico    |    Um identificador exclusivo para cada acidente relatado         |
|   ano_colisão |   data        |    Ano em que ocorreu o acidente                                  |
|   ref_acident |   numérico    |    Um número de referência associado ao acidente                  | 
|   veic_refe   |   numérico    |    Número de referência do veículo envolvido no acidente          | 
|   ref_casual  |   numérico    |    Um número de referência da vítima envolvida no acidente        |
|   clas_viti   |   categórico  |    Indica a classe da vítima (ex: motorista, passageiro, pedestre)|
|   sexo        |   textual     |    O sexo da vítima (masculino ou feminino)			    |
|   idade       |   numérico    |    A idade da vítima						    |
|   faix_etar   |   numérico    |    Faixa etária a que pertence a vítima (ex.: 0-5, 6-10, 11-15)    |
|   grav_ferim  |   categórico  |    A gravidade dos ferimentos da vítima (por exemplo, fatal, grave,leve)|
|   loca_pedes  |   numérico    |    Localizção do pedrestre no momento do acidente 	            |
|   mov_pedes   |   numérico    |    Movimentação do pedrestre durante o acidente 		    |
|   passa_car   |   categórico  |    Indica se o acidentado era passageiro do carro no momento do acidente|
|   pass_onib   |   categórico  |    Indica se a vítima foi um passageiro de ônibus ou ônibus (sim ou não)|
|   traba_rodov |   categórico  |    Indica se o acidentado era trabalhador de manutenção rodoviária (sim ou não)|
|   tipo_vitim  |   categórico  |    O tipo de vítima (por exemplo, motorista/passageiro, passageiro, pedestre)|
|   resid_vitim |   categórico  |    O tipo de área em que a vítima reside (por exemplo, urbana, rural)|
|   decil_IMD   |   numérico    |    O decil IMD da área onde reside a vítima (uma medida de privação)|
|   LSOA        |   numérico    |    A Área de Super Saída da Camada Inferior (LSOA) associada à localização da vítima|


O gráfico mostra a severidade das lesões e danos experimentados pelos indivíduos envolvidos nos acidentes de carro retratados na nossa base de dados. A gravidade é categorizada como 1- ferimentos leves, 2- ferimentos graves ou 3- mortes.


###    Descrição de dados

• Dados Numéricos:

• Localização do pedestre no momento do acidente: Este dado fornece a localização do pedestre no momento do acidente.

• Faixa etária a que pertence a vítima: Indica em qual faixa etária a vítima se enquadra.

• Número de referência do veículo envolvido no acidente: Identifica o veículo envolvido no acidente.

• Dados Categóricos:

• Tipo de área em que a vítima reside: Categoriza se a área da residência da vítima é urbana ou rural.

• Tipo de vítima: Descreve se a vítima é motorista/passageiro, passageiro ou pedestre.

• Indica se a vítima foi um passageiro de ônibus ou ônibus: Indica se a vítima estava envolvida em um acidente de ônibus.

• A gravidade dos ferimentos da vítima: Categoriza os ferimentos da vítima em fatal, grave ou leve.

• Indica a classe da vítima: Define a classe da vítima, como motorista, passageiro ou pedestre.

• Dados Textuais:

• Sexo da vítima: Indica o sexo da vítima, masculino ou feminino.

|   Variáveis   | Tipo de dado  |                      Descrição                                    |
| ------------- | ------------- |------------------------------------------------------------       |
|   ano_colisão |   data        |    Ano em que ocorreu o acidente                                  |
|   veic_refe   |   numérico    |    Número de referência do veículo envolvido no acidente          | 
|   clas_viti   |   categórico  |    Indica a classe da vítima (ex: motorista, passageiro, pedestre)|
|   sexo        |   textual     |    O sexo da vítima (masculino ou feminino)			    |
|   faix_etar   |   numérico    |    Faixa etária a que pertence a vítima (ex.: 0-5, 6-10, 11-15)    |
|   grav_ferim  |   categórico  |    A gravidade dos ferimentos da vítima (por exemplo, fatal, grave,leve)|
|   loca_pedes  |   numérico    |    Localizção do pedrestre no momento do acidente 	            |
|   pass_onib   |   categórico  |    Indica se a vítima foi um passageiro de ônibus ou ônibus (sim ou não)|
|   tipo_vitim  |   categórico  |    O tipo de vítima (por exemplo, motorista/passageiro, passageiro, pedestre)|
|   resid_vitim |   categórico  |    O tipo de área em que a vítima reside (por exemplo, urbana, rural)|

### Distribuição por gravidade   

![__results___10_0](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/160488415/3340d31e-ff3a-4329-9bd5-e4d0c0324037)

### Distribuição por idade

![__results___10_2](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/160488415/9a11b5b0-e1bc-4940-9a06-94bc63ba59ea)

### Distribuição por sexo

![__results___12_0](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/160488415/8ae1c17e-68e9-435c-b53e-39c289737899)

### Distribuição por classe da vítima

![__results___13_0](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/160488415/106dc7ff-06fc-4cae-8bb1-2a5cb90feaae)

### Distribuição por área de residência

![__results___14_0](https://github.com/ICEI-PUC-Minas-PPL-CD/probabilidade-de-acidentes/assets/160488415/96f6f9db-5510-4afe-b508-1aa1c074a473)


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




