# iaproyecto

Proyecto de práctica sobre **embeddings con Ollama**: generación de embeddings de texto, analogías semánticas, visualización con t-SNE y búsqueda semántica, desarrollados en un notebook de Jupyter.

## Contenido

```
iaproyecto/
├── Ollama Embeddings/
│   ├── embeddings_ollama_clase.ipynb   # Notebook principal
│   └── requirements.txt                # Dependencias
├── .gitignore
└── README.md
```

## Requisitos

- **Python 3.9 o superior** (probado con Python 3.13)
- **Git**
- **[Ollama](https://ollama.com)** instalado y en ejecución
- Un modelo de embeddings descargado en Ollama (revisa en el notebook cuál se usa; por ejemplo):

```powershell
ollama pull nomic-embed-text
```

Para comprobar que Ollama responde:

```powershell
ollama list
```

## Instalación

### 1. Clonar el repositorio

```powershell
git clone https://github.com/rosalbat/iaproyecto.git
cd iaproyecto
```

### 2. Crear y activar el entorno virtual

Windows (PowerShell):

```powershell
python -m venv venv
.\venv\Scripts\activate
```

Si PowerShell bloquea la activación, ejecuta una sola vez:

```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

macOS / Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Instalar dependencias

```powershell
pip install -r "Ollama Embeddings/requirements.txt"
pip install ipykernel jupyter
```

El `requirements.txt` incluye `requests`, `numpy`, `matplotlib` y `scikit-learn`. Jupyter e ipykernel se instalan aparte para ejecutar el notebook.

## Uso

1. Asegúrate de que **Ollama esté abierto** (escucha en `localhost:11434`).
2. Abre `Ollama Embeddings/embeddings_ollama_clase.ipynb` en VS Code.
3. En la esquina superior derecha elige **Select Kernel → Python Environments** y selecciona el intérprete de `venv`.
4. Ejecuta las celdas en orden con `Shift+Enter`, o usa **Run All**.

## Solución de problemas

| Problema | Posible solución |
|---|---|
| `source` no se reconoce en Windows | Usa `.\venv\Scripts\activate` en lugar de `source venv/bin/activate`. |
| Error de conexión a `localhost:11434` | Ollama no está en ejecución; ábrelo y vuelve a correr la celda. |
| El kernel `venv` no aparece | Ejecuta **Developer: Reload Window** en VS Code y reintenta. |
| Modelo no encontrado | Descarga el modelo con `ollama pull <nombre-del-modelo>`. |

## Flujo de trabajo con Git

```powershell
git add .
git commit -m "Describe qué cambiaste"
git push
```

## Notas

- La carpeta `venv/` no se sube al repositorio (está en `.gitignore`); se recrea con los pasos de instalación.
- Guarda claves o tokens en un archivo `.env`, que también está ignorado por Git.
