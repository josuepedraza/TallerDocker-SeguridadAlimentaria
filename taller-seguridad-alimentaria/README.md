# Análisis de Seguridad Alimentaria en Colombia (WFP + DANE ECV 2024)

**Autor:** Josue Pedraza    
**Herramientas:** Python, Docker, PySpark, Pandas, Jupyter Notebook  

---

# Descripción del proyecto

Este proyecto tiene como objetivo analizar la **inseguridad alimentaria en Colombia** utilizando dos fuentes de información diferentes. La primera fuente es un informe del **Programa Mundial de Alimentos (WFP)** que contiene datos de inseguridad alimentaria por departamento. La segunda fuente corresponde a los **microdatos de la Encuesta de Calidad de Vida (ECV) 2024 del DANE**, los cuales contienen información socioeconómica de los hogares colombianos.

Para realizar el análisis se utilizaron técnicas de **extracción de datos desde PDF**, limpieza de datos y análisis exploratorio. Posteriormente se combinaron los datos del WFP con indicadores socioeconómicos derivados de los microdatos del DANE para analizar la relación entre inseguridad alimentaria y variables como pobreza, acceso a acueducto, hacinamiento y nivel educativo.

El proyecto se ejecuta dentro de un **entorno reproducible utilizando Docker**, lo que permite instalar automáticamente todas las dependencias necesarias y ejecutar el análisis en Jupyter Notebook.

---

# Instrucciones para ejecutar con Docker

## 1. Clonar el repositorio

```bash
git clone https://github.com/josuepedraza/TallerDocker-SeguridadAlimentaria.git
cd TallerDocker-SeguridadAlimentaria
```

## 2. Descargar los datos

Descargar los datos y colocarlos en las carpetas correspondientes.

### PDF del WFP

https://docs.wfp.org/api/documents/WFP-0000158611/download/

Guardar el archivo como:

```
WFP_Colombia_2024.pdf
```

### Microdatos DANE – Encuesta de Calidad de Vida 2024

https://microdatos.dane.gov.co/index.php/catalog/861/get-microdata

Descargar los archivos CSV y colocarlos dentro de:

```
datos/datos_dane/
```

## 3. Construir y ejecutar el contenedor

```bash
docker-compose up --build
```

## 4. Abrir Jupyter Notebook

Abrir el navegador en:

```
http://localhost:8888
```

Luego ejecutar el notebook:

```
notebooks/analisis_completo.ipynb
```

---

# Estructura de carpetas

```
taller-seguridad-alimentaria
│
├── datos
│   └── datos_dane
│
├── notebooks
│   └── analisis_completo.ipynb
│
├── resultados
│   ├── datos_combinados_wfp_dane.csv
│   ├── grafico_inseguridad_departamentos.png
│   └── grafico_correlaciones.png
│
├── WFP_Colombia_2024.pdf
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
└── README.md
```

---

# Fuentes de datos

## Programa Mundial de Alimentos (WFP)

Informe sobre inseguridad alimentaria en Colombia.

https://docs.wfp.org/api/documents/WFP-0000158611/download/

## DANE – Encuesta de Calidad de Vida 2024

Microdatos oficiales del DANE.

https://microdatos.dane.gov.co/index.php/catalog/861/get-microdata

---

# Principales hallazgos

- El promedio de **inseguridad alimentaria en Colombia es cercano al 30%** según el informe del WFP.
- Los departamentos con mayor nivel de inseguridad alimentaria incluyen **La Guajira, Chocó y Córdoba**.
- Existe una relación positiva entre pobreza monetaria e inseguridad alimentaria.
- Variables como Falta de acceso a acueducto, hacinamiento y bajo nivel educativo también presentan relación con mayores niveles de inseguridad alimentaria.
- Los departamentos con condiciones socioeconómicas más vulnerables tienden a presentar **mayor riesgo de inseguridad alimentaria**.

---

# Resultados generados

El análisis genera automáticamente los siguientes archivos:

- `datos_combinados_wfp_dane.csv`
- `grafico_inseguridad_departamentos.png`
- `grafico_correlaciones.png`

Estos resultados se almacenan en la carpeta:

```
resultados/
```

---

# Conclusión

El análisis muestra que la inseguridad alimentaria en Colombia está asociada con diferentes factores socioeconómicos. Los resultados sugieren que departamentos con mayores niveles de pobreza y menores condiciones de infraestructura presentan mayores niveles de inseguridad alimentaria.

Este tipo de análisis permite identificar territorios prioritarios para la implementación de políticas públicas orientadas a mejorar la seguridad alimentaria y las condiciones de vida de la población