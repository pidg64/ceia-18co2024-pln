# Procesamiento del Lenguaje Natural - 18Co2024

Este repositorio contiene la resolución de los desafíos semanales de la materia **Procesamiento del Lenguaje Natural**, correspondiente a la cohorte **18Co2024**.

## Docentes

- Dr. Rodrigo Cardenas Szigety
- Dr. Nicolás Vattuone

## Descripción

El repositorio será utilizado para almacenar y versionar las soluciones desarrolladas para los distintos desafíos prácticos que se presenten a lo largo del curso.

---

## Desafíos realizados

### Desafío 1 - Análisis de similitud y clasificación de textos

Este proyecto aborda tareas fundamentales de procesamiento de texto utilizando el dataset 20 Newsgroups, que contiene documentos clasificados en diferentes categorías temáticas. El trabajo se divide en tres partes principales:

1. Vectorización y Similitud de Documentos: Se vectorizaron los documentos usando TF-IDF y se seleccionaron 5 documentos al azar para medir su similitud con el resto. Se observó que los documentos más similares suelen pertenecer a la misma categoría y comparten vocabulario, validando la utilidad de la representación vectorial. Sin embargo, cuando la similitud es baja, la relación semántica no siempre es clara.
2. Clasificación con Naïve Bayes: Se entrenaron modelos de clasificación (MultinomialNB y ComplementNB) para maximizar el F1-score macro. Se probó el impacto de eliminar stopwords y de usar unigramas y bigramas. La mejor configuración permitió alcanzar un F1-score macro de aproximadamente 0.70 con ComplementNB.
3. Similitud entre Palabras: Al transponer la matriz documento-término, se estudió la similitud entre palabras seleccionadas manualmente, comprobando que la vectorización TF-IDF también permite analizar relaciones contextuales entre términos.

**Conclusión:** El desafío muestra cómo técnicas básicas de vectorización y modelos clásicos de clasificación pueden ser efectivos para analizar y clasificar textos, así como para explorar relaciones semánticas simples entre palabras.

---

### Desafío 2 - Entrenamiento y análisis de embeddings Word2Vec sobre Harry Potter

En este proyecto se entrenó un modelo de embeddings Word2Vec utilizando como corpus los siete libros de Harry Potter. El flujo de trabajo fue el siguiente:

1. Preprocesamiento del corpus: Lectura, segmentación en oraciones y tokenización de los textos.
2. Entrenamiento del modelo Word2Vec: Se entrenó un modelo skip-gram sobre el corpus procesado, obteniendo representaciones vectoriales para las palabras más frecuentes.
3. Pruebas y análisis: Se exploró la similitud semántica entre palabras, detección de outliers y analogías vectoriales, mostrando que el modelo capta relaciones relevantes del universo Harry Potter.
4. Visualización: Proyección 3D de embeddings seleccionados usando PCA, observando agrupamientos coherentes de personajes y casas.

**Resultados principales:** El modelo Word2Vec logró capturar relaciones semánticas relevantes y permite explorar la estructura narrativa del corpus literario.

**Conclusión:** Con un preprocesamiento adecuado y un modelo Word2Vec bien configurado, es posible obtener representaciones vectoriales útiles para analizar relaciones semánticas y explorar la estructura narrativa de un corpus literario.

---

### Desafío 3 - Modelado de lenguaje a nivel de caracteres con redes recurrentes

En este proyecto se entrenaron y compararon modelos de lenguaje basados en redes neuronales recurrentes (RNN) sobre el texto del primer libro de Harry Potter, utilizando una tokenización a nivel de caracteres.

1. Preprocesamiento y tokenización: Normalización y tokenización del texto a nivel de caracteres, generando secuencias para entrenamiento y validación.
2. Definición y entrenamiento de modelos: Se implementaron SimpleRNN, LSTM y GRU, entrenando cada uno y evaluando la evolución de la perplejidad.
3. Generación de texto: Se probaron diferentes estrategias de generación (greedy, sampling, beam search), observando que el modelo GRU combinado con beam search estocástico logra el mejor balance entre diversidad y coherencia.

**Resultados principales:** El modelo GRU superó a SimpleRNN y LSTM tanto en perplejidad como en calidad de texto generado. El uso de beam search estocástico permitió obtener secuencias más creativas y coherentes.

**Conclusión:** La arquitectura y la estrategia de decodificación son claves en el modelado de lenguaje. Las GRU, combinadas con beam search estocástico, ofrecen una solución eficiente y de alta calidad para la generación de texto a nivel de caracteres.

---

### Desafío 4 - Traducción automática inglés-español con LSTM y PyTorch puro

En este proyecto se implementó un sistema de traducción automática de inglés a español utilizando una arquitectura encoder-decoder basada en LSTM, desarrollada íntegramente en PyTorch.

1. Carga y preprocesamiento del dataset: Corpus de pares de oraciones inglés-español, análisis de cobertura de vocabulario, tokenización y padding.
2. Construcción de vocabularios y embeddings: Vocabularios limitados a las palabras más frecuentes, embeddings GloVe para el encoder y embeddings entrenables para el decoder.
3. Arquitectura del modelo: Encoder y decoder con dos capas LSTM, 512 unidades y dropout 0.3. Teacher forcing durante el entrenamiento.
4. Entrenamiento y evaluación: 20 épocas con early stopping, descenso sostenido de la pérdida y leve overfitting al final.
5. Pruebas y resultados: Traducciones razonables para frases simples, aunque con algunas repeticiones o errores gramaticales.

**Conclusión:** El desafío permitió construir un traductor secuencial funcional y comprender en profundidad cada etapa de una arquitectura encoder-decoder en PyTorch. Constituye una base sólida para futuras mejoras, como la incorporación de mecanismos de atención o el uso de subwords.
