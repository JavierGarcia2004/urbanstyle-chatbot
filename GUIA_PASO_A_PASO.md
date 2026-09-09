# GUÍA PASO A PASO - Chatbot UrbanStyle

## ============================================
## PASO 1: OBTENER API KEY DE OPENAI
## ============================================

### 1.1 Crear cuenta en OpenAI

1. Ve a: https://platform.openai.com
2. Haz clic en "Sign Up"
3. Puedes registrarte con:
   - Email y contraseña
   - Google
   - Microsoft
4. Completa el registro (te pedirá número de teléfono)
5. Verifica tu email

### 1.2 Obtener la API Key

1. Una vez dentro, ve a: https://platform.openai.com/api-keys
2. Haz clic en "Create new secret key"
3. Ponle un nombre (ej: "chatbot-urbanstyle")
4. Haz clic en "Create secret key"
5. **COPIA LA CLAVE INMEDIATAMENTE** (empieza con sk-...)
6. **GUÁRDALA EN UN LUGAR SEGURO** (solo se muestra una vez)

### 1.3 Importante sobre costos

- OpenAI te da $5 USD de crédito gratis al crear la cuenta
- Cuesta aproximadamente $0.002 por consulta al chatbot
- Con $5 puedes hacer ~2,500 consultas
- No necesitas agregar tarjeta de crédito para empezar

---

## ============================================
## PASO 2: ABRIR TERMINAL
## ============================================

### Windows:
1. Presiona las teclas Windows + R
2. Escribe "cmd" y presiona Enter
3. Se abre la ventana de comandos

### Mac:
1. Presiona Command + Espacio
2. Escribe "Terminal"
3. Presiona Enter

---

## ============================================
## PASO 3: CREAR EL PROYECTO
## ============================================

### 3.1 Navegar al escritorio

**Windows:**
```
cd %USERPROFILE%\Desktop
```

**Mac:**
```
cd ~/Desktop
```

### 3.2 Crear la carpeta del proyecto

**Windows:**
```
mkdir urbanstyle-chatbot
cd urbanstyle-chatbot
```

**Mac:**
```
mkdir urbanstyle-chatbot
cd urbanstyle-chatbot
```

### 3.3 Verificar que estás en la carpeta correcta

**Windows:**
```
cd
```

**Mac:**
```
pwd
```

Debe mostrar algo como: `C:\Users\TU_USUARIO\Desktop\urbanstyle-chatbot`

---

## ============================================
## PASO 4: CREAR ENTORNO VIRTUAL
## ============================================

### 4.1 Crear el entorno virtual

**Windows:**
```
python -m venv venv
```

**Mac:**
```
python3 -m venv venv
```

Si da error "python no reconocido", prueba:
```
py -m venv venv
```

### 4.2 Activar el entorno virtual

**Windows:**
```
venv\Scripts\activate
```

**Mac:**
```
source venv/bin/activate
```

Si funciona, verás `(venv)` al inicio de la línea de comandos.

### 4.3 Verificar que está activo

```
python --version
```

Debe mostrar algo como: `Python 3.10.x` o superior.

---

## ============================================
## PASO 5: INSTALAR DEPENDENCIAS
## ============================================

### 5.1 Crear el archivo requirements.txt

Escribe esto exactamente en la terminal (copia y pega):

**Windows:**
```
echo langchain==0.3.7 > requirements.txt
echo langchain-openai==0.2.9 >> requirements.txt
echo langchain-community==0.3.7 >> requirements.txt
echo chromadb==0.5.23 >> requirements.txt
echo pypdf==5.1.0 >> requirements.txt
echo python-dotenv==1.0.1 >> requirements.txt
echo tiktoken==0.8.0 >> requirements.txt
```

**Mac:**
```
echo "langchain==0.3.7" > requirements.txt
echo "langchain-openai==0.2.9" >> requirements.txt
echo "langchain-community==0.3.7" >> requirements.txt
echo "chromadb==0.5.23" >> requirements.txt
echo "pypdf==5.1.0" >> requirements.txt
echo "python-dotenv==1.0.1" >> requirements.txt
echo "tiktoken==0.8.0" >> requirements.txt
```

### 5.2 Instalar las dependencias

**Windows:**
```
pip install -r requirements.txt
```

**Mac:**
```
pip3 install -r requirements.txt
```

Esto tardará 2-5 minutos. No cierres la ventana.

---

## ============================================
## PASO 6: CONFIGURAR API KEY
## ============================================

### 6.1 Crear el archivo .env

**Windows:**
```
echo OPENAI_API_KEY=tu-api-key-aqui > .env
```

**Mac:**
```
echo "OPENAI_API_KEY=tu-api-key-aqui" > .env
```

### 6.2 Editar el archivo .env

Reemplaza "tu-api-key-aqui" con tu API key real.

**Usando Notepad (Windows):**
```
notepad .env
```

**Usando nano (Mac):**
```
nano .env
```

Guarda el archivo:
- Notepad: Ctrl+S y cierra
- nano: Ctrl+X, presiona Y, Enter

---

## ============================================
## PASO 7: CREAR ESTRUCTURA DE CARPETAS
## ============================================

**Windows:**
```
mkdir data
mkdir src
mkdir tests
mkdir docs
```

**Mac:**
```
mkdir data src tests docs
```

---

## ============================================
## PASO 8: VERIFICAR QUE TODO FUNCIONA
## ============================================

### 8.1 Verificar archivos

**Windows:**
```
dir
```

**Mac:**
```
ls -la
```

Debes ver:
- .env
- requirements.txt
- carpetas: data, src, tests, docs

### 8.2 Verificar entorno virtual

```
python -c "import langchain; print('LangChain OK')"
```

Si no da error, todo está instalado correctamente.

---

## ============================================
## PASO 9: EJECUTAR EL CHATBOT
## ============================================

Una vez que tengas todos los archivos del proyecto creados:

**Windows:**
```
python -m src.chatbot
```

**Mac:**
```
python3 -m src.chatbot
```

Deberías ver:
```
============================================================
  URBANSTYLE CHILE - Chatbot de Atención al Cliente
  Escribe 'salir' para terminar la conversación
============================================================
Inicializando pipeline RAG...
```

Prueba escribir:
- "¿Cuánto cuesta la remera básica?"
- "¿Cuáles son los horarios?"
- "¿Puedo devolver un producto?"

Para salir escribe: "salir"

---

## ============================================
## SOLUCIÓN DE ERRORES COMUNES
## ============================================

### Error: "python no se reconoce"
**Solución:** Instala Python desde https://www.python.org/downloads/
- Marca la casilla "Add Python to PATH" durante la instalación

### Error: "pip no se reconoce"
**Solución:** Reinicia la terminal después de instalar Python

### Error: "No such file or directory"
**Solución:** Verifica que estás en la carpeta correcta con `cd` o `pwd`

### Error: "OPENAI_API_KEY not set"
**Solución:** Verifica que el archivo .env existe y tiene tu API key

### Error: "ModuleNotFoundError"
**Solución:** Asegúrate de tener el entorno virtual activado (venv)
