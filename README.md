# Chatbot con red neuronal — clasificación de intenciones

Asistente conversacional en español entrenado desde cero: una red neuronal
clasifica la intención del usuario sobre **784 intenciones** y **2 075 patrones**
de entrenamiento. El modelo se exporta a TensorFlow.js y corre directamente en
el navegador, sin servidor.

### 🔗 [Probar la demo](https://isabh17.github.io/IA1_Proyecto_17.github.io/)

**Stack:** Python · TensorFlow / Keras · NLTK · TensorFlow.js · JavaScript

---

## Cómo funciona

1. **Preprocesamiento** — tokenización y lematización de los patrones con NLTK,
   construyendo el vocabulario (`words.pkl`) y las clases (`classes.pkl`).
2. **Representación** — cada frase se convierte en un vector *bag-of-words*.
3. **Entrenamiento** — red neuronal densa en Keras que clasifica el vector en
   una de las 784 intenciones (`trainingbot.py`).
4. **Despliegue** — el modelo entrenado (`chatbot_model.h5`) se convierte a
   TensorFlow.js (`model/`) y se ejecuta en el navegador desde `app.js`.

La inferencia ocurre del lado del cliente: no hay backend ni llamadas de red.

---

## Estructura

| Archivo | Qué hace |
|---|---|
| `trainingbot.py` | Entrena la red y guarda el modelo |
| `model.py` | Carga el modelo y predice la intención |
| `chatbot.py` | Interfaz de conversación por consola |
| `convertJson.py` | Exporta vocabulario y clases a JSON para el navegador |
| `intents2.json` | Corpus de intenciones, patrones y respuestas |
| `model/` | Modelo convertido a TensorFlow.js |
| `app.js` · `index.html` | Cliente web de la demo |

---

## Ejecutar localmente

```bash
pip install tensorflow nltk numpy
python trainingbot.py    # entrena el modelo
python chatbot.py        # conversa por consola
```

---

## Contexto

Proyecto del laboratorio de Inteligencia Artificial 1, Ingeniería en Ciencias
y Sistemas — Universidad de San Carlos de Guatemala.
