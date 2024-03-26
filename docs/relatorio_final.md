# Previsão de Desemprego 


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
Este trabalho tem como objetivo analisar e prever a taxa de desemprego no Brasil, utilizando modelos estatísticos e econômicos. Foram coletados dados históricos da taxa de desemprego, bem como variáveis econômicas e sociais relevantes para a região. Utilizamos técnicas de análise de séries temporais e modelos de previsão, como ARIMA e modelos de regressão, para estimar a taxa de desemprego futura. Com a breve analise na base de dados pode até se prever que o desemprego no Brasil está correlacionado com variáveis como PIB, inflação e taxa de juros. Com base nas previsões obtidas, foi possível identificar tendências e padrões que podem auxiliar na formulação de políticas públicas e estratégias para mitigar o desemprego na região.


## Introdução

A taxa de desemprego é um indicador crucial que reflete a saúde econômica de uma região e o bem-estar de sua população. No Brasil, país com uma economia diversificada e significativa contribuição para o cenário internacional, a questão do desemprego é de extrema relevância. Com o objetivo de compreender melhor esse cenário e fornecer insights para a formulação de políticas públicas e estratégias de desenvolvimento econômico, este trabalho se propõe a analisar e prever a taxa de desemprego em nosso país .

Através da utilização de modelos estatísticos e econômicos, buscamos identificar os principais fatores que influenciam o desemprego nas regiões e antecipar possíveis cenários futuros. Esta análise poderá ser de grande contribuição para orientar decisões e ações que visem promover o crescimento econômico e o bem-estar social no Brasil. 


###    Contextualização

A crescente disponibilidade de dados e avanços tecnológicos têm permitido a aplicação da ciência de dados em diversas áreas, incluindo a economia e o mercado de trabalho. No contexto do Brasil, a análise preditiva do desemprego por meio de técnicas de ciência de dados se mostra como uma ferramenta poderosa para compreender e antecipar as tendências do mercado de trabalho. A capacidade de coletar, processar e analisar grandes volumes de dados permite identificar padrões, correlações e insights que podem ser fundamentais para a formulação de políticas públicas e estratégias de emprego. Neste sentido, este trabalho se propõe a explorar o uso de técnicas avançadas de ciência de dados para prever a taxa de desemprego no brasil, contribuindo assim para uma abordagem mais informada e eficaz na gestão do mercado de trabalho e no enfrentamento dos desafios econômicos e sociais de cada região.  


###    Problema
O problema que o agente pretende resolver é o alto índice de desemprego no Brasil. o país enfrenta dificuldades com altas taxas de desemprego, o que impacta diretamente a qualidade de vida da população, gerando instabilidade econômica e social. de acordo com o site Agência Brasil, "o país apresenta uma taxa de desocupação de 7,6% de sua população nacional." ou seja aproximadamente 8,3 milhões de pessoas.

Essa situação de desemprego apresenta uma série de desafios tanto para os indivíduos em busca de oportunidades de trabalho quanto para as empresas que necessitam encontrar profissionais qualificados para preencher suas demandas. Com altas taxas de desemprego, surge uma complexa rede de consequências, incluindo a redução do poder de compra, o aumento da insegurança financeira e a diminuição do investimento em educação e saúde.

FREITAS, bruno. Taxa de desemprego fica em 7,6% no trimestre encerrado em janeiro. Agência Brasil, 2024. Disponível em: <https://agenciabrasil.ebc.com.br/economia/noticia/2024-02/taxa-de-desemprego-fica-em-76-no-trimestre-encerrado-em-janeiro#:~:text=A%20taxa%20de%20desocupa%C3%A7%C3%A3o%20do,2023%20(8%2C4%25).>. Acesso em: 24 março 2024.


###    Objetivo geral

Analisar o crescimento contínuo da incidência de desemprego nos centros urbanos do Brasil e estimar sua projeção futura.  

####    Objetivos específicos

• Identificar os principais centros urbanos do Brasil que apresentam um aumento significativo na população em situação de ociosidade laboral.  
• Analisar os dados estatísticos relacionados ao índice de desemprego em cada um dos centros urbanos identificados.  
• Comparar e contrastar os dados obtidos sobre a população em desocupação profissional, a carência de emprego e a desigualdade social para encontrar correlações potenciais.  
• Propor recomendações para políticas públicas ou intervenções sociais visando mitigar os efeitos negativos dessas correlações na sociedade.  
• Impulsionar um aumento da qualidade de vida da população através de iniciativas abrangentes em áreas como saúde, educação, habitação e bem-estar social.  


###    Justificativas

O projeto oferece uma ferramenta para gestores públicos, pesquisadores e profissionais dos setores de assistência social, saúde e segurança pública, representando uma contribuição significativa para o cenário econômico ao possibilitar a formulação de políticas públicas mais eficazes. Baseado em dados estatísticos confiáveis e pesquisa detalhada, o sistema visa não apenas facilitar a tomada de decisões, mas também promover o desenvolvimento econômico por meio da otimização de recursos e da identificação de oportunidades de crescimento sustentável.  

No âmbito social, nosso objetivo é promover o bem-estar e contribuir para a construção de uma sociedade íntegra. Ao adotar essa ferramenta, empresas têm a oportunidade de desempenhar um papel fundamental na melhoria da qualidade de vida das pessoas, ao mesmo tempo em que colaboram para a criação de uma comunidade mais coesa e inclusiva.  


##    Público alvo

Gestores Públicos: Possuem familiaridade com políticas públicas, gestão de recursos e tomada de decisões estratégicas. Utilizam sistemas de informação para análise de dados e monitoramento de indicadores sociais. Podem ocupar cargos de liderança em órgãos governamentais, como secretarias de assistência social, saúde e segurança pública.  

Pesquisadores Corporativos: Têm formação acadêmica em áreas como sociologia, economia ou ciência política, com experiência em análise de dados e métodos de pesquisa. Utilizam ferramentas estatísticas e software de análise de dados para realizar estudos e produzir relatórios. Podem atuar em instituições de pesquisa, universidades ou organizações não governamentais.  


## Análise exploratórida dos dados

###    Dicionário de dados

BASE DE DADOS 1

|   Variáveis   | Tipo de dado  |                      Descrição                       |
| ------------- | ------------- |----------------------------------------------------  |
|   estado      |   textual     |    Estado ou região dentro do país                   |
|   data        |   data        |    Data da coleta dos dados                          |
|   idade       |   numérico    |    idade da população de uma região                  | 
|   população   |   numérico    |    quantidade de habitantes de uma região ou estado  |
|   educação    |   categórico  |    nível de formação da população                    |
|   prin_renda  |   categórico  |    pricipal fonte de renda de uma região             |




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




