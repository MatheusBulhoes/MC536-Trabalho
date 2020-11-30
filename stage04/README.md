# Etapa 04 - Análises com o Segundo Modelo Lógico

## Slides da Apresentação da Etapa

> [Link para os slides](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/stage04/slides/pp%20etapas%203%20e%204.pdf)

## Modelo Conceitual Atualizado

> ![Modelo Conceitual](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/stage03/Modelo%20Conceitual.png)

## Modelos Lógicos Atualizados

> Exemplo de modelo lógico relacional
~~~
CLIMA(_País_, Temperatura, Pressão, Umidade)
~~~

## Programa de extração e conversão de dados atualizado

> Código utilizado para a criação da tabela
* [Link para o Notebook](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/stage04/notebooks/convert.ipynb)

## Conjunto de queries de dois modelos

> Queries realizadas nesta etapa
* [Link para o Notebook](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/stage04/src/queries.md)

## Bases de Dados
> Bases de dados da etapa 4

título da base | link | breve descrição
----- | ----- | -----
Ip Geolocation API | https://api.ipgeolocationapi.com/countries | Contém as coordenadas geográficas da maioria das cidades e países. Será usada em conjunto com a Open Weather Map pois essa requer as coordenadas para buscar os dados climáticos
Open Weather Map | http://api.openweathermap.org/data/ |  Contém os dados de temperatura, pressão e umidade dos países a partir de sua latitude e longitude


## Arquivos de Dados
> Arquivos de dados das etapas 3 e 4

nome do arquivo | link | breve descrição
----- | ----- | -----
Covid | https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/stage03/data/covid.csv | Tabela que apresenta os dados de Covid no Brasil para um certo intervalo de datas
Temperatura | https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/stage03/data/weather.csv | Tabela que apresenta os dados da temperatura no Brasil para um certo intervalo de datas
Clima-Países | https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/stage04/data/countries_weather.csv | Tabela relacionando os dados climáticos de todos os países
