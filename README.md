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

Iniciei a análise pelos *Fabricantes*, ao calcular a média de suas notas. Selecionei os 15 que tiveram as melhores médias e criei um novo dataframe, composto por 49 linhas e 9 colunas. 

![image](https://user-images.githubusercontent.com/67301805/221249766-cf0ac0cf-c901-42b6-9677-b39e540fc1ca.png)

Em que, 6 delas são dos Estados Unidos, 2 da França e mais sete países com 1 empresa cada. 

Em seguida, averiguei qual a porcentagem de cacau mais presente nas barras de chocolate, o top 3 é composto por 24 produtos com 70% de cacau, 11 com 72% e 4 com 68%. 

Ao fazer a análise do tipo de grão mais utilizado, percebi uma incoerência do dataset. Quando fiz o **.info()**, tanto a variável Tipo_grao quanto a Origem_grao, apresentaram apenas 1 linha sem informação, o que considerei ‘ok’ para um dataset com 1795 entradas. Mas, no retorno do **groupby()** haviam 9 produtos sem a informação sobre os grãos… 🤷‍♀️

Enfim, os grãos mais presentes são: 14 barras de Trinitario, 10 de Criollo, 9 sem identificação e 3 de Blend.

Finalizando com o país de origem dos grãos, 14 são da Venezuela, 8 do Peru e 3 sem identificação. 














![image](https://user-images.githubusercontent.com/67301805/220790343-cc77c084-bd21-42e1-adad-77be55631534.png)




# Conclusão 🏁

De acordo com os fabricantes: 

Caso a empresa queira desenvolver um produto que consiga as melhores notas, sugiro verificar o concorrente italiano *Amedei*, fabricante do *Chuao*, que recebeu nota máxima na avaliação.

Caso a empresa queira ter uma linha de produtos, com avaliações consistentes e acima da mediana de todas as notas, sugiro verificar a linha de produtos dos concorrentes *Idilio*, *Matale* e *Patric*. 


## Ferramentas utilizadas 🧰 
<p> <a href="https://www.python.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a> 
    <a href="https://pandas.pydata.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/2ae2a900d2f041da66e950e4d48052658d850630/icons/pandas/pandas-original.svg" alt="pandas" width="40" height="40"/>
    <a href="https://seaborn.pydata.org/" target="_blank" rel="noreferrer"> <img src="https://seaborn.pydata.org/_images/logo-mark-lightbg.svg" alt="seaborn" width="40" height="40"/>
    <a href="https://numpy.org/" target="_blank" rel="noreferrer"> <img src="https://numpy.org/images/logo.svg" alt="numpy" width="40" height="40"/>
    </p>
