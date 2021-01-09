## Projeto Relacionando Covid e Clima

## Equipe MIL
* Matheus Bulhões Barbosa
* Isabela Caroline de Sousa
* Lucas Antevere Santana

## Slides da Apresentação da Etapa Final

* [Link para os slides](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/slides/pp%20banco%20de%20dados.pdf)

## Resumo do Projeto
Relacionamos dados como temperatura, umidade e pressão de países com diferentes características com informações sobre a doença como contaminação diária. Primeiro fizemos a seleção de países com diferentes condições climáticas, em seguida, escolhemos o período de tempo para análise, e depois, relacionamos o número de casos com as condições climáticas durante o intervalo de tempo anteriormente selecionado. Para fazer a análise dos resultados tentamos minimizar influências externas (comportamento social e ações governamentais) e buscar por padrões na evolução da doença

## Motivação e Contexto

Escolhemos abordar o tema da Covid-19 mediante o contexto da atual pandemia. Nosso objetivo nesse projeto de MC 536 é verificar a relação entre os picos de contaminação da doença e as condições geoclimáticas em diferentes partes do mundo. Nossa ideia surgiu diante das especulações disseminadas no início da pandemia acerca do caráter sazonal do vírus, as quais corroboram com crenças equivocadas como, por exemplo, que a contaminação no Brasil não seria massiva em razão das altas temperaturas do país.

## Detalhamento do Projeto
Para a realização da etapa de seleção dos países utilizamos o modelo de grafos. Nosso objetivo foi agrupar os países por semelhanças climáticas e, assim, selecionar quais os países cujos dados relacionados à covid-19 seriam usados no decorrer do nosso projeto. Inicialmente, fizemos um programa em python para unir duas APIs, uma vez que não conseguimos encontrar uma API que contivesse o nome do país, sua localização em termos de latitude e longitude e seus dados climáticos. Com a tabela que criamos, usando o NEO4J, verificamos os países com características climáticas próximas (temperatura, pressão e umidade) e tentamos separá-los em grupos de acordo com similaridade. A análise no NEO4J consistiu em: Importar a tabela criada anteriormente e criar os nós, conectar os países com características similares em termos de temperatura, pressão e umidade (consideramos que os países que possuem os 3 tipos de relações de similaridade possuem uma similaridade climática), determinar os países com os quais um determinado país é semelhante e visualizar graficamente os grupos de países similares entre si. Para os cinco grupos expressivos que foram encontrados com a análise escolhemos os seguintes países:

Malásia, Brunei <br/>
Estados Unidos, Holanda, Coreia do Sul <br/>
Egito, Emirados Árabes <br/>
Uruguai, Brasil, Costa do Marfim <br/>
Senegal, Sudão <br/>

Para abranger um período de tempo suficiente para a realização da análise, escolhemos os cinco períodos listados a seguir:

10/03 à 20/03 <br/>
10/05 à 20/05 <br/>
10/07 à 20/07 <br/>
10/09 à 20/09 <br/>
10/11 à 20/11 <br/>

Na etapa de relacionamento do número de casos confirmados com as condições climáticas de cada país utilizamos o modelo relacional e a linguagem SQL. Inicialmente realizamos uma análise preliminar correspondente a etapa 3 do projeto, em seguida estendemos essa análise para abranger todos os países que fazem parte do nosso grupo de interesse. A análise preliminar consistiu em: importar as tabelas Covid-19 e Temperatura, selecionar um intervalo de datas a partir da tabela Covid-19, alterar a coluna “Data” da tabela Covid-19 para um formato padrão de data para que houvesse compatibilidade entre os formatos de datas das duas tabelas, fazer a junção dessas tabelas a partir da data e calcular o crescimento percentual de casos confirmados. O fluxograma a seguir representa essa análise:

![fluxograma](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/images/Fluxograma%20analise%20preliminar%20etapa%203.png)

Para a análise complementar repetimos o que foi implementado na análise preliminar, porém com um volume maior de dados, considerando que a análise foi estendida para 11 países e 5 intervalos de tempo para cada um deles. 
A partir das tabelas geradas nas análises anteriores, geramos vários gráficos relacionando o crescimento da doença e a temperatura com as datas, que serviram de base para que pudéssemos elaborar uma conclusão.


