# Desafios-Azure
Desafios Trilha Microsoft Azure

## Desafio 1 
#### Resultado
Com base no exercício proposto podemos concluir que há sim uma relação entre as notas de ciências da natureza e matemática já que o desempenho dos alunos nas duas são bem parecidos e o modelo previu de forma próxima as duas notas.

#### Desenvolvimento

Para chegarmos aos resultados relatados anteriormente precisamos primeiro criar um modelo de Machine Learning no qual irá ser responsável pela comparação e previsão de novas notas de ciência da natureza baseadas nas notas de matemática. 

Primeiramente foi criado um workspace no Azure para poder trabalhar com o machine learning, logo em seguida foram criados a instância de computação e cluster de computação, com esse "pre-set" pronto podemos finalmente dar início a resolução do problema.

A principal ferramenta utilizada para tal feito foi a pipeline do Azure disponível na parte de Designer, logo abaixo é possível observar a pipeline pronta: 

[![Captura-de-Tela-31.png](https://i.postimg.cc/jqmqjcx9/Captura-de-Tela-31.png)](https://postimg.cc/0rG1WpJd)

O desenvolvimento pode ser dividido em 3 partes. 

- 1º Parte:

Coloca-se o conjunto de dados e logo em seguida o módulo para selecionar as colunas, nesse caso são NU_NOTA_CN e NU_NOTA_MT, por fim um módulo de limpar dados ausentes já que foi verificado no dataset valores indeterminados, com tudo configurado corretamente executamos a pipeline. 

Com a execução finalizada os dados foram analisados.

- 2º Parte:
 
Dividimos os dados para uma parte ser usada para o treino e outra para ser prevista, assim podemos avaliar a eficácia e os resultados, adiciona-se o módulo de treinar modelo e o de regressão linear (algoritmo escolhido pois é mais fácil e rápido de treinar), por fim é inserido a ação de pontuar modelo para prever os dados retidos anteriormente com o modelo criado e assim fazer uma comparação com os valores reais e os previstos.

- 3º Parte:

É inserido o módulo de avaliar modelo para sabermos a eficácia do nosso modelo.

Só com esses dados já podemos determinar se as notas de matemática e ciência da natureza seguem um padrão de semelhança, mas como uma outra etapa poderíamos adicionar a pipeline em tempo real para receber dados externos ao dataset. 

---
Conclui-se então que sim, o aluno mantém o desempenho em ambas as provas de maneira parecida, conforme os resultados comparados e previstos, podemos ver que a média das notas de matemática e ciência da natureza se assemelham bastante, o modelo utilizado não teve uma performance muito precisa, porém esse exercício não exige tamanha exatidão e sim uma boa aproximação, então o "custo-benefício" desse algoritmo ainda pode se caracterizar válido. 
