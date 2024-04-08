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





###    Descrição de dados

Dado Numérico: Idade da População de uma Região 

• Média: Calculo a média das idades da população. 

• Desvio Padrão: Determino o grau de dispersão das idades em relação à média. 

• Mínimo e Máximo: Identifico a idade mínima e máxima da população. 

• Quartis: Divido as idades em quartis para entender a distribuição. 

• Histograma: Represento graficamente a distribuição das idades. 

Dado Numérico: Quantidade de Habitantes de uma Região ou Estado 

• Média: Calculo a média da quantidade de habitantes. 

• Desvio Padrão: Determino o grau de dispersão da quantidade de habitantes em relação à média. 

• Mínimo e Máximo: Identifico a menor e a maior quantidade de habitantes. 

• Quartis: Divido a quantidade de habitantes em quartis para entender a distribuição. 

• Histograma: Represento graficamente a distribuição da quantidade de habitantes. 

Dado de Data: Data da Coleta dos Dados 

• Não é possível calcular estatísticas descritivas com uma única data, mas podemos verificar o intervalo de tempo abrangido pelos dados. 

Dados Categóricos: Principal Fonte de Renda de uma Região e Nível de Formação da População 

• Moda: Identifico a principal fonte de renda e o nível de formação mais comuns na região. 

• Quantidade de Valores Distintos: Conto o número de diferentes fontes de renda e níveis de formação. 

• Distribuição das Categorias: Represento graficamente a frequência de cada fonte de renda e nível de formação.

## Preparação dos dados


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




