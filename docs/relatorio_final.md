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

Os acidentes nas rodovias representam um grave problema em todo o mundo, resultando em perdas humanas, danos materiais e impactos econômicos significativos. Nesse contexto, a aplicação de sistemas inteligentes analise dos dados através da ciência de dados tem se mostrado uma abordagem promissora para a prevenção e mitigação desses acidentes. A capacidade desses sistemas de coletar, processar e analisar grandes volumes de dados em tempo real, juntamente com a capacidade de tomar decisões autônomas e rápidas, torna-os ferramentas essenciais na busca por estratégias mais eficazes de segurança viária. Este trabalho tem como objetivo explorar o papel dos sistemas inteligentes na redução de acidentes nas rodovias, destacando suas potenciais contribuições e desafios a serem superados.

###    Contextualização

A crescente disponibilidade de dados e avanços tecnológicos têm permitido a aplicação da ciência de dados em diversas áreas, incluindo a economia e o mercado de trabalho. No contexto do Brasil, a análise preditiva do desemprego por meio de técnicas de ciência de dados se mostra como uma ferramenta poderosa para compreender e antecipar as tendências do mercado de trabalho. A capacidade de coletar, processar e analisar grandes volumes de dados permite identificar padrões, correlações e insights competentes. Neste sentido, este trabalho se propõe a explorar o uso de técnicas avançadas de ciência de dados para prever a taxa de desemprego no Brasil, contribuindo assim para uma abordagem mais informada e eficaz na gestão do mercado de trabalho e no enfrentamento dos desafios econômicos e sociais de cada região.  


###    Problema
O problema que o agente pretende resolver é o alto índice de desemprego no Brasil. O país enfrenta dificuldades com altas taxas de desemprego, o que impacta diretamente a qualidade de vida da população, gerando instabilidade econômica e social. De acordo com o site Estadão, "A taxa de desemprego no País subiu de 7,6% no trimestre terminado em janeiro para 7,8% no trimestre encerrado em fevereiro, a segunda elevação consecutiva, após nove trimestres móveis seguidos de recuo.", ou seja, aproximadamente 8,535 milhões de pessoas se encontram atualmente desempregadas.

Essa circunstância revela uma série de desafios, tanto para os indivíduos em busca de oportunidades de trabalho, quanto para as empresas que necessitam encontrar profissionais qualificados para preencher suas demandas. Com altas taxas de desemprego, surge uma complexa rede de consequências, incluindo a redução do poder de compra, o aumento da insegurança financeira e a diminuição do investimento em educação e saúde.

Desemprego sobe para 7,8% no trimestre encerrado em fevereiro, aponta IBGE. 28/3/2024:
https://www.estadao.com.br/economia/pnad-ibge-desemprego-fevereiro-2024/


###    Objetivo geral

Analisar o crescimento contínuo da incidência do desemprego nos centros urbanos do Brasil e estimar sua projeção futura.  

####    Objetivos específicos

• Identificar os principais centros urbanos do Brasil que apresentam um aumento significativo na população em situação de ociosidade laboral;  
• Analisar os dados estatísticos relacionados ao índice de desemprego em cada um dos centros urbanos identificados;
• Comparar e contrastar os dados obtidos sobre a população em desocupação profissional, a carência de emprego e a desigualdade social para encontrar potenciais correlações;  
• Propor recomendações para políticas públicas ou intervenções sociais visando mitigar os efeitos negativos dessas correlações na sociedade;
• Impulsionar um aumento da qualidade de vida da população através de iniciativas abrangentes em áreas como saúde, educação, habitação e bem-estar social.  


###    Justificativas

O projeto oferece uma ferramenta para gestores públicos, pesquisadores e profissionais dos setores de assistência social, saúde e segurança pública, representando uma contribuição significativa para o cenário econômico ao possibilitar a formulação de políticas públicas mais eficazes. Baseado em dados estatísticos confiáveis e pesquisa detalhada, o sistema visa não apenas facilitar a tomada de decisões, mas também promover o desenvolvimento econômico por meio da otimização de recursos e da identificação de oportunidades de crescimento sustentável.  

No âmbito social, nossa motivação é edificada ao promover o bem-estar e contribuir para a construção de uma sociedade íntegra. Ao adotar essa ferramenta, empresas têm a oportunidade de desempenhar um papel fundamental na melhoria da qualidade de vida das pessoas, ao mesmo tempo em que colaboram para a criação de uma comunidade mais coesa e inclusiva.  


##    Público alvo

Gestores Públicos: Possuem familiaridade com políticas públicas, gestão de recursos e tomada de decisões estratégicas. Utilizam sistemas de informação para análise de dados e monitoramento de indicadores sociais. Podem ocupar cargos de liderança em órgãos governamentais, como secretarias de assistência social, saúde e segurança pública.  

Pesquisadores Corporativos: Têm formação acadêmica em áreas como sociologia, economia ou ciência política, com experiência em análise de dados e métodos de pesquisa. Utilizam ferramentas estatísticas e software de análise de dados para realizar estudos e produzir relatórios. Podem atuar em instituições de pesquisa, universidades ou organizações não governamentais.  


## Análise exploratórida dos dados

###    Dicionário de dados

BASE DE DADOS 1

|   Variáveis   | Tipo de dado  |                      Descrição                                    |
| ------------- | ------------- |------------------------------------------------------------       |
|   índice_coli |   textual     |    Um identificador exclusivo para cada acidente relatado         |
|   ano_colisão |   data        |    Ano em que ocorreu o acidente                                  |
|   ref_acident |   numérico    |    Um número de referência associado ao acidente                  | 
|   veic_refe   |   numérico    |    Número de referência do veículo envolvido no acidente          | 
|   ref_casual  |   categórico  |    Um número de referência da vítima envolvida no acidente        |
|   clas_viti   |               |    Indica a classe da vítima (ex: motorista, passageiro, pedestre)|
|   sexo        |   categórico  |    O sexo da vítima (masculino ou feminino)			    |
|   idade       |   numérico    |    A idade da vítima						    |
|   faix_etar   |   numérico    |    Faixa etária a que pertence a vítima (ex.: 0-5, 6-10, 11-15)    |
|   grav_ferim  |   categórico  |    A gravidade dos ferimentos da vítima (por exemplo, fatal, grave,leve)|
|   loca_pedes  |               |    Localizção do pedrestre no momento do acidente 	            |
|   mov_pedes   |               |    Movimentação do pedrestre durante o acidente 		    |
|   passa_car   |               |    Indica se o acidentado era passageiro do carro no momento do acidente|
|   pass_onib   |               |    Indica se a vítima foi um passageiro de ônibus ou ônibus (sim ou não)|
|   traba_rodov |               |    Indica se o acidentado era trabalhador de manutenção rodoviária (sim ou não)|
|   tipo_vitim  |               |    O tipo de vítima (por exemplo, motorista/passageiro, passageiro, pedestre)|
|   resid_vitim |               |    O tipo de área em que a vítima reside (por exemplo, urbana, rural)|
|   decil_IMD   |               |    O decil IMD da área onde reside a vítima (uma medida de privação)|
|   LSOA        |               |    A Área de Super Saída da Camada Inferior (LSOA) associada à localização da vítima|




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




