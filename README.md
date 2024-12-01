# NLP

## Participantes
- Hugo Jiménez García
- Alonso Cañas Rico

## Tabla de resultados

| Modelo                                     | Dataset | Accuracy  | Roc-Auc    | Brier      | c@1       | F1          | F0.5U       | Mean       |
|-------------------------------------------|---------|-----------|------------|------------|-----------|-------------|-------------|------------|
| Modelo Individual Concatenar Embeddings - Bert | Train   | 0.9998867 | 1.0        | 0.00010471 | 0.9998867 | 0.99989481  | 0.99983171  | 0.99990171 |
| Modelo Individual Concatenar Embeddings - Bert | Val     | 0.9932127 | 0.99971165 | 0.00637516 | 0.9932127 | 0.99369748  | 0.99369748  | 0.99478882 |
| Modelo Individual Concatenar Embeddings - Bert | Test    | 0.9892534 | 0.99933351 | 0.00898538 | 0.9892534 | 0.99004715  | 0.98849372  | 0.99162848 |


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