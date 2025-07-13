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