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





### 2. Tabela dos resultados
