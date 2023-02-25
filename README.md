![Badge em Desenvolvimento](http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=GREEN&style=for-the-badge)

| :placard: Vitrine.Dev |    |
| -------------  | --- |
| :sparkles: Nome        | **Data Science: análise e visualização de dados**
| :label: Tecnologias | python
| :rocket: URL         | Notebook no Kaggle
| :fire: Desafio     | Conteúdo do curso [Data Science: analise e visualização de dados](https://www.alura.com.br/curso-online-data-science-primeiros-passos)

![](https://user-images.githubusercontent.com/67301805/218529188-eb796695-5693-44b2-85f1-a34b32fb5328.jpg#vitrinedev)

# Sobre o curso 📚

Este é o primeiro curso da formação Data Science, ministrado pelo instrutor [Guilherme Silveira](https://www.linkedin.com/in/guilhermeazevedosilveira/), em que aprofundei meus conhecimentos sobre o que é fazer ciência de dados, ao fazer mais análises exploratórias de um banco de dados, melhorar a visualização dos gráficos utilizando Matplotlib e Seaborn.

Utilizamos três bases de dados neste curso, todas relacionadas a filmes. A primeira é sobre as notas que o usuário atribuiu aos filmes que já assistiu, a segunda contém o título dos filmes e seus gêneros, enquanto a última era um dataset mais robusto, pois além do título e duração, há informações sobre o orçamento, idioma original, sinopse, popularidade, data de lançamento, nota média e quantidade de votos que o filme recebeu.

![image](https://user-images.githubusercontent.com/67301805/219108327-b5c82f9c-9632-4b52-94f9-81bdad53f1e7.png)
![image](https://user-images.githubusercontent.com/67301805/219108394-02ef69af-db48-4f73-8fb9-538083eb5fa3.png)
![image](https://user-images.githubusercontent.com/67301805/219108492-8e79a70a-2f0e-4143-a5fc-779947e55069.png)




# Minha prática 👩🏻‍💻

Até o momento, eu estava replicando o que aprendi nos cursos da Alura. Ou seja, mostrava o que identifiquei nos dados, usando os métodos e bibliotecas que vi no curso. Porém, decidi apresentar esta prática de outra forma, por dois motivos:

- em janeiro, eu terminei de ler o livro [Storytelling com dados](https://altabooks.com.br/produto/storytelling-com-dados/), da Cole Nussbaumer, que é sobre como melhorar a visualização de dados. Ao longo do livro, a autora ensina como construir uma narrativa para os dados e deixar a apresentação mais interessante para quem estiver ouvindo/lendo. Mas durante a leitura, também comecei a refletir sobre todos os relatórios e apresentações que fiz ao longo da minha vida, tanto acadêmica quanto profissional, porque eu consegui recordar de situações em que foquei no “embelezamento” do gráfico, ao invés de melhorar o texto e facilitar a compreensão do ouvinte/leitor.

- e o segundo motivo, é um outro curso que concluí recentemente na Alura, o de [Modelos preditivos em dados: detecção de fraude](https://www.alura.com.br/curso-online-modelos-preditivos-dados-deteccao-fraude), da instrutora [Sthefanie Monica](https://github.com/sthemonica?tab=overview&from=2023-02-01&to=2023-02-17). Antes de dar início a criação do modelo preditivo, a instrutora apresenta o seguinte cenário: 
*Estamos trabalhando em uma startup de dados e precisamos criar um modelo preditivo para uma instituição financeira fictícia. Posteriormente, o projeto será adicionado ao portfólio da empresa e apresentado aos futuros clientes*.
Ao longo do curso, decisões foram tomadas a partir desta informação e que facilitou minha compreensão. 

Entende que há uma diferença entre contextualizar a narrativa com um cenário (mesmo que fictício), ao invés de exemplificar com uma situação isolada? 

Que é exatamente o que fiz até o momento, explicava brevemente sobre o que se tratava o dataset e resumia os resultados obtidos no notebook.

Portanto, vou criar um contexto para o projeto, inspirada na didática do curso sobre modelos preditivos e também para replicar o que aprendi com o livro.

---

Dito isso, para esta prática, utilizei um dataset disponível no [Kaggle](https://www.kaggle.com/) sobre avaliações de [barras de chocolate](https://www.kaggle.com/datasets/rtatman/chocolate-bar-ratings), provenientes de diversos países, compostos por diferentes tipos de grão e porcentagem de cacau.

![image](https://user-images.githubusercontent.com/67301805/219493123-06dc2cee-536c-49f3-b5ee-059fd713a275.png)

Neste caso, vamos supor que: 

**Eu preciso fazer a análise exploratória neste dataset, porque estou prestando consultoria para uma empresa do setor de alimentos que nunca trabalhou com chocolate anteriormente, mas quer entrar neste ramo e desenvolver seu produto. 
Portanto, preciso apresentar os melhores produtos presentes no mercado, os principais concorrentes, de onde eles são, qual grão eles utilizam, qual o país de origem do grão e qual a porcentagem de cacau que possui as melhores avaliações.**

Decidi explorar os dados da seguinte maneira:

Calcular a média, ou mediana, das notas para cada variável. Selecionando os fabricantes com as melhores médias, depois os melhores produtos, assim por diante. A cada etapa, criaria um novo dataframe e exploraria as demais variáveis. Por exemplo, ao selecionar os melhores produtos, verificaria de onde eles são, as porcentagens de cacau mais recorrentes, etc.

## Fabricantes: 🏭

Iniciei a análise pelos *Fabricantes*, ao calcular a média de suas notas. Selecionei os 15 que tiveram as melhores médias e criei um novo dataframe, composto por 49 linhas e 9 colunas. Entre as empresas, 6 delas são dos Estados Unidos, 2 da França e mais sete países com 1 empresa cada.

![image](https://user-images.githubusercontent.com/67301805/221249766-cf0ac0cf-c901-42b6-9677-b39e540fc1ca.png)

Em seguida, averiguei qual a porcentagem de cacau mais presente nas barras de chocolate, o top 3 é composto por 24 produtos com 70% de cacau, 11 com 72% e 4 com 68%. 

Ao fazer a análise do tipo de grão mais utilizado, percebi uma incoerência do dataset. Quando fiz o **.info()**, tanto a variável Tipo_grao quanto a Origem_grao, apresentaram apenas 1 linha sem informação, o que considerei ‘ok’ para um dataset com 1795 entradas. Mas, no retorno do **groupby()** haviam 9 produtos sem a informação sobre os grãos… 🤷‍♀️

Enfim, os grãos mais presentes são: 14 barras de Trinitario, 10 de Criollo, 9 sem identificação e 3 de Blend.

Finalizando com o país de origem dos grãos, 14 são da Venezuela, 8 do Peru e 3 sem identificação. 

## Produtos: 🍫

Passando para os *Produtos*, a maioria recebeu uma avaliação entre 3,0 e 3,5. 

![image](https://user-images.githubusercontent.com/67301805/221252528-054f208c-ce1f-4b78-bc48-c5b5923b5b8a.png)

Porém decidi selecionar apenas os produtos com nota maior ou igual a 4,0 que resultou em um dataframe com 100 produtos.

Mais uma vez, o mercado norte americano e francês são os mais frequentes no dataframe, com 16 e 6 empresas respectivamente, seguido pelo mercado do Reino Unido com 4 fabricantes.

Em relação a porcentagem de cacau, mais uma vez, produtos com 70% são os mais frequentes, com 45 produtos, seguidos por 75% e 72%, com 17 e 11 produtos respectivamente. Não houve mudança em relação ao país exportador de cacau, mas há 32 produtos sem informação sobre o tipo de grão, seguido por *Trinitario* com 26 e *Criollo* com 14.

## Porcentagem de cacau: 🌱

Seguindo para a porcentagem de cacau, selecionei as 15 medianas mais altas. A porcentagem que tem a melhor mediana são as barras com 50% de cacau, com 3,75. Seguida por 63%, com mediana de 3,625, e 78%, com mediana de 3,5.

![image](https://user-images.githubusercontent.com/67301805/221262890-5c82fd65-f929-444a-bdcb-4c42c8973c67.png)

No novo dataframe, com 735 registros, a empresa com maior quantidade de produtos presente é a francesa *Bonnat*, com 26 produtos, e as empresas com maior variedade de porcentagem são a norte americana *Scharffen Berger* e a francesa *Valrhona*, ambas com 6 diferentes porcentagem de cacau.

Sobre o país de origem dos fabricantes, o mercado norte americano e francês continuam dominando o primeiro e segundo lugar, a mudança está no terceiro lugar, ocupado pelo Canadá, com 10 empresas. 


## País de origem da empresa: 🗺️

Ao fazer uma contagem de onde são os fabricantes, fica claro o porquê dos Estados Unidos sempre aparecer em maior quantidade nas análises anteriores, pois no dataset de 1795 linhas, 764 delas são referentes a produtos norte-americanos, em que estão registradas 175 empresas distintas. Em seguida vem a França, com 156 produtos, provenientes de 22 empresas, e pelo Canadá, com 125 produtos de 20 empresas.

Para se ter uma ideia do tamanho do mercado norte americano, plotei o gráfico que apresenta a junção de todos os produtos dos Estados Unidos X demais países. Em seguida, plotei um outro gráfico para apresentar os 10 países que estão depois dos Estados Unidos:

![image](https://user-images.githubusercontent.com/67301805/221368103-85046bb9-f3ab-42c5-a090-74cb3fb5cba8.png)
![image](https://user-images.githubusercontent.com/67301805/220790343-cc77c084-bd21-42e1-adad-77be55631534.png)

Ao calcular a média de nota por local, o Chile ficou com na primeira posição, com 3,75, seguido por Amsterdam, Países Baixos e Filipinas, todas com 3,5. 
Neste novo dataframe, a empresa com maior quantidade de produtos é a canadense *Soma*, com 47 produtos. O produto com maior variedade de porcentagem de cacau é o *Brazil*, com 6 versões distintas. 

Barras com 70% de cacau continuam ocupando o primeiro lugar na contagem, com 156 produtos, seguido por 72% e 75%, ambas com 30 produtos.
Ao fazer a contagem dos países dos fabricantes, o Canadá possui 20 empresas no dataframe, Austrália e Itália com 10 empresas cada uma, Suíça com 8.
Diante o alto valor de empresas canadenses, no total há 125 produtos deste país.
O grão que mais aparece são os ‘não identificados’, com 137 registros, seguido por *Trinitario*, com 93,  e *Criollo*, com 45. O maior país exportador de grão, continua sendo a Venezuela.
 


## Tipo de grão: 🌿

Selecionando os 15 grãos com maior média, resultou em um dataframe com 30 linhas. O fabricante com mais produtos é a brasileira *AMMA*, com 4 produtos, e a empresa com maior variedade de grãos, é a norte americana *Heirloom Cacao Preservation (Guittard)*, com os grãos *Amazon, ICS*, *Beniano* e *EET*. 

O tipo de grão mais frequente no dataframe é o *Forastero (Parazinho)*, utilizado por 5 fabricantes. Os três maiores exportadores de grãos são o *Brasil*, *Bolívia* e *Venezuela*.


## Origem do grão: 🌏🌎🌍





# Conclusão 🏁

### De acordo com os fabricantes: 

Caso a empresa queira desenvolver um produto que consiga as melhores notas, sugiro verificar o concorrente italiano *Amedei*, fabricante do *Chuao*, que recebeu nota máxima na avaliação.

Caso a empresa queira ter uma linha de produtos, com avaliações consistentes e acima da mediana de todas as notas, sugiro verificar a linha de produtos dos concorrentes *Idilio*, *Matale* e *Patric*. 

### De acordo com os produtos:

Seguindo a ideia de desenvolver o melhor produto, reforço a sugestão de verificar o concorrente italiano *Amedei*.
E caso a empresa queira uma linha de produtos mais consistente, sugiro um estudo mais aprofundado do fabricante *Soma*, que apresentou 10 produtos com nota 4,0.



## Ferramentas utilizadas 🧰 
<p> <a href="https://www.python.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a> 
    <a href="https://pandas.pydata.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/pandas/pandas-original.svg" alt="pandas" width="40" height="40"/>
    <a href="https://seaborn.pydata.org/" target="_blank" rel="noreferrer"> <img src="https://seaborn.pydata.org/_images/logo-mark-lightbg.svg" alt="seaborn" width="40" height="40"/>
    <a href="https://numpy.org/" target="_blank" rel="noreferrer"> <img src="https://numpy.org/images/logo.svg" alt="numpy" width="40" height="40"/>
    </p>
