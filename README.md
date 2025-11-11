# LangChain LLM Project

## 📋 Descripción del Proyecto

Este proyecto implementa una aplicación basada en **LangChain** que integra modelos de lenguaje de OpenAI con herramientas de rastreo y monitoreo a través de LangSmith.

---

## 🏗️ Arquitectura y Componentes

### Componentes Principales

1. **OpenAI Integration**
   - Integración con modelos GPT de OpenAI
   - Gestión de claves API de forma segura

2. **LangChain Framework**
   - Orquestación de flujos con modelos de lenguaje
   - Cadenas y agentes para procesamiento de información
   - Manejo de prompts y memoria

3. **LangSmith Monitoring**
   - Rastreo y monitoreo de ejecuciones
   - Análisis de rendimiento de cadenas
   - Debugging y evaluación de resultados

4. **Environment Management**
   - Carga de variables de entorno desde archivo `.env`
   - Gestión segura de claves API

### Flujo de Trabajo

```
┌─────────────────────────────────────────────────┐
│         Entrada de Usuario / Prompt             │
└────────────────────┬────────────────────────────┘
                     │
                     ▼
         ┌───────────────────────────┐
         │    LangChain Chain/Agent  │
         │  (Procesa la solicitud)   │
         └────────────┬──────────────┘
                      │
        ┌─────────────┴─────────────┐
        │                           │
        ▼                           ▼
   ┌─────────────┐          ┌─────────────┐
   │   OpenAI    │          │ LangSmith   │
   │   Models    │          │  Tracing    │
   └─────────────┘          └─────────────┘
        │                           │
        └─────────────┬─────────────┘
                      │
                      ▼
         ┌───────────────────────────┐
         │      Resultado Final      │
         └───────────────────────────┘
```

---

## 🚀 Instalación y Configuración

### Requisitos Previos

- **Python 3.11.0** o superior
- **pip** actualizado
- **Windows PowerShell** (o Command Prompt)
- Conexión a internet

### Paso 1: Clonar o Descargar el Proyecto

```powershell
cd C:\LangChain LLM
```

### Paso 2: Crear Entorno Virtual

```powershell
python -m venv venv
```

### Paso 3: Activar Entorno Virtual

**En PowerShell:**
```powershell
.\venv\Scripts\Activate.ps1
```

**En Command Prompt (CMD):**
```cmd
.\venv\Scripts\activate.bat
```

**Si obtienes error de ejecución de scripts:**
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Paso 4: Instalar Dependencias

Ejecuta las siguientes celdas en el notebook `LangChain.ipynb`:

**Celda 1: Dependencias básicas**
```python
!pip install openai python-dotenv
```

**Celda 2: LangChain**
```python
!pip install langchain
```

**Celda 3: LangChain con OpenAI**
```python
!pip install -qU "langchain[openai]"
```

---

## ⚙️ Configuración de Variables de Entorno

### Opción 1: Archivo `.env` (Recomendado)

Crea un archivo `.env` en la raíz del proyecto:

```
OPENAI_API_KEY=sk-proj-xxxxxxxxxxxxxxxxxxxxx
LANGSMITH_API_KEY=sk-proj-xxxxxxxxxxxxxxxxxxxxx
LANGSMITH_PROJECT=Tu_Proyecto_LangSmith
LANGSMITH_TRACING=true
```

### Opción 2: Configuración Manual en el Notebook

El notebook configurará automáticamente:
- Rastreo de LangSmith (`LANGSMITH_TRACING`)
- Clave API de LangSmith
- Nombre del proyecto (te pedirá input)

---

## 📝 Estructura del Proyecto

```
C:\LangChain LLM\
├── LangChain.ipynb              # Notebook principal
├── .env                         # Variables de entorno (crear)
├── venv/                        # Entorno virtual
├── README.md                    # Este archivo
└── (otros archivos del proyecto)
```

---

## ▶️ Ejecución del Proyecto

### En VS Code (Jupyter Notebook)

1. Abre `LangChain.ipynb`
2. Asegúrate de seleccionar el kernel `venv` (esquina superior derecha)
3. Ejecuta las celdas en orden:
   - **Celda 1-4**: Instalación de dependencias y configuración
   - **Celdas siguientes**: Tu código específico

### En Terminal

```powershell
# Con el entorno virtual activado
jupyter notebook
```

---

## 🔑 Gestión de Claves API

### OpenAI API Key
1. Ve a [platform.openai.com](https://platform.openai.com)
2. Inicia sesión o crea una cuenta
3. Ve a "API keys" y copia tu clave
4. Guárdala en `.env` como `OPENAI_API_KEY`

### LangSmith API Key
1. Ve a [smith.langchain.com](https://smith.langchain.com)
2. Inicia sesión con tu cuenta
3. Ve a "Settings" → "API Keys"
4. Copia tu clave y guárdala en `.env` como `LANGSMITH_API_KEY`

---

## 🛠️ Solución de Problemas

### Error: "No se puede cargar el archivo Activate.ps1"
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Error: "No hay instalador de Pip disponible"
- Usa un entorno virtual limpio
- Verifica que Python esté correctamente instalado
- Intenta: `python -m pip install --upgrade pip`

### Error: "Módulo no encontrado"
```powershell
pip install openai python-dotenv langchain
```

### Las claves API no se cargan
- Verifica que el archivo `.env` esté en la raíz del proyecto
- Asegúrate de que `load_dotenv()` se ejecute antes de usar las variables

---

## 📚 Recursos Adicionales

- [Documentación de LangChain](https://python.langchain.com/)
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference)
- [LangSmith Docs](https://docs.smith.langchain.com/)
- [Python Dotenv](https://github.com/theskumar/python-dotenv)

---

## 📄 Licencia

Este proyecto utiliza APIs de terceros (OpenAI, LangSmith). Asegúrate de cumplir con sus términos de servicio.

---

**Última actualización:** 10 de noviembre de 2025
