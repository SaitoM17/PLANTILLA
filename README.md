
# Guía para la Estructura y Configuración de Proyectos de Análisis de Datos

Esta guía proporciona una estructura organizada para proyectos de análisis de datos, junto con buenas prácticas para la gestión de dependencias y el versionado con Git.


## 1. Organización de Carpetas en un Proyecto de Análisis de Datos

Es importante mantener una estructura organizada en tus proyectos. Se recomienda la siguiente jerarquía:

```
📂 MiProyectoAnalisisDatos/
│── 📂 data/           
│   ├── 📂 raw/         # Datos originales sin modificar
│   └── 📂 processed/   # Datos limpios/listos para análisis
│
│── 📂 notebooks/       # Contiene los Jupyter Notebooks para explorar los datos
│── 📂 scripts/         # Guarda scripts de Python para limpieza, modelos, etc.
│── 📂 reports/         # Contiene gráficos y reportes generados
│── 📂 models/          # Si usas machine learning, guarda los modelos aquí
│── 📂 docs/            # Documentación del proyecto
│── requirements.txt    # Lista de paquetes necesarios (para instalar en otro PC)
│── README.md           # Explicación del proyecto
│── LICENSE
```
## Ejemplo de Creación de Carpetas con Python

Para automatizar la creación de esta estructura, usa el siguiente script en Python:

```Python
import os

# Define la estructura de carpetas
folders = ["data", "notebooks", "scripts", "reports", "models", "docs"]

# Crea las carpetas si no existen
for folder in folders:
    os.makedirs(folder, exist_ok=True)

print("Estructura de carpetas creada con éxito.")
```


## 2. Uso de un Entorno Virtual para Aislar Dependencias

Para evitar conflictos con versiones de librerías, se recomienda usar entornos virtuales.

###  Crear y Activar un Entorno Virtual

#### Crear el entorno virtual:
```
python -m venv venv
```
#### Activar el entorno:
* #### En Windows:

    ```
    venv\Scripts\activate
    ```

* #### En Mac/Linux::

    ```
    source venv/bin/activate
    ```

#### Instalar dependencias dentro del entorno:
```
pip install numpy pandas matplotlib seaborn scikit-learn
```
#### Para guardar las librerías instaladas en un archivo requirements.txt:
```
pip freeze > requirements.txt
```
#### Para reinstalar las dependencias en otro equipo:
```
pip install -r requirements.txt
```


## 3. Versionado del Proyecto con Git

Para mantener un historial de cambios y colaborar con otros, usa Git y GitHub.

### Configurar Git en tu Proyecto

#### Inicializar Git:
```
git init
```
#### Crear un archivo .gitignore para excluir archivos innecesarios:
```
echo "venv/" >> .gitignore
echo "__pycache__/" >> .gitignore
echo "*.csv" >> .gitignore
```
#### Subir el proyecto a GitHub:
```
git add .
git commit -m "Primer commit"
git branch -M main
git remote add origin https://github.com/usuario/repositorio.git
git push -u origin main
```

(Borrar este archivo y renombrar el archivo plantilla_README.md a README.md)