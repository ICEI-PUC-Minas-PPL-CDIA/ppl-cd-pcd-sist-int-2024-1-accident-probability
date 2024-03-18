# Previsão de Desemprego 


Matheus Melo Couto, matheus.couto.1525924@sga.pucminas.br

Luan Inaibes Guimarães, liguimaraes@sga.pucminas.br

João Henrique Pereirinha Sorrentino, jhpsorrentino@sga.pucminas.br

Rafael Brandão de Oliveira, rafael.brandao@sga.pucminas.br

---

Professores:

hugodepaula


---

_Curso de Ciência de Dados, Unidade Praça da Liberdade_

_Instituto de Informática e Ciências Exatas – Pontifícia Universidade de Minas Gerais (PUC MINAS), Belo Horizonte – MG – Brasil_

---

Este trabalho teve como objetivo analisar e prever a taxa de desemprego em Minas Gerais, utilizando modelos estatísticos e econômicos. Foram coletados dados históricos da taxa de desemprego, bem como variáveis econômicas e sociais relevantes para a região. Utilizamos técnicas de análise de séries temporais e modelos de previsão, como ARIMA e modelos de regressão, para estimar a taxa de desemprego futura. Os resultados mostraram que o desemprego em Minas Gerais está correlacionado com variáveis como PIB, inflação e taxa de juros. Com base nas previsões obtidas, foi possível identificar tendências e padrões que podem auxiliar na formulação de políticas públicas e estratégias para mitigar o desemprego na região.

---


## Introdução

A taxa de desemprego é um indicador crucial que reflete a saúde econômica de uma região e o bem-estar de sua população. Em Minas Gerais, estado com uma economia diversificada e significativa contribuição para o cenário nacional, a questão do desemprego é de extrema relevância. Com o objetivo de compreender melhor esse cenário e fornecer insights para a formulação de políticas públicas e estratégias de desenvolvimento econômico, este trabalho se propõe a analisar e prever a taxa de desemprego em Minas Gerais.

Através da utilização de modelos estatísticos e econômicos, buscamos identificar os principais fatores que influenciam o desemprego na região e antecipar possíveis cenários futuros. Esta análise é fundamental para orientar decisões e ações que visem promover o crescimento econômico e o bem-estar social em Minas Gerais. 

###    Contextualização

A crescente disponibilidade de dados e avanços tecnológicos têm permitido a aplicação da ciência de dados em diversas áreas, incluindo a economia e o mercado de trabalho. No contexto de Minas Gerais, um estado com uma economia diversificada e uma população significativa, a análise preditiva do desemprego por meio de técnicas de ciência de dados se mostra como uma ferramenta poderosa para compreender e antecipar as tendências do mercado de trabalho. A capacidade de coletar, processar e analisar grandes volumes de dados permite identificar padrões, correlações e insights que podem ser fundamentais para a formulação de políticas públicas e estratégias de emprego. Neste sentido, este trabalho se propõe a explorar o uso de técnicas avançadas de ciência de dados para prever a taxa de desemprego em Minas Gerais, contribuindo assim para uma abordagem mais informada e eficaz na gestão do mercado de trabalho e no enfrentamento dos desafios econômicos e sociais da região.

###    Problema
O problema que meu agente pretende resolver é o alto índice de desemprego em Minas Gerais. A região enfrenta dificuldades com altas taxas de desemprego, o que impacta diretamente a qualidade de vida da população, gerando instabilidade econômica e social.

Esse cenário de desemprego gera desafios para os indivíduos em busca de oportunidades de trabalho e para as empresas que precisam encontrar profissionais qualificados para suas demandas. A aplicação será desenvolvida para ajudar a conectar de forma mais eficiente os profissionais desempregados com oportunidades de emprego disponíveis na região de Minas Gerais.

