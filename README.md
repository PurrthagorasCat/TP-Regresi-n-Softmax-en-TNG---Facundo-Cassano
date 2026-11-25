# TP1 - Regresión softmax en 20 Newsgroups

Trabajo práctico de Redes Neuronales. Clasificación de los mensajes de 20 Newsgroups en sus 20 categorías con TF-IDF y una regresión softmax en PyTorch, con búsqueda de hiperparámetros en Optuna y registro de los entrenamientos en TensorBoard y MLflow.

Esta es la versión corregida después de la devolución. Al principio del notebook hay una celda que resume qué cambió respecto de la primera entrega.

## Qué hay en el repo

- `01_Softmax_Regression_20Newsgroups.ipynb` es el notebook con la resolución, ejecutado y con todos los outputs.
- `figuras/` tiene los gráficos que genera el notebook (curvas de validación, comparación de learning rate y batch size, loss por batch y las curvas de TensorBoard de la búsqueda).
- `requirements.txt` tiene las librerías con las versiones que usé.

## Cómo reproducirlo

Desde la carpeta del repo, con Python 3.11 o más nuevo.

```bash
python -m venv .venv
source .venv/bin/activate        # en Windows .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook 01_Softmax_Regression_20Newsgroups.ipynb
```

Después hay que ejecutar todas las celdas en orden. El dataset lo descarga scikit-learn la primera vez (unos 14 MB) y los recursos de NLTK se bajan solos si no están. La carpeta `figuras/` se crea desde el código, así que no hace falta crearla a mano. En CPU el notebook completo tarda unos 15 minutos, la mayor parte en el preprocesamiento y en la búsqueda de Optuna.

Para ver los logs después de ejecutarlo.

```bash
tensorboard --logdir runs
mlflow ui
```
