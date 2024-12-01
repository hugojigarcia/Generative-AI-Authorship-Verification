# NLP

## Participantes
- Hugo Jiménez García
- Alonso Cañas Rico


## Introducción
Para realizar la tarea de determinar cuál de los textos en un par fue generado por un humano y cuál por una IA, hemos empleado diversos enfoques que serán explicados más adelante.

El primer paso consiste en procesar los datos y organizarlos en el formato requerido: pares de textos, donde uno ha sido redactado por un humano y el otro por una IA. Además, cada par de textos estará acompañado de una etiqueta que indica cuál es el texto humano.

Las etiquetas se definen de la siguiente manera:

- 0: el primer texto del par es el redactado por un humano, y el segundo fue generado por una IA.
- 1: el segundo texto del par es el redactado por un humano, y el primero fue generado por una IA.

Dado que cada texto pertenece a un ID específico, las combinaciones se realizaron únicamente entre los textos asociados al mismo ID. Es decir, para un ID dado, se generaron todas las combinaciones posibles de pares humano-IA dentro de ese mismo ID.

La división en los conjuntos de train, validación y test también se realizó respetando los IDs. En concreto:

- 62'5% de los IDs se asignaron al conjunto de train.
- 12'5% de los IDs al conjunto de validación.
- 25% de los IDs IDs al conjunto de test.

Este enfoque garantiza que no haya "trampas", ya que evita que combinaciones de un mismo ID aparezcan en diferentes conjuntos de datos. Si esto ocurriera, el modelo podría estar siendo evaluado con datos que ya había visto durante su entrenamiento, comprometiendo así la validez de los resultados.


## Tabla de resultados

| Modelo                                     | Dataset | Accuracy  | Roc-Auc    | Brier      | c@1       | F1          | F0.5U       | Mean       |
|-------------------------------------------|---------|-----------|------------|------------|-----------|-------------|-------------|------------|
| Modelo Individual - Bert - Congelado| Train | 0.94380877 | 0.98509176 | 0.93101753 | 0.94380877 | 0.94773446 | 0.94869415 | 0.95126933 |
| Modelo Individual - Bert - Congelado| Val | 0.95418552 | 0.98920487 | 0.94012256 | 0.95418552 | 0.95716552 | 0.96112999 | 0.96036169 |
| Modelo Individual - Bert - Congelado| Test | 0.95361991 | 0.98982985 | 0.93798217 | 0.95361991 | 0.95675105 | 0.95917936 | 0.95947247 |
| Modelo Individual - Bert - Última capa no congelada | Train | 0.99739436 | 0.99992248 | 0.99551480 | 0.99739436 | 0.99758124 | 0.99739244 | 0.99756106 |
| Modelo Individual - Bert - Última capa no congelada | Val | 0.99830317 | 0.99976443 | 0.99529791 | 0.99830317 | 0.99842520 | 0.99811083 | 0.99798031 |
| Modelo Individual - Bert - Última capa no congelada | Test | 0.99632353 | 0.99981528 | 0.99257655 | 0.99632353 | 0.99658703 | 0.99643007 | 0.79931587 |
| Modelo Individual - Preentrenado - Congelada | Train | 0.97394358 | 0.99617202 | 0.97802812 | 0.97394358 | 0.97578947 | 0.97615939 | 0.98001852 |
| Modelo Individual - Preentrenado - Congelada | Val | 0.98472851 | 0.99719116 | 0.98411381 | 0.98472851 | 0.98582677 | 0.98551637 | 0.98747532 |
| Modelo Individual - Preentrenado - Congelada | Test | 0.97963801 | 0.99794743 | 0.98289116 | 0.97963801 | 0.98103267 | 0.98289696 | 0.98488125 |
| Modelo Individual - Preentrenado - Última capa no congelada | Train | 0.9961 | 0.9993 | 0.0046 | 0.9961 | 0.9964 | 0.9963 | 0.7986 |
| Modelo Individual - Preentrenado - Última capa no congelada | Val | 0.9910 | 0.9987 | 0.0086 | 0.9910 | 0.9916 | 0.9928 | 0.7965 |
| Modelo Individual - Preentrenado - Última capa no congelada | Test | 0.99519231 | 0.99952821 | 0.99403501 | 0.99519231 | 0.99554157 | 0.99475891 | 0.99581120 |
| Modelo Individual Concatenar Embeddings - Bert - Congelado | Train   | 0.7944942 | 0.87691638 | 0.17975273 | 0.7944942 | 0.81139530  | 0.80576550  | 0.82176372 |
| Modelo Individual Concatenar Embeddings - Bert - Congelado | Val     | 0.7980769 | 0.88917681 | 0.17542979 | 0.7980769 | 0.81121100  | 0.81457094  | 0.82752118 |
| Modelo Individual Concatenar Embeddings - Bert - Congelado | Test    | 0.8127828 | 0.88928977 | 0.17763947 | 0.8127828 | 0.82588112  | 0.82666386  | 0.83539562 |
| Modelo Individual Concatenar Embeddings - Bert - Última capa no congelada | Train   | 0.9998867 | 1.0        | 0.99989529 | 0.9998867 | 0.99989481  | 0.99983171  | 0.99990171 |
| Modelo Individual Concatenar Embeddings - Bert - Última capa no congelada | Val     | 0.9932127 | 0.99971165 | 0.99362484 | 0.9932127 | 0.99369748  | 0.99369748  | 0.99478882 |
| Modelo Individual Concatenar Embeddings - Bert - Última capa no congelada | Test    | 0.9892534 | 0.99933351 | 0.99101462 | 0.9892534 | 0.99004715  | 0.98849372  | 0.99162848 |
| Modelo Individual Concatenar Embeddings - Preentrenado - Congelado | Train   | 0.7976663 | 0.89574215 | 0.15099982 | 0.7976663 | 0.82964517  | 0.78567041  | 0.83154483 |
| Modelo Individual Concatenar Embeddings - Preentrenado - Congelado | Val     | 0.8076923 | 0.90136477 | 0.14482791 | 0.8076923 | 0.83653846  | 0.79612006  | 0.83937754 |
| Modelo Individual Concatenar Embeddings - Preentrenado - Congelado | Test    | 0.8057127 | 0.90345982 | 0.14605282 | 0.8057127 | 0.83654532  | 0.79189189  | 0.83831138 |
| Modelo Individual Concatenar Embeddings - Preentrenado  - Última capa no congelada | Train   | 0.9873117 | 0.99901651 | 0.01027358 | 0.9873117 | 0.98827961  | 0.98518673  | 0.98990419 |
| Modelo Individual Concatenar Embeddings - Preentrenado  - Última capa no congelada | Val     | 0.9796380 | 0.99611242 | 0.01720775 | 0.9796380 | 0.98126951  | 0.97578642  | 0.98311972 |
| Modelo Individual Concatenar Embeddings - Preentrenado  - Última capa no congelada | Test    | 0.9694570 | 0.99619947 | 0.02372124 | 0.9694570 | 0.97175732  | 0.96932387  | 0.97660329 |
| Modelo Siames - Bert Congelado              | Train   | 0.5384615 | 0.50763459 | 0.27385091 | 0.5384615 | 0.70000000  | 0.59322034  | 0.61309311 |
| Modelo Siames - Bert Congelado              | Val     | 0.5384615 | 0.49855438 | 0.27519247 | 0.5384615 | 0.70000000  | 0.59322034  | 0.61100876 |
| Modelo Siames - Bert Congelado              | Test    | 0.5384615 | 0.49893285 | 0.27384061 | 0.5384615 | 0.70000000  | 0.59322034  | 0.61135482 |
| Modelo Siames - Bert - Última capa no congelada | Train | 0.49507194 | 0.49930613 | 0.73494949 | 0.49507194 | 0.51643702 | 0.52633907 | 0.55442073 |
| Modelo Siames - Bert - Última capa no congelada | Val | 0.49717195 | 0.49737846 | 0.73385354 | 0.49717195 | 0.50196078 | 0.52287582 | 0.55064811 |
| Modelo Siames - Bert - Última capa no congelada | Test | 0.49321267 | 0.49993451 | 0.73410456 | 0.49321267 | 0.51905529 | 0.52600087 | 0.46081975 |
| Modelo Siames - Preentrenado - Última capa no congelada | Train | 0.53846154 | 0.49575905 | 0.74125414 | 0.53846154 | 0.70000000 | 0.59322034 | 0.61373901 |
| Modelo Siames - Preentrenado - Última capa no congelada | Val | 0.53846154 | 0.49727225 | 0.73863060 | 0.53846154 | 0.70000000 | 0.59322034 | 0.61351695 |
| Modelo Siames - Preentrenado - Última capa no congelada | Test | 0.53846154 | 0.50742873 | 0.73908130 | 0.53846154 | 0.70000000 | 0.59322034 | 0.61563838 |