> **Links Úteis**:
> - [Objetivos, Problema de pesquisa e Justificativa](https://medium.com/@versioparole/objetivos-problema-de-pesquisa-e-justificativa-c98c8233b9c3)


###    Objetivo geral

Analisar uma possível correlação entre o aumento da população em condição de rua nos centros urbanos de Minas Gerais e o aumento no índice de desemprego, bem como no consumo de entorpecentes.

####    Objetivos específicos

• Identificar os principais centros urbanos de Minas Gerais que apresentam um aumento significativo na população em situação de rua.  
• Analisar os dados estatísticos relacionados ao índice de desemprego em cada um dos centros urbanos identificados.  
• Investigar os padrões e tendências do consumo de entorpecentes nas áreas urbanas selecionadas.  
• Comparar e contrastar os dados obtidos sobre a população em situação de rua, desemprego e consumo de drogas para encontrar correlações potenciais.  
• Propor recomendações para políticas públicas ou intervenções sociais visando mitigar os efeitos negativos dessas correlações na sociedade.  

###    Justificativas

Este projeto foi escolhido devido à urgente necessidade de compreender os complexos fenômenos associados ao aumento da população em situação de rua, desemprego e consumo de drogas em Minas Gerais. Seu propósito é 
desenvolver um sistema inteligente capaz de identificar padrões entre esses indicadores sociais, proporcionando uma ferramenta crucial para gestores públicos, pesquisadores e profissionais das áreas de assistência 
social, saúde e segurança pública. Baseado em dados estatísticos oficiais, relatórios de pesquisa e estudos relevantes, esse trabalho visa facilitar a formulação de políticas públicas eficazes para lidar com essas 
questões sociais complexas.

##    Público alvo

Gestores Públicos: Possuem familiaridade com políticas públicas, gestão de recursos e tomada de decisões estratégicas. Utilizam sistemas de informação para análise de dados e monitoramento de indicadores sociais. 
Podem ocupar cargos de liderança em órgãos governamentais, como secretarias de assistência social, saúde e segurança pública.  

Pesquisadores: Têm formação acadêmica em áreas como sociologia, economia ou ciência política, com experiência em análise de dados e métodos de pesquisa. Utilizam ferramentas estatísticas e software de análise de 
dados para realizar estudos e produzir relatórios. Podem atuar em instituições de pesquisa, universidades ou organizações não governamentais.  

Profissionais de Assistência Social, Saúde e Segurança Pública: Possuem conhecimento prático sobre as questões sociais abordadas, incluindo políticas de assistência social, saúde pública e segurança comunitária. 
Podem variar de acordo com a experiência individual, mas geralmente têm habilidades básicas no uso de sistemas de informação. Trabalham em equipes multidisciplinares e podem ter diferentes níveis de autoridade, 
dependendo da estrutura organizacional.  

Mapa de Stakeholders:

• Governo Estadual: Responsável pela coordenação de políticas públicas e alocação de recursos para enfrentar os problemas sociais.  
• Prefeituras Municipais: Implementam programas locais de assistência social, saúde e segurança pública.  
• Instituições de Pesquisa: Realizam estudos e fornecem análises críticas para embasar políticas e intervenções sociais.  
• Organizações Não Governamentais: Prestam assistência direta às pessoas em situação de rua e auxiliam na formulação de políticas públicas.  
• População em Situação de Rua: Representa o grupo mais afetado pelos problemas sociais em questão, e suas necessidades devem ser consideradas nas intervenções propostas.  

## Análise exploratórida dos dados

###    Dicionário de dados

Apresente uma descrição das bases de dados a serem utilizadas. 
Dicionários de dados devem conter as bases de dados, os nomes dos atributos 
com seu significado, seu tipo (inteiro, real, textual, categórico, etc).

Este projeto deve utilizar pelo menos duas fontes de dados. Uma fonte principal e 
uma fonte para enriquecimentos dos dados principais.


###    Descrição de dados

Utilize a análise descritiva baseada em estatística de primeira ordem para descrever os dados.
Como descrever dados numéricos: média, desvio padrão, mínimo, máximo, quartis, histograma, etc.
Como descrever dados qualitativos (categóricos): moda (valor mais frequente), quantidade de valores distintos (categorias), distribuição das categorias (histograma), etc.


## Preparação dos dados

A preparação dos dados consiste dos seguintes passos:

> - Seleção dos atributos
> - Tratamentos dos valores faltantes ou omissos: remoção, substituição, indução, etc.
> - Tratamento dos valores inconsistentes: conversão, remoção de dados duplicados, remoção ou tratamento de ouliers.
> - Conversão de dados: p. ex. numérico para categórico, categórico para binário, etc.


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




