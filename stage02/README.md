# Etapa 02 - Descrição da Proposta
# Slides da Proposta
* [Link para os slides](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/stage02/slides/ppt%20etapa2.pdf)
# Motivação e Contexto
Escolhemos abordar o tema da Covid-19 mediante o contexto da atual pandemia. Nosso objetivo nesse projeto de MC 536 é verificar a relação entre os picos de contaminação da doença e as condições geoclimáticas em diferentes partes do mundo. Nossa ideia surgiu diante das especulações disseminadas no início da pandemia acerca do caráter sazonal do vírus, as quais corroboram com crenças equivocadas como, por exemplo, que a contaminação no Brasil não seria massiva em razão das altas temperaturas do país. Iremos relacionar dados como temperatura, umidade e pressão de países com diferentes características com informações sobre a doença como contaminação diária, número de mortes e número de recuperados. A expectativa é de que encontremos uma relação relevante, porém não determinante, quanto à influência do clima nos efeitos do COVID. Teremos a necessidade de usar dados organizados
em, por exemplo, tabelas que relacionam um país e uma data com o número de infectados. Outro exemplo seriam documentos em formato hierárquico referentes a um lugar com as propriedades de temperatura ao longo do tempo.
# Método
A princípio adotaremos a seguinte metodologia para realização do nosso projeto:
* Selecionaremos diversos países com diferentes características geoclimáticas
* Escolheremos em função do tempo decorrido da doença naquele país, um período específico para análise.
* Analisaremos o crescimento do número de infectados e mortes pela doença em função das condições climáticas, do tempo de desenvolvimento da doença e do crescimento de contaminação naquele período.
* Para tentar minimizar as influências sociais e governamentais, faremos comparações entre os dados referentes a todos os períodos analisados do mesmo país.
* Por fim, iremos observar os padrões existentes ao compararmos a evolução da doença em todos os países escolhidos
# Base de dados
Selecionamos algumas bases de dados para serem candidatas a utilizarmos. Seus dados se aproximam, em sua maioria, das informações que desejamos para subsidiar nossa análise, são elas:

Nome | Link | Descrição
----- | ----- | -----
World Weather Online | https://www.worldweatheronline.com/developer/api/docs/local-city-town-weather-api.aspx | Contém informações históricas dos dados climáticos de diversas cidades do mundo
Covid19 API | https://api.covid19api.com/ | Contém os principais dados da covid, como contaminação, mortes e recuperados, em todos os países
World Health Organization | https://covid19.who.int/table | Apresenta informações gerais relevantes para serem adicionadas ao estudo, não necessariamente será usada diretamente para reacionar os dados
Ip Geolocation API | https://api.ipgeolocationapi.com/countries | Contém as coordenadas geográficas da maioria das cidades e países. Será usada em conjunto com a Open Weather Map pois essa requer as coordenadas para buscar os dados climáticos
Open Weather Map | http://api.openweathermap.org/data/ | Contém os dados de temperatura, pressão e umidade dos países a partir de sua latitude e longitude
