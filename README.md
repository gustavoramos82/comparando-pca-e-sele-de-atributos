# Semente de aboboras: comparando pca e seleção de atributos

Neste projeto, a partir de um dataset retirado do kaggle (que pode ser obtido [aqui](https://www.kaggle.com/datasets/muratkokludataset/pumpkin-seeds-dataset)), cujo objetivo e classificar diferentes tipos de sementes de abobora,entretanto, observa-se que se têm atributos altamente correlacionado, como podemos ver abaixo:

![image](https://github.com/gustavoramos82/comparando-pca-e-sele-de-atributos/assets/39843884/04d5e9fa-7c59-4a7c-85c4-016befedb422)

A partir disso, vamos tentar aplicar modelos de *machine learning* de três formas:

- Aplicando as trezes colunas que vem no dataset
- Removendo as colunas altamente correlacionadas
- Aplicando PCA

E nesse caso, qual seria melhor e qual tem a melhor perfomace, para isso, foi utilizado os seguintes modelos para classificação:

- Reegressão Logistica
- KNN
- SVM
- GaussianNB (naive bayes em que supõe um distribuição gauusiana)
- Árvore de Decisão
- Random Forest
- Extra tree
- Gradiente Boosting
- Histogram-based Gradient Boosting Classification 

## Baseline

Rodando o modelo com as treze colunas, as melhores méticas foram com SVM e Rando Forest, que foram

![image](https://github.com/gustavoramos82/comparando-pca-e-sele-de-atributos/assets/39843884/50724a12-c434-41f5-b0a4-df704e812587)

![image](https://github.com/gustavoramos82/comparando-pca-e-sele-de-atributos/assets/39843884/26c2244f-e1f7-429c-9f5e-7b8170c64ee6)

## Seleção de atributos

Nessa parte em vez de trabalhar as trezes colunas foram removidas as colunas que são altamente correlacionadas entre si, e no caso foram tirado
as seguintes colunas: 'Perimeter','Convex_Area','Equiv_Diameter','Roundness','Compactness'

Com isso rodou novamente o modelo, e os modelo que tiveram as melhores métricas foram o SVM e o Hist gradiente boosting, que foram

![image](https://github.com/gustavoramos82/comparando-pca-e-sele-de-atributos/assets/39843884/91ad8c81-3f5a-4abc-9759-d337a17ce59f)

![image](https://github.com/gustavoramos82/comparando-pca-e-sele-de-atributos/assets/39843884/80effdc3-5405-4ac0-b2fb-f206366d70a6)

## Aplicando PCA

Aplicando pca para reduzir a 7 colunas, os melhore foram o SVM e o Extra tree, que foram

![image](https://github.com/gustavoramos82/comparando-pca-e-sele-de-atributos/assets/39843884/9621eafb-8c1c-4cc0-9bef-445833565886)

![image](https://github.com/gustavoramos82/comparando-pca-e-sele-de-atributos/assets/39843884/c531aa7f-eb6a-4ead-8d50-7f3807860ca1)


## Conclusão

- Podemos ver que o modelo SVM foi o que saiu bem em todas as situações
- O PCA não teve muita difreença para o baseline, entretanto a seleção de atributos foi o que se mostrou melhor
- Nesse caso considerando as sementes, o melhor modelo não precisa ser o melhor em décimos, logo nesse caso, o caso da seleção de atributos seria o melhor,
usando ou o SVM ou o Hist gradiente boosting, dependendo do caso.

### O que pode ser feito para melhorar a perfomace

Já sabemos que a seleção dos atributos é a melhor,então poderiamos fazer:
- mudar os parametros do modelo para ter uma melhor perfomace
- cross validation para avaliar mlehort os modelos
- tentar outras variações do pca como o kernel pca para verificar se tem alguma melhora
