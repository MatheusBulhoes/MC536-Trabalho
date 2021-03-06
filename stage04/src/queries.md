* Importamos a tabela criada

~~~cypher
LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/MatheusBulhoes/MC536-Trabalho/main/stage04/countries_weather.csv' AS line
CREATE (:Country {nome:line.country, temp: line.temp, pressure: line.pressure, humidity: line.humidity})

CREATE INDEX ON :Country(nome)
~~~

* Para temperatura, pressão e umidade, conectamos os países que têm características próximas

~~~cypher
MATCH (c1:Country)
MATCH (c2:Country)
WHERE ABS(toFloat(c1.temp) - toFloat(c2.temp)) < 4 AND c1 <> c2
CREATE (c1)-[:similar_temperature]->(c2)

MATCH (c1:Country)
MATCH (c2:Country)
WHERE ABS(toFloat(c1.pressure) - toFloat(c2.pressure)) < 6 AND c1 <> c2
CREATE (c1)-[:similar_pressure]->(c2)

MATCH (c1:Country)
MATCH (c2:Country)
WHERE ABS(toFloat(c1.humidity) - toFloat(c2.humidity)) < 10 AND c1 <> c2
CREATE (c1)-[:similar_humidity]->(c2)
~~~

* Consideramos que os países que têm os 3 tipos de similaridades possuem uma similaridade climática, no geral

~~~cypher
MATCH p=(c1)-[:similar_humidity]->(c2)<-[:similar_pressure]-(c1)-[:similar_temperature]->(c2)
CREATE (c1)-[:similar]->(c2)
~~~

* E deletaremos as outras relações de similaridade para que os grafos não fiquem visualmente poluídos

~~~cypher
MATCH p=()-[r:similar_temperature]->()
DELETE r

MATCH p=()-[r:similar_humidity]->()
DELETE r

MATCH p=()-[r:similar_pressure]->()
DELETE r
~~~

* É possível agora, utilizar o algoritmo de comunidade para relacionar vários países que são similares entre si

~~~cypher
CALL gds.graph.create('similarCountries','Country',{similar: {orientation:'UNDIRECTED'}})

CALL gds.louvain.stream('similarCountries')
YIELD nodeId, communityId
MATCH (c:Country {nome: gds.util.asNode(nodeId).nome})
SET c.community = communityId
~~~

* Também é possível manualmente contar os países com o qual um determinado país é semelhante

~~~cypher
MATCH (c)-[:similar]->(c1)
MERGE (c)-[r:count]->()
ON CREATE SET r.similarity=1
ON MATCH SET r.similarity=r.similarity+1
~~~

* E, assim, visualizar graficamente os grupos de países similares entre si

~~~cypher
MATCH ()<-[r:count]-(c1)-[s:similar]->(c2)
WHERE r.similarity < 10
RETURN c1,c2
LIMIT 50

MATCH ()<-[r:count]-(c1)-[s:similar]->(c2)
WHERE r.similarity > 25
RETURN c1,c2
LIMIT 30
~~~
