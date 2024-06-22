# Local RAG

## Requisitos Previos

- Sistema operativo compatible con Docker (Linux, macOS, Windows).
- Docker instalado en tu máquina. Puedes seguir la guía oficial de instalación de Docker [aquí](https://docs.docker.com/get-docker/).
- Python 3.x instalado.

## Instrucciones de Instalación

### 1. Instalar Docker

Si aún no tienes Docker instalado, sigue los pasos para instalarlo desde el [sitio oficial de Docker](https://docs.docker.com/get-docker/).

### 2. Ejecutar Ollama en un Contenedor Docker

Una vez que Docker esté instalado y ejecutándose, sigue estos pasos:

1. **Crear y ejecutar un contenedor Docker para Ollama:**
   ```bash
   docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
   ```
2. **Descargar el modelo mxbai-embed-large:**
   ```bash
   ollama pull mxbai-embed-large
   ```
3. **(Opcional) Descargar otro modelo, por ejemplo, mistral:**
   ```bash
   ollama pull mistral
   ```
3. **Configurar el Entorno de Python**
   1. Crear un entorno virtual:
   ```bash
   python -m venv myenv
   source myenv/bin/activate   # En Windows usa `myenv\Scripts\activate`
   ```
   2. Instalar las dependencias desde requirements.txt:

   ```bash
   pip install -r requirements.txt
   ```
   3. O bien, instalar manualmente las librerías necesarias:

   ```bash
   pip install ollama chromadb
   ```
4. **Ejecutar el Script main.py**

Con el entorno configurado y las dependencias instaladas, ejecuta el script principal:

```bash
python main.py
```