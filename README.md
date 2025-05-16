Classificação de Imagens de Estéril e Mineral

Objetivo
Este projeto tem como objetivo desenvolver e treinar um modelo de inteligência artificial capaz de distinguir automaticamente imagens de material estéril e mineral proveniente de operações de mineração. A iniciativa visa automatizar a triagem visual de amostras geológicas, auxiliando na melhoria da eficiência operacional e na redução de erros humanos no processo de classificação de materiais extraídos.

Metodologia
O trabalho foi estruturado nas seguintes etapas:

Coleta e Organização das Imagens
As imagens foram organizadas em um diretório denominado model_1, contendo duas subpastas: mineral e esteril, correspondentes às classes alvo do modelo.

Pré-processamento
As imagens foram carregadas utilizando a biblioteca cv2, convertidas para RGB e redimensionadas para 224x224 pixels. Posteriormente, os dados foram normalizados (valores de pixel entre 0 e 1) e as classes foram codificadas com LabelBinarizer.

Divisão da Base de Dados
O conjunto de dados foi dividido em subconjuntos de treino e teste utilizando train_test_split, com balanceamento das classes.

Arquitetura da Rede Neural
A base do modelo é a arquitetura pré-treinada VGG16 (transfer learning), com camadas adicionais de Flatten, Dense, Dropout e Softmax para adaptação ao problema binário. Apenas as camadas finais foram treinadas.

Treinamento
O modelo foi treinado por 15 épocas, com taxa de aprendizado inicial de 0.001 e batch size de 30. Utilizou-se Adam como otimizador e categorical_crossentropy como função de perda.

Avaliação
O desempenho foi avaliado através de métricas como acurácia, precisão, recall e F1-score, além da matriz de confusão. Também foram gerados gráficos de perda e acurácia por época.

Conclusões
O modelo treinado demonstrou bom desempenho na tarefa de classificação binária entre material mineral e estéril, alcançando valores satisfatórios de acurácia e F1-score nos dados de teste. A utilização de transferência de aprendizado com VGG16 permitiu acelerar o processo de convergência e extrair características robustas mesmo com um conjunto de dados relativamente pequeno. A abordagem se mostrou promissora para aplicação em campo, podendo ser embarcada em sistemas de inspeção automatizada com câmeras industriais. Melhorias futuras incluem o aumento da base de dados, testes com arquiteturas mais leves (ex: MobileNet) e deploy em edge devices.