## Evolução do Projeto
<p>Entre os obstáculos que encontramos para a realização do projeto foi a dificuldade para encontrar APIs que continham os dados que precisávamos. Para contornar essa situação na etapa 4 do projeto, utilizamos duas APIs diferentes, uma com todos os países do mundo e suas respectivas latitudes e longitudes, e outra com os dados climáticos de um único país que consultávamos a partir da latitude e longitude. Criamos um código em Python que, para cada país que fosse lido numa consulta à primeira API, fosse realizada uma consulta à segunda API, e assim obtivemos os dados climáticos de todos os países do mundo em uma data específica.</p>
<p>Outro problema encontrado foi a inconsistência na hora de fazer consultas às APIs. Houveram erros ao procurar pelos dados da Covid nos EUA, e o programa parou sem que soubéssemos o motivo. Além disso, os dados que coletamos de Brunei pareciam desatualizados, pois não houve mudança entre os contaminados da Covid entre as datas escolhidas. Nossa solução foi, então, retirar os EUA e Brunei da lista de países escolhidos para realizar o estudo. Com isso, a Malasia ficou em um grupo isolado, sem que fosse possível comparar seus resultados com um país climaticamente semelhante, e por isso a colocamos no grupo já existente de Sudão e Senegal, pois também havia uma semelhança climática entre a Malásia e estes países.</p>
<p>Por fim, é importante ressaltar que ao longo das etapas do projeto, apesar do êxito conquistado na maioria dos objetivos pontuais de cada tarefa, havia constantemente a incerteza quanto a se obteríamos, de fato, um resultado final coerente. Apesar disso, optamos por não realizar mudanças quanto ao objetivo do projeto entre duas diferentes etapas. </p>

