# Simple LLM Application with LangChain

Este repositorio contiene el código y la documentación para un proyecto básico que utiliza **LangChain** y **OpenAI** para construir una aplicación simple de traducción de texto. Este proyecto sigue el tutorial oficial de LangChain: Build a simple LLM application with chat models and prompt templates.

---
## Descripción del Proyecto

El proyecto consiste en una aplicación que traduce texto de inglés a otro idioma utilizando un modelo de lenguaje (LLM) de OpenAI (como GPT-4) y el framework **LangChain**. Se utilizan **prompt templates** para estructurar las entradas al modelo y mejorar la interacción con el LLM.

---

## Requisitos
Para ejecutar este proyecto, necesitas:

1. Una cuenta en OpenAI para obtener una clave API.

2. Un entorno de Google Colab o un entorno local con Python 3.8+.

3. Las siguientes bibliotecas de Python:
    - openai

## **Instalación**

Sigue estos pasos para configurar el proyecto:

1. Clona este repositorio:
    
    ```python

     git clone https://github.com/juliandtrianar/AREP_TALLER_LLM/tree/d5b434cb305eb877bd507d777eedee756df2f7a8/TutorialLLM_chain

    ```
    
2. Instala las dependencias:
    
    ```python
    !pip install langchain
    !pip install -qU "langchain[openai]"
    ```
    
3. Configura las variables de entorno:
    - Crea un archivo `.env` en la raíz del proyecto y añade tu clave de OpenAI:
        
        ```python
        OPENAI_API_KEY=tu_clave_de_openai
        ```
        

## **Estructura del Proyecto**

El proyecto tiene la siguiente estructura de archivos:

```
LangChain-LLM-AREP/
├── README.md
├── src/
│   └── LangChain.ipynb
```

- **`README.md`**: Este archivo, con la documentación del proyecto.
- **`LangChain.ipynb`**: Código principal del proyecto.

---

## **Configuración**

1. **Clona este repositorio** (si no estás usando Google Colab):
    
    ```bash
    git clone https://github.com/juliandtrianar/AREP_TALLER_LLM/tree/d5b434cb305eb877bd507d777eedee756df2f7a8/TutorialLLM_chain
    ```
    
2. **Instala las dependencias**:
    - Si estás usando Google Colab, ejecuta:
        
        ```bash
        !pip install langchain openai
        ```
        
3. **Configura tu clave de OpenAI**:
    - En Google Colab, ejecuta:
        
        ```python
        import getpass
        import os
        
        os.environ["OPENAI_API_KEY"] = getpass.getpass("Enter API key for OpenAI: ")
        ```
        

---

## **Uso**

1. **Abre el notebook**:
    - Si estás en Google Colab, sube el archivo `LangChain.ipynb` o copia y pega el código en un nuevo notebook.
2. **Ejecuta el código**:
    - Sigue las celdas del notebook para:
        - Inicializar el modelo de lenguaje.
        - Crear una plantilla de prompt.
        - Traducir texto de inglés a otro idioma.
3. **Ejemplo de código**:
    
    ```python
    from langchain.chat_models import init_chat_model
    from langchain_core.messages import HumanMessage, SystemMessage
    from langchain_core.prompts import ChatPromptTemplate
    
    # Inicializa el modelo
    model = init_chat_model("gpt-4", model_provider="openai")
    
    # Crea una plantilla de prompt
    system_template = "Translate the following from English into {language}"
    prompt_template = ChatPromptTemplate.from_messages(
        [("system", system_template), ("user", "{text}")]
    )
    
    # Traduce un texto
    prompt = prompt_template.invoke({"language": "Italian", "text": "good morning"})
    response = model.invoke(prompt)
    print(response.content)  # Output: "Buongiorno!"
    ```
    

---

## **Ejemplos**

- **Traducción a Italiano**:
    
    ```python
    prompt = prompt_template.invoke({"language": "Italian", "text": "good morning"})
    response = model.invoke(prompt)
    print(response.content)  # Output: "Buongiorno!"
    ```
    
- **Traducción a Francés**:
    
    ```python
    prompt = prompt_template.invoke({"language": "French", "text": "good night"})
    response = model.invoke(prompt)
    print(response.content)  # Output: "Bonne nuit!"
    ```
    

---

## **Ejemplos de Uso**

1. **Traducir texto a italiano**:
    - Entrada: `"hi!"`
    - Salida: `"Ciao!"`
2. **Traducir texto a francés**:
    - Entrada: `"good morning"`
    - Salida: `"Bonjour!"`

---

## **Capturas de Pantalla**

Aquí hay un ejemplo de la salida en la consola:

<img width="597" height="232" alt="image" src="https://github.com/user-attachments/assets/005e4dfd-9297-4255-b467-e7a2b830663e" />

<img width="661" height="110" alt="image" src="https://github.com/user-attachments/assets/d24c03db-3ed8-4450-b0fe-34344cf53e97" />


---
### **Autor**

- Julián David Triana Roa
