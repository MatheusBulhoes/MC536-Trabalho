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
> Apresente aqui detalhes da análise. Nesta seção ou na seção de Resultados podem aparecer destaques de código como indicado a seguir. Note que foi usada uma técnica de highlight de código, que envolve colocar o nome da linguagem na abertura de um trecho com `~~~`, tal como `~~~python`.
> Os destaques de código devem ser trechos pequenos de poucas linhas, que estejam diretamente ligados a alguma explicação. Não utilize trechos extensos de código. Se algum código funcionar online (tal como um Jupyter Notebook), aqui pode haver links. No caso do Jupyter, preferencialmente para o Binder abrindo diretamente o notebook em questão.

~~~python
df = pd.read_excel("/content/drive/My Drive/Colab Notebooks/dataset.xlsx");
sns.set(color_codes=True);
sns.distplot(df.Hemoglobin);
plt.show();
~~~

## Evolução do Projeto
> Relatório de evolução, descrevendo as evoluções na modelagem do projeto, dificuldades enfrentadas, mudanças de rumo, melhorias e lições aprendidas. Referências aos diagramas, modelos e recortes de mudanças são bem-vindos.
> Podem ser apresentados destaques na evolução dos modelos conceitual e lógico. O modelo inicial e intermediários (quando relevantes) e explicação de refinamentos, mudanças ou evolução do projeto que fundamentaram as decisões.
> Relatar o processo para se alcançar os resultados é tão importante quanto os resultados.

## Resultados e Discussão
> Apresente os resultados da forma mais rica possível, com gráficos e tabelas. Mesmo que o seu código rode online em um notebook, copie para esta parte a figura estática. A referência a código e links para execução online pode ser feita aqui ou na seção de detalhamento do projeto (o que for mais pertinente).
> A discussão dos resultados também pode ser feita aqui na medida em que os resultados são apresentados ou em seção independente. Aspectos importantes a serem discutidos: É possível tirar conclusões dos resultados? Quais? Há indicações de direções para estudo? São necessários trabalhos mais profundos?

## Conclusões
> Apresente aqui as conclusões finais do trabalho e as lições aprendidas.

## Modelo Conceitual Final

> Modelo conceitual final em ER
> ![ER Modelo](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/images/Modelo%20Conceitual.png)

## Modelos Lógicos Finais

> Modelo relacional final do projeto
~~~
COVID(Confirmados, Mortes, Recuperados, Ativos, _Data_)
TEMPERATURA(Maximo, Minimo, Media, _Data_)
~~~

## Programa de extração e conversão de dados atualizado

> Coloque um link para o arquivo do notebook que executa a extração e conversão de dados. Ele estará dentro da pasta `notebook`. Se por alguma razão o código não for executável no Jupyter, coloque na pasta `src`. Se a extração e conversão envolverem queries executadas através de uma interface de um SGBD não executável no Jupyter, como o Cypher, apresente na forma de markdown.

## Conjunto de queries para todos os modelos

> Acrescente um link para o(s) arquivo(s) do(s) notebook(s) que executa(m) as queries para cada um dos modelos lógicos. Eles estarão dentro da pasta `notebook`. Se por alguma razão o código não for executável no Jupyter, coloque na pasta `src`. Se as queries forem executadas através de uma interface de um SGBD não executável no Jupyter, como o Cypher, apresente na forma de markdown.
> Apresente todas as suas queries em versão final, mesmo que tenham aparecido em etapas anteriores.

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
Conteúdo Percentual | https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/data/processed/content_percent.csv | Tabela que contém os dados percentuais tanto climáticos quanto da Covid nos mesmos intervalos de data
