# Guía para la Estructura y Configuración de Proyectos de Análisis de Datos

Esta guía proporciona una estructura organizada para proyectos de análisis de datos, junto con buenas prácticas para la gestión de dependencias y el versionado con Git.


## Organización de Carpetas en un Proyecto de Análisis de Datos

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
│── README.md           # Guía para la Estructura y Configuración de Proyectos de Análisis de Datos
│── LICENSE             # LICENSE del proyecto
|── plantilla_README.md # Plantilla para proyectos Explicación del proyecto
```

## Clonar Plantilla (Repositorio)
**1. Clona el repositorio de la plantilla:** Clona tu repositorio de plantilla y renombra la carpeta del proyecto con el nombre adecuado para tu nuevo proyecto.
```            
git clone https://github.com/SaitoM17/PLANTILLA.git nombre_de_tu_proyecto
```
   * ##### **Moverse a la carpeta del proyecto:**
      ```
      cd nombre_de_tu_proyecto
      ```
**2. Renombra los archivos según sea necesario:** Si es necesario, cambia el nombre de los archivos como plantilla_README.md a README.md.
```
mv plantilla_README.md README.md
```

**3. Elimina el historial de Git:** Para comenzar con un repositorio limpio, elimina el historial de Git del repositorio clonado (esto borrará los archivos de configuración de Git previos).
```
rm -rf .git
```

**4. Crea el entorno virtual:** Crea un entorno virtual para aislar las dependencias de tu proyecto y evitar conflictos con otras librerías.
```
python -m venv venv
```
#### Activar el entorno:
* ##### **En Windows:**

    ```
    venv\Scripts\activate
    ```

* ##### **En Mac/Linux:**

    ```
    source venv/bin/activate
    ```

**5. Instala las dependencias:** Si tu proyecto tiene un archivo requirements.txt con las dependencias necesarias, instálalas:
```
pip install -r requirements.txt
```
   * Si no tienes el archivo requirements.txt, instala las dependencias que necesites manualmente. Por ejemplo: 
      ```
      pip install numpy pandas matplotlib seaborn
      ```
**6. Inicializa Git:** Inicializa un nuevo repositorio Git en tu proyecto.
```
git init
```

**7. Configura .gitignore:** Crea o edita el archivo .gitignore para evitar que el entorno virtual o archivos innecesarios se suban al repositorio. Asegúrate de incluir venv/ y cualquier otro archivo que no quieras rastrear con Git (como archivos de configuración, logs, etc.).

   * **Ejemplo de .gitignore:**
      ```
      venv/
      __pycache__/
      *.csv
      *.log
      ```
**8. Haz tu primer commit:** Agrega todos los archivos al repositorio y haz tu primer commit.
```
git add .
git commit -m "Primer commit: Configuración inicial del proyecto"
```
**9. Sube tu proyecto a GitHub:** Si tienes un repositorio en GitHub, conecta tu proyecto local al repositorio remoto y empuja los cambios.
```
git remote add origin https://github.com/TU_USUARIO/nuevo_repositorio.git
git push -u origin main

```
(Borrar este archivo y renombrar el archivo plantilla_README.md a README.md)