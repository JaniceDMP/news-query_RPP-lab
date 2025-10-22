# Task 1: Sistema de Recuperación de Noticias RPP (RSS)

Este proyecto implementa un sistema de recuperación de información (RAG) que ingiere las últimas 50 noticias del feed RSS de RPP Perú.

El pipeline utiliza LangChain para orquestar el proceso, ingiriendo los datos, dividiéndolos, generando embeddings con `SentenceTransformers`, almacenándolos en `ChromaDB` y permitiendo consultas de similitud semántica.

## Componentes Clave

* **Ingesta de Datos**: `langchain_community.document_loaders.RSSFeedLoader` para leer el feed de RPP.
* **Tokenización/Splitting**: `tiktoken` para análisis y `RecursiveCharacterTextSplitter` para la división de documentos.
* **Embeddings**: `sentence-transformers/all-MiniLM-L6-v2` a través de `HuggingFaceEmbeddings`.
* **Vector Store**: `ChromaDB` para almacenar y consultar los vectores de embeddings.
* **Orquestación**: `LangChain` para unir todo el pipeline.

## ¿Cómo ejecutarlo?

1.  **Clonar el repositorio (si aplica):**
    ```bash
    git clone [URL_DEL_REPO]
    cd [NOMBRE_DEL_REPO]
    ```

2.  **Crear un entorno virtual (recomendado):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # En Windows: venv\Scripts\activate
    ```

3.  **Instalar las dependencias:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Ejecutar el Jupyter Notebook:**
    ```bash
    jupyter notebook RPP_News_Retrieval.ipynb
    ```