## Resultados e Discussão
Para que fosse mais prático para analizar os resultados, decidimos plotar os dados obtidos em python e obter os resultados mais visualmente a partir deles. Eles podem ser encontrados na pasta de [imagens](https://github.com/MatheusBulhoes/MC536-Trabalho/tree/main/final/images). <br/>
O primeiro resultado importante que encontramos foi que o número bruto de casos permaneceu, na grande maioria dos países, com um crescimento constante ao longo do tempo, independendemente do grupo de semelhança climática e da temperatura naquela época do ano. Temos como exemplo o gráfico do Brasil em maio:

<img src="https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/images/Brazil/5_2020.png" width=500 style="vertical-align:middle">

Para conseguir resultados mais expressivos, fizemos uma análise percentual nos dados que tínhamos anteriormente e novamente plotamos para todos os países. Ao contrário do que houve na análise bruta dos dados, os gráficos em percentuais tiveram uma tendência a decair ao longo dos meses, porém com uma variância muito maior ao longo dos dias e dos países. Com isso, tentamos analisar grupo a grupo, conforme tínhamos planejado quando selecionamos os países.

* O primeiro grupo onde foi realizada a análise continha os países Sudão, Senegal e Malásia. Neste grupo, observamos que no Senegal e no Sudão os casos percentuais da Covid eram decrescente ao longo do ano, com a diverença de um pico crescente em novembro no Senegal. No caso da malásia, houve um vale em Julho, onde os casos percentuais passaram de decrescente para crescente até o final do ano.

* No segundo grupo, temos o Uruguai, o Brasil e a Costa do Marfim. Os dados no Uruguai, ao contrário do esperado, revelaram que o crescimento da doença no país foi percentualmente constante ao longo do ano, enquanto a Costa do Marfim e o Brasil tiveram uma queda constante ao longo do ano todo. É importante frisar que a queda percentual constante no Brasil se deve muito ao crescimento gigantesco nos casos brutos, que chegaram a atingir praticamente 1 milhão de novas vítimas por mês.

* O terceiro grupo continha o Egito e os Emirados Árabes Unidos. Ambos os países foram apresentados com um comportamento decrescente da doença ao longo de todo o ano, com a diferença que os Emirados teve um pico crescente em Setembro.

* Por fim, no último grupo temos a Coreia, que teve, ao contrário do esperado, casos percentuais crescentes desde o início do ano e a Holanda, onde a doença também mostrou um comportamento decrescente, com a excessão de Setembro, onde houve a segunda onda na Europa, situação que já temos conhecimento que a influência principal foi a reabertura das cidades e dos estabelecimentos pouco tempo antes dos novos crescimentos dos casos.

À primeira vista, observamos que todos os grupos de semelhança climática continham diferenças consideráveis entre seus países, de modo em que não houvesse um padrão de comportamento da doença que se baseasse principalmente no clima do país. Depois disso, procuramos uma visão mais abrangente, analisando o dados de todos os países em conjunto e procurando por comportamentos em comum em função das mudanças de temperatura. Com esta análise, porém, encontramos o oposto do esperado: casos onde a temperatura se comportou de maneira semelhante e a doença não manteve a mesma uniformidade, ressaltando a conclusão de que não se encontrava nenhum tipo de correlação entre os dois dados. Entre tais exemplos, estão:

* Holanda e Costa do Marfim - A temperatura nos dois países se manteve a mesma entre os meses 7 e 9. Os casos percentuais na Holanda cresceram em 10 vezes, enquanto os casos na Costa do Marfim se reduziram em 10 vezes, como pode ser visto na imagem:

<img src="https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/images/casoHolandaCosta.png" width=800 style="vertical-align:middle">

* Egito e Emirados Árabes - Casos com temperaturas altíssimas, acima dos 40 graus em média. Nos Emirados, a contaminação estava baixa, enquanto no Egito estava alta.

* Sudão - Entre os meses 7 e 9 a temperatura se manteve constante, porém os casos caíram em 10 vezes. Entre os meses 7 e 11 a temperatura teve uma diferença grande e os casos percentuais estavam na mesma proporção.

## Conclusões
Não conseguimos observar uma influência da temperatura no aumento de casos confirmados relevante quando comparada à influência que o comportamento social exerce. Seria possível realizar um trabalho mais a fundo com mais conhecimento em estatística e análise de dados, porém com os resultados obtidos neste projeto, a conclusão é que o comportamento da doença pode ser considerado independente quanto à temperatura. Apesar do resultado não ter se mostrado o mais expressivo, o trabalho foi importante para aprendermos a utilizar diferentes bases e tipos de dados ao nosso favor e nos proveio mais conhecimento em relação a bancos de dados no geral.

## Modelo Conceitual Final

![ER Modelo](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/images/Modelo%20Conceitual.png)

## Modelos Lógicos Finais

~~~
COVID(Confirmados, Mortes, Recuperados, Ativos, _Data_)
TEMPERATURA(Maximo, Minimo, Media, _Data_)
~~~

## Programa de extração e conversão de dados atualizado

* [Criação da tabela Covid](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/notebooks/covid_convert.ipynb)
* [Criação da tabela Clima](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/notebooks/weather_convert.ipynb)
* [Criação da tabela Clima-Países](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/stage04/notebooks/convert.ipynb)

## Conjunto de queries para todos os modelos

* [Escolhendo países com semelhanças climáticas](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/src/queries_cypher.md)
* [Join entre Covid e Weather](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/notebooks/join_content.ipynb)
* [Colocando os dados da Covid em percentuais](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/notebooks/percent_convert.ipynb)
* [Plotando os gráficos](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/notebooks/plot_content.ipynb)
* [Plotando os gráficos em percentuais](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/notebooks/plot_percent.ipynb)

## Bases de Dados

título da base | link | breve descrição
----- | ----- | -----
Covid19 API | https://api.covid19api.com/ | Contém os principais dados da covid, como contaminação, mortes e recuperados, em todos os países
World Weather Online | https://www.worldweatheronline.com/developer/api/docs/local-city-town-weather-api.aspx | Contém informações históricas dos dados climáticos de diversas cidades do mundo
Ip Geolocation API | https://api.ipgeolocationapi.com/countries | Contém as coordenadas geográficas da maioria das cidades e países. Será usada em conjunto com a Open Weather Map pois essa requer as coordenadas para buscar os dados climáticos
Open Weather Map | http://api.openweathermap.org/data/ |  Contém os dados de temperatura, pressão e umidade dos países a partir de sua latitude e longitude

## Arquivos de Dados

nome do arquivo | link | breve descrição
----- | ----- | -----
Covid | https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/data/interim/covid.csv | Tabela que apresenta os dados da Covid nos países escolhidos para os intervalos de datas escolhidos
Clima | https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/data/interim/weather.csv | Tabela que apresenta os dados climáticos nos países escolhidos para os intervalos de datas escolhidos
Clima-Países | https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/stage04/data/countries_weather.csv | Tabela relacionando os dados climáticos de todos os países, usado na seleção dos países
Conteúdo Total | https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/data/processed/content.csv | Tabela que contém tanto os dados climáticos quanto os dados da Covid nos mesmos intervalos de data
Conteúdo Percentual | https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/data/processed/content_percent.csv | Tabela que contém os tanto os dados climáticos quanto os dados percentuais da Covid nos mesmos intervalos de data
