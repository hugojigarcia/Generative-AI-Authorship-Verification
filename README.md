# NLP

## Participantes
- Hugo Jiménez García
- Alonso Cañas Rico


## Tabla de resultados

| Modelo                                     | Dataset | Accuracy  | Roc-Auc    | Brier      | c@1       | F1          | F0.5U       | Mean       |
|-------------------------------------------|---------|-----------|------------|------------|-----------|-------------|-------------|------------|
| Modelo Individual - Bert | Test | 0.99632353 | 0.99981528 | 0.99257655 | 0.99632353 | 0.99658703 | 0.99643007 | 0.79931587 |
| Modelo Individual - Preentrenado - Última capa no congelada | Train | 0.9961 | 0.9993 | 0.0046 | 0.9961 | 0.9964 | 0.9963 | 0.7986 |
| Modelo Individual - Preentrenado - Última capa no congelada | Val | 0.9910 | 0.9987 | 0.0086 | 0.9910 | 0.9916 | 0.9928 | 0.7965 |
| Modelo Individual - Preentrenado - Última capa no congelada | Test | 0.99519231 | 0.99952821 | 0.99403501 | 0.99519231 | 0.99554157 | 0.99475891 | 0.99581120 |
| Modelo Individual - Preentrenado - Congelada | Test | 0.97963801 | 0.99794743 | 0.98289116 | 0.97963801 | 0.98103267 | 0.98289696 | 0.98488125 |
| Modelo Individual Concatenar Embeddings - Bert | Train   | 0.9998867 | 1.0        | 0.99989529 | 0.9998867 | 0.99989481  | 0.99983171  | 0.99990171 |
| Modelo Individual Concatenar Embeddings - Bert | Val     | 0.9932127 | 0.99971165 | 0.99362484 | 0.9932127 | 0.99369748  | 0.99369748  | 0.99478882 |
| Modelo Individual Concatenar Embeddings - Bert | Test    | 0.9892534 | 0.99933351 | 0.99101462 | 0.9892534 | 0.99004715  | 0.98849372  | 0.99162848 |


## Explicación de modelos
Para cada tipo de modelo, se ha probado tanto con bert-base-uncased como con Lau123/distilbert-base-uncased-detect_ai_generated_text, un modelo prentrenado para la tarea de clasificación de textos según si su autor es humano o una IA.

### Modelo Individual 


### Modelo Individual Concatenar Embeddings


### Modelo Siamés

### Enfoque de aprendizaje contrastivo
Se investigó como poder aplicar este tipo de entrenamiento para esta tarea, pero finalmente nos enfocamos más en el resto de aproximaciones, puesto que nos daban buenos resultados.



## Create env
```
python -m venv venv
venv\Scripts\activate

python.exe -m pip install --upgrade pip
pip install -r requirements.txt
```

## Compile requirements
```
pip install pip-tools==7.4.1
pip-compile requirements.in
```