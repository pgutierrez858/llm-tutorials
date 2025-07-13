# 📘 Proyecto con Jupyter y Poetry

Este proyecto usa [Poetry](https://python-poetry.org/) para la gestión del entorno virtual y dependencias, y está preparado para trabajar con **Jupyter Notebook** de forma aislada y reproducible.

---

## ⚙️ Requisitos

Antes de comenzar, asegúrate de tener instalado:

- Python 3.12 o superior
- [Poetry](https://python-poetry.org/docs/#installation)

---

## 🚀 Instalación del entorno

1. Clona el repositorio:

```bash
git clone https://github.com/pgutierrez858/llm-tutorials
cd mi_proyecto
```

2. Instala las dependencias (usamos `--no-root` porque no estamos trabajando con un paquete, sino con notebooks y dependencias únicamente):

```bash
poetry install --no-root
```

---

Para poder usar este entorno en Jupyter, debes registrarlo como un kernel:

```bash
poetry run python -m ipykernel install --user --name=llms_tutorial --display-name "Python (llms_tutorial)"
```

+ --name: nombre interno del kernel

+ --display-name: cómo aparecerá en la lista de kernels de Jupyter

y para poder ver los widgets de Guidance, debes habilitarlos con:

```bash
jupyter labextension enable widgetsnbextension
```

---

Una vez instalado todo, puedes abrir Jupyter con:
```bash
poetry run jupyter notebook
# o bien
poetry run jupyter lab
```

Desde la interfaz de Jupyter, selecciona el kernel llamado "Python (llms_tutorial)" para trabajar con el entorno correcto.


---

## 📂 Antes de abrir el notebook

Antes de empezar con la introducción a las funcionalidades básicas de Guidance con el notebook de inicio, vamos a preparar las distintas piezas necesarias para lanzarlo de forma local.

Lo primero va a ser hacernos con el modelo de lenguaje que queramos utilizar. [Hugging Face](https://huggingface.co/models?other=LLM) está lleno de LLMs de muchísimos tipos, pero en la práctica lo más probable es que sólo podamos usar unos pocos de ellos en nuestro PC por distintos motivos y restricciones (tamaño del modelo, requisitos de RAM, licencias, compatibilidad con las librerías desde las que queramos llamarlo, etc). En el caso de Guidance, los modelos con mejor soporte con la librería sin tener que hacer adaptaciones complicadas son los de la línea Phi de Microsoft y los Llama, si bien es posible utilizar muchos otros (incluyendo modelos basados en APIs como los de OpenAI), con capacidades limitadas… o con un setup menos amigable.

Se recomienda usar el modelo cuantizado que puede descargarse en [Meta-Llama-3-8B-Instruct.Q4_0.gguf](https://huggingface.co/QuantFactory/Meta-Llama-3-8B-Instruct-GGUF/blob/main/Meta-Llama-3-8B-Instruct.Q4_0.gguf), basado en Llama 3 8B Instruct, y colocarlo en la raíz del proyecto (o donde se prefiera, recordando cambiar la ruta asociada al referenciarlo en el notebook). Un modelo cuantizado es una versión optimizada que reduce el tamaño y el consumo de memoria al representar los pesos del modelo con menos bits, lo que facilita su ejecución en equipos con recursos limitados sin perder demasiada precisión.

En el notebook de ejemplo se ofrecen otras alternativas para equipos con diferentes capacidades, desde más potentes hasta más modestos, pero este modelo debería ser una buena opción para equipos de gama media.
