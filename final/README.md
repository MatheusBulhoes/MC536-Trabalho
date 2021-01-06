## Projeto Relacionando Covid e Clima

## Equipe MIL
* Matheus Bulhões Barbosa
* Isabela Caroline de Sousa
* Lucas Antevere Santana

## Slides da Apresentação da Etapa Final

* [Link para os slides](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/slides/pp%20banco%20de%20dados.pdf)

## Resumo do Projeto
> Texto resumindo o projeto.

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
> ![ER Taxi](https://github.com/MatheusBulhoes/MC536-Trabalho/blob/main/final/images/Modelo%20Conceitual.png)

## Modelos Lógicos Finais

> Modelos relacionais do projeto
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
> Elencar as bases de dados utilizadas no projeto. Apresente todas as bases usadas na versão final, mesmo aquelas que tenham sido apresentadas em etapas anteriores.

título da base | link | breve descrição
----- | ----- | -----
`<título da base>` | `<link para a página da base>` | `<breve descrição da base>`

## Arquivos de Dados
> Elencar os arquivos usados no projeto que estão disponíveis no Github do projeto. Apresente todos os arquivos usados na versão final, mesmo aqueles que tenham sido apresentadas em etapas anteriores.

nome do arquivo | link | breve descrição
----- | ----- | -----
`<nome do arquivo>` | `<link para o arquivo>` | `<breve descrição do arquivo>`

> Os arquivos devem ser colocados na pasta `data`, em subpasta conforme seu papel (externo, interim, processado, raw). A diferença entre externo e raw é que o raw é em formato não adaptado para uso. A pasta `raw` é opcional, pois pode ser substituída pelo link para a base original da seção anterior.
> Coloque arquivos relacionais (usualmente CSV), XML ou JSON que não estejam disponíveis online e sejam acessados pelo notebook.

