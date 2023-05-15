## Descrição do Gradiente Descendente para Ajuste de Parábola

Este código foi desenvolvido como parte do Curso Superior de Tecnologia em Ciência de Dados da Faculdade de Tecnologia da Baixada Santista - Rubens Lara. O objetivo é encontrar a melhor parábola que se ajusta a um conjunto de treinamento, minimizando o erro.

### Importações e Pré-Definições
O código inicia importando as bibliotecas necessárias, como `matplotlib.pyplot` e `tqdm`. Além disso, define-se o estilo de plotagem para o gráfico utilizando $\texttt{plt.style.use('ggplot')}$.

### Dados de Treinamento
O conjunto de treinamento é fornecido como uma lista de pontos no plano, representando as coordenadas $(x, y)$. Os pontos de treinamento são os seguintes:

$$(1, 4), (-1, 5), (2, 7), (-2, 8), (3, 12), (-3, 13), (4, 19), (-4, 20)$$

### Função do Gradiente Descendente
A função $\texttt{GradDesc}$ implementa o Gradiente Descendente para ajuste da parábola. Ela recebe como entrada os coeficientes iniciais $w_1$, $w_2$, $b$ e a taxa de aprendizagem $\texttt{lr}$ ($\gamma$).

Dentro da função, há um loop que itera até que o erro seja menor do que um determinado limiar predefinido. Em cada iteração, o algoritmo calcula o erro quadrático médio entre as previsões da parábola e os valores reais do conjunto de treinamento.

A parábola é definida pela função $y = w_1x^2 + w_2x + b$, onde $w_1$, $w_2$ e $b$ são os coeficientes a serem otimizados.

Em seguida, são calculados os gradientes das variáveis $w_1$, $w_2$ e $b$, usando as derivadas parciais da função de custo em relação a cada coeficiente. Esses gradientes indicam a direção de maior declive da função de custo, permitindo ajustar os coeficientes na direção de minimização do erro.

Os coeficientes são atualizados multiplicando a taxa de aprendizagem pelos gradientes calculados. Esse processo é repetido até que o erro seja menor do que o limiar definido.

Durante a execução do Gradiente Descendente, uma barra de carregamento é exibida utilizando a biblioteca $\texttt{tqdm}$, mostrando o número de iterações, o valor do erro, os valores atualizados dos coeficientes $w_1$, $w_2$ e $b$.

Ao final das iterações, os coeficientes otimizados $w_1$, $w_2$ e $b$ são retornados pela função $\texttt{GradDesc}$.

### Execução e Impressão dos Resultados
O algoritmo é executado chamando a função $\texttt{GradDesc}$ com os coeficientes iniciais e a taxa de aprendizagem desejada. Os coeficientes otimizados são então impressos na tela, mostrando os valores finais de $w_1$, $w_2$ e $b$.

Este código é um exemplo de aplicação do Gradiente Descendente para ajuste de uma parábola aos dados de treinamento fornecidos. Pode ser utilizado como base para realizar ajustes de parábolas em outros conjuntos de dados.

## Equações

A função da parábola a ser ajustada é definida por:

$$
y = w_1x^2 + w_2x + b
$$

O erro quadrático médio entre as previsões da parábola e os valores reais do conjunto de treinamento é calculado pela seguinte equação:

$$
\text{{erro}} = \frac{1}{N} \sum_{i=1}^{N} \left( y_i - (w_1x_i^2 + w_2x_i + b) \right)^2
$$

Onde $N$ é o número de pontos de treinamento, $x_i$ é a coordenada x do ponto $i$ e $y_i$ é a coordenada y correspondente.

Os gradientes em relação aos coeficientes $w_1$, $w_2$ e $b$ são calculados pelas seguintes equações:

$$
\frac{\partial \text{{erro}}}{\partial w_1} = -\frac{2}{N} \sum_{i=1}^{N} x_i^2 \left( y_i - (w_1x_i^2 + w_2x_i + b) \right)
$$

$$
\frac{\partial \text{{erro}}}{\partial w_2} = -\frac{2}{N} \sum_{i=1}^{N} x_i \left( y_i - (w_1x_i^2 + w_2x_i + b) \right)
$$

$$
\frac{\partial \text{{erro}}}{\partial b} = -\frac{2}{N} \sum_{i=1}^{N} \left( y_i - (w_1x_i^2 + w_2x_i + b) \right)
$$

Os coeficientes são atualizados de acordo com a seguinte regra:

$$
w_1 = w_1 - \text{{lr}} \frac{\partial \text{{erro}}}{\partial w_1}
$$

$$
w_2 = w_2 - \text{{lr}} \frac{\partial \text{{erro}}}{\partial w_2}
$$

$$
b = b - \text{{lr}} \frac{\partial \text{{erro}}}{\partial b}
$$

Onde $\text{{lr}}$ é a taxa de aprendizagem.

Durante a execução do Gradiente Descendente, a barra de carregamento exibe o número de iterações, o valor do erro, os valores atualizados dos coeficientes $w_1$, $w_2$ e $b$.

Ao final das iterações, os coeficientes otimizados $w_1$, $w_2$ e $b$ são impressos na tela.

Espero que essa descrição ajude a entender o funcionamento do código e o processo de ajuste da parábola utilizando o Gradiente Descendente.