## Explicación de modelos
Para cada tipo de modelo, se ha probado tanto con bert-base-uncased como con Lau123/distilbert-base-uncased-detect_ai_generated_text, un modelo prentrenado para la tarea de clasificación de textos según si su autor es humano o una IA.

Las pruebas se llevaron a cabo en notebooks separados, variando entre ellas en dos aspectos principales:

- La definición del modelo, incluyendo tanto la arquitectura como el modelo seleccionado para el fine-tuning.
- Los hiperparámetros utilizados en el proceso de entrenamiento.

Se cuenta con un hiperparámetro llamado LAYERS_TO_TRAIN, el cual indica la cantidad de capas del modelo original a entrenar (ya sea bert-base-uncased o distilbert-base-uncased-detect_ai_generated_text), tomando siempre las finales. Es decir, si el parámetro es LAYERS_TO_TRAIN=1, todos los pesos del modelo original estarán congelados salvo la última capa. En cualquier caso, se ha tomado la decisión de que siempre se reentrenen los parámetros de la capa pooler.dense, incluso cuando LAYERS_TO_TRAIN=0. Esto es para asegurar que siempre se realiza un fine-tuning del modelo original.


### Modelo Individual 
Utiliza los modelos bert-base-uncased y distilbert-base-uncased-detect_ai_generated_text para realizar una predicción sobre cada uno de los textos de la pareja por separado. Luego dictamina que texto es el humano según cuál de los dos resultados es mayor.


### Modelo Individual Concatenar Embeddings
Se realiza una concatenación de los dos textos de la pareja unidos por el token [SEP] (esto lo hace automáticamente el tokenizer). A continuación, se le introduce al modelo y este genera unos embeddings (last_hidden_state), los cuales son procesados por otra capa densa y se devuelve un output que indica qué texto es el generado por humano.


### Modelo Siamés
Se realizan los embeddings de los dos textos usando el modelo base. Luego pasa por otra capa densa, se calcula la similaridad coseno y se emplea una última capa densa para clasificar qué texto es el generado por humano.


### Enfoque de aprendizaje contrastivo
Se investigó como poder aplicar este tipo de entrenamiento para esta tarea, pero finalmente nos enfocamos más en el resto de aproximaciones, puesto que nos daban buenos resultados.