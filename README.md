![alt text](https://github.com/pedrozanineli/imersao-dados-desafio-final/blob/main/Capa-1.png)

A proposta do projeto foi inspirada em um desafio do Laboratório de inovação de ciências de [Harvard](https://lish.harvard.edu/), com os dados da competição disponibilizados no [kaggle](https://www.kaggle.com/c/lish-moa).

## A ciência de dados e o *Machine Learning* no tema de *drug discovery*

O tema desse trabalho é a identificação dos chamados MoA - *Mecanism of Activations*, ou Mecanismo de Ativação, por meio do uso de *Machine Learning* em uma base de dados. Uma vez identificados os compostos com efeito clínicos efetivos, é possível auxiliar no processo de criação de medicamentos e análise nas etapas desse processo.

### Objetivo a ser resolvido

O objetivo escolhido a ser realizado é a previsão de ativação ou não de determinados mecanismos, tomando como base, tanto de treino para teste, os dados fornecidos na plataforma kaggle já mencionada.

Para podermos compreender o projeto como um todo, é preciso tomar como ponto de partida o entendimento das tabelas e variáveis:

### 1.Tabela dos experimentos

Podemos buscar a tabela dos experimentos, após leitura da base de dados com o auxílio da biblioteca Pandas importada, sendo armazenada na variável exp, com o código abaixo:

```python
exp.head()
```

| Id            | Tratamento  | Tempo | Dose  | Composto  | g-0      | ... | c-99    |
| ------------- | ----------  | ----- | ----- | --------  | -------- | --- | ------- |
| id_000644bb2  | com_droga   |	24    | D1    |	b68db1d53 | 1.0620   | ... | 0.4176  |
| id_000779bfc	| com_droga   |	72    |	D1    |	df89a8e5a |	0.0743   | ... | 0.7371  |
| id_000a6266a  |	com_droga   |	48    |	D1    |	18bb41b2c |	0.6280   | ... | 0.6931  | 
| id_0015fd391  |	com_droga   |	48    |	D1    |	8c7f86626 |	-0.5138  | ... | -0.8154 |
| id_001626bd3	| com_droga	  | 72    |	D2    |	7cbed3131	| -0.3254  | ... | 0.7125  |

Para entendermos as particularidades desse projeto, precisamos entender qual o seu significado e respectivos valores possíveis:

1. Id - refere-se a cada experimento realizado, servindo como um identificador para cada um deles;
2. Tratamento - indica como a amostra foi tratada, sendo possível com ou sem droga;
3. Tempo - demonstra o tempo decorrido para apresentação de algum efeito, podendo ser 24, 48 ou 72 horas (um, dois ou três dias, portanto);
4. Dose - apesar de não ser possível compreender tão a fundo, dois tipos de dosagem são apresentados (D1 e D2), podendo ser a quantidade aplicada, p.e.;
5. Composto - constitui o composto (droga, na tabela original) que está sendo testado, apresentado uma grande quantidade de opções;
6. Colunas com prefixo "g" - as expressões gênicas, o processo de transcrição até a possível síntese de uma proteína;
7. Coluna com prefixo "c" - as viabilidades celulares, isto é, a avaliação quantitativa e qualitativa de uma cultura celular.

### 2. Tabela dos resultados

De maneira semelhante ao acesso da tabela de experimentos, acessamos a tabela de resultados:

```python
res.head()
```

| id            | 5-alpha_reductase_inhibitor | 11-beta-hsd1_inhibitor | acat_inhibitor | ... |
| ------------- | --------------------------- | ---------------------- | -------------- | --- |
| id_000644bb2  |	0                           | 0                      | 0              | ... |
| id_000779bfc  |	0                           |	0                      | 0              | ... |
| id_000a6266a  |	0                           |	0                      | 0              | ... |
| id_0015fd391  |	0                           |	0                      | 0              | ... |
| id_001626bd3  |	0                           |	0                      | 0              | ... |

Para entendermos as particularidades desse projeto, precisamos entender qual o seu significado e respectivos valores possíveis:

1. Id - refere-se a cada experimento realizado, servindo como um identificador para cada um deles;
2. Colunas seguintes são indicadas por MoA, *mecanism of activation*, os mecanismos de ativação.

Nessas colunas, os valores que podem ser atribuídos são binários - ou seja, apenas dois possíveis. Caso o valor seja 0, indicando uma resposta negativa, sem ativação, portanto. Mas, se o valor for igual a 1, indicando uma resposta positiva, com ativação, portanto.

Os nomes dos mecanismos são compostos por 2 componentes: o alvo e o efeito causado no alvo. Por exemplo o MoA 5-alpha_reductase_inhibitor, indica um mecanismo relacionado com a inibição de redutase 5-alpha.

## Bibliografia utilizada no projeto

[1] Projeto do laboratório de inovações de ciência de Harvard:

https://lish.harvard.edu/;

[2] Dados da competição disponibilizados no kaggle:

https://www.kaggle.com/c/lish-moa;

[3] NADEL, Dani, & WERKER, Ella. (1999). The oldest ever brush hut plant remains from Ohalo II, Jordan Valley, Israel (19,000 BP). Disponível em: 

https://www.researchgate.net/publication/262726781_The_oldest_ever_brush_hut_plant_remains_from_Ohalo_II_Jordan_Valley_Israel_19_BP;

[4] Vantagens, aplicação e composição da farinha de peixe:

https://www.patense.com.br/pt/views/farinha-de-peixe.php;

[5] HARDY, Karen. Paleomedicine and the Evolutionary Context of Medicinal Plant Use. **Revista Brasileira de Farmacologia**, 2020. Disponível em: https://link.springer.com/article/10.1007/s43450-020-00107-4

[6] Informações e publicações de artigos a respeito de *drug discovery*:

https://www.nature.com/subjects/drug-discovery;

[7] TOLEDO, Karina. Drogas que modulam a expressão gênica são testadas em modelo de diabetes. **Agência FAPESP**, 2016. Disponível em: https://agencia.fapesp.br/drogas-que-modulam-a-expressao-genica-sao-testadas-em-modelo-de-diabetes/23690/

[8] Python na Ciência de Dados Livro de Bolso, do autor Jake VanderPlas:

https://jakevdp.github.io/PythonDataScienceHandbook/00.00-preface.html;

[9] Documentação da biblioteca Pandas:

https://pandas.pydata.org/docs/;

[10] Documentação da biblioteca Matplotlib:

https://matplotlib.org/2.0.2/;contents.html

[11] Documentação da biblioteca Seaborn:

https://seaborn.pydata.org/;

[12] Entendendo melhor os vetores com a Alura:

https://www.alura.com.br/conteudo/kotlin-introducao-collections-arrays-listas;

[13] Entendendo a distribuição normal, seu conceito, para que serve e como fazer a sua construção:

https://www.voitto.com.br/blog/artigo/distribuicao-normal;

[14] Palestra do pesquisador Dr. Daniel Antunes a respeito de mecanismos epigenéticos:

http://ead.hemocentro.fmrp.usp.br/joomla/index.php/noticias/adotepauta/669-mecanismos-epigeneticos;

[15] Conceituação de *Machine Learning* pelo cientista da computação Arthur Samuel:

https://solvimm.com/blog/o-que-e-machine-learning/;

[16] Entendendo a regressão logística e sua documentação:

 https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html;

[17] Guia de usuário/documentação do *Sci-kit Learning*:

https://scikit-learn.org/stable/user_guide.html;

[18] Entendendo a árvore de decisão e sua documentação:

https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html;

[19] Compreendendo mais a fundo o laço de repetição *for*:

https://www.devmedia.com.br/conceitos-e-exemplos-do-for-lacos-de-repeticoes-estrutura-da-linguagem-parte-2/18871;

[20] Entendendo a árvore de decisão e sua documentação:

https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html;

[21] Droga Milasen desenvolvida para a menina Mila:

https://www.milasmiracle.org/milasen.
