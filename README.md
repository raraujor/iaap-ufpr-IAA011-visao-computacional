# IAA011 Visão Computaciona

## Equipe 03
-	Gustavo Costa de Souza
-	Marcos Vinicius de Melo
-	Marcus Eneas Silveira Galvao do Rio Apa II
-	Patrícia Verdugo Pascoal
-	Rodrigo de Araujo
-	William de Souza Alencar


## 1. Extração de Características
Os bancos de imagens fornecidos são conjuntos de imagens de 250x250 pixels de imuno-histoquímica (biópsia) de câncer de mama. No total são 4 classes (0, 1+, 2+ e 3+) que estão divididas em diretórios. O objetivo é classificar as imagens nas categorias correspondentes. Uma base de imagens será utilizada para o treinamento e outra para o teste do treino. As imagens fornecidas são recortes de uma imagem maior do tipo WSI (Whole Slide Imaging) disponibilizada pela Universidade de Warwick (link). A nomenclatura das imagens segue o padrão XX_HER_YYYY.png, onde XX é o número do paciente e YYYY é o número da imagem recortada. Separe a base de treino em 80% para treino e 20% para validação. Separe por pacientes (XX), não utilize a separação randômica! Pois, imagens do mesmo paciente não podem estar na base de treino e de validação, pois isso pode gerar um viés. No caso da CNN VGG16 remova a última camada de classificação e armazene os valores da penúltima camada como um vetor de características. Após o treinamento, os modelos treinados devem ser validados na base de teste.

### Tarefas:

Carregue a base de dados de Treino.
Crie partições contendo 80% para treino e 20% para validação (atenção aos pacientes).
Extraia características utilizando LBP e a CNN VGG16 (gerando um csv para cada extrator).
Treine modelos Random Forest, SVM e RNA para predição dos dados extraídos (nessa tarefa utilize todas as imagens para o treinamento).
Carregue a base de Teste e execute a tarefa 3 nesta base.
Aplique os modelos treinados nos dados de teste.
Calcule as métricas de Sensibilidade, Especificidade e F1-Score com base em suas matrizes de confusão.
Indique qual modelo dá o melhor o resultado e a métrica utilizada

## 2. Redes Neurais
Utilize as duas bases do exercício anterior para treinar as Redes Neurais Convolucionais VGG16 e a Resnet50. Utilize os pesos pré-treinados (Transfer Learning), refaça as camadas Fully Connected para o problema de 4 classes. Treine só as novas camadas. Compare os treinos de 10 épocas com e sem Data Augmentation. Tanto a VGG16 quanto a Resnet50 têm como camada de entrada uma imagem 224x224x3, ou seja, uma imagem de 224x224 pixels coloridos (3 canais de cores). Portanto, será necessário fazer uma transformação de 250x250x3 para 224x224x3. Ao fazer o Data Augmentation cuidado para não alterar demais as cores das imagens e atrapalhar na classificação.

### Tarefas:

Utilize a base de dados de Treino já separadas em treino e validação do exercício anterior.
Treine modelos VGG16 e Resnet50 adaptadas com e sem Data Augmentation
Aplique os modelos treinados nas imagens da base de Teste
Calcule as métricas de Sensibilidade, Especificidade e F1-Score com base em suas matrizes de confusão.
Indique qual modelo dá o melhor o resultado e a métrica utilizada
