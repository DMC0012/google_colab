# 📚 Sistema RAG con Python en Google Colab

Este proyecto presenta la implementación de un **sistema RAG (Retrieval-Augmented Generation)** desarrollado en **Python** y ejecutado en **Google Colab**, cuyo propósito es crear un chatbot capaz de responder preguntas utilizando información previamente almacenada en documentos.

El sistema integra **búsqueda semántica** con **modelos de lenguaje**, lo que permite generar respuestas más coherentes y basadas en contenido relevante.

---

# 🚀 Tecnologías utilizadas

- Python  
- LangChain  
- FAISS (motor de búsqueda vectorial)  
- Sentence Transformers (para generar embeddings)  
- Transformers (HuggingFace)  
- TinyLlama 1.1B Chat  
- ipywidgets (interfaz interactiva en Colab)  
- PyTorch  

---

# ⚙️ Funcionamiento del sistema

El funcionamiento del sistema RAG se organiza en las siguientes etapas:

## 1️⃣ Preparación de documentos
Se recopila un conjunto de textos con información relevante sobre diferentes temas, que servirán como base de conocimiento.

## 2️⃣ División del contenido
Los documentos se separan en fragmentos más pequeños mediante un **Text Splitter**, lo que facilita encontrar información específica con mayor precisión.

## 3️⃣ Creación de embeddings
Cada fragmento de texto se convierte en un **vector numérico** utilizando modelos de *Sentence Transformers*, permitiendo comparar significados entre textos.

## 4️⃣ Almacenamiento vectorial
Los embeddings se guardan en una base de datos vectorial usando **FAISS**, optimizada para búsquedas rápidas por similitud.

## 5️⃣ Recuperación de información (Retrieval)
Al hacer una pregunta, el sistema:

- Convierte la consulta en un embedding  
- Busca los fragmentos más similares en la base de datos  
- Selecciona los más relevantes  

## 6️⃣ Generación de respuesta (Generation)
Los fragmentos recuperados se utilizan como contexto para el modelo (**TinyLlama**), el cual genera una respuesta basada únicamente en esa información.

## 7️⃣ Interfaz de usuario
Se implementa una interfaz sencilla con **ipywidgets** que permite:

- Escribir preguntas  
- Ejecutar la búsqueda  
- Ver el contexto encontrado  
- Mostrar la respuesta generada  

---

# 💬 Ejemplo de flujo

1. El usuario introduce una pregunta.  
2. El sistema procesa la consulta y busca información relacionada.  
3. Se identifican los fragmentos más relevantes.  
4. Se construye un prompt con ese contexto.  
5. El modelo genera una respuesta fundamentada en los datos obtenidos.  

---

# 📦 Instalación de dependencias

El notebook incluye la instalación automática de las librerías necesarias:

```bash
pip install langchain
pip install langchain-community
pip install langchain-text-splitters
pip install sentence-transformers
pip install transformers
pip install accelerate
pip install faiss-cpu
pip install ipywidgets
