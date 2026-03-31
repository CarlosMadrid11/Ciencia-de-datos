# Proyecto Módulo 2 — Análisis Exploratorio de Datos con archivo TXT
## Descripción
Este proyecto forma parte del Módulo 2 de la materia de Ciencia de Datos. El objetivo es demostrar el proceso completo de carga, limpieza y análisis exploratorio de un archivo de texto plano (`.txt`) con datos climatológicos reales de la estación **Acatitán, Sinaloa (Clave 25001)**, proporcionada por la CONAGUA.

El dataset contiene registros diarios de precipitación, evaporación y temperaturas máxima y mínima desde **enero de 1961** hasta **julio de 2018**.

-----
## Estructura del proyecto
```
📁 Modulo 2 - Analitica de datos/
├── 📄 README.md
├── 📄 ProyectoModulo2.ipynb             ← Notebook principal
├── 📄 Procesamiento de Archivo TXT.pdf  ← Reporte del proyecto
└── 📁 Datasets/
    └── 📄 25001.txt                     ← Archivo fuente de CONAGUA
```
-----
## Fuente de datos
|Campo             |Detalle                |
|------------------|-----------------------|
|Organismo         |CONAGUA-DGE            |
|Estación          |25001 — Acatitán       |
|Estado            |Sinaloa                |
|Municipio         |San Ignacio            |
|Latitud           |24.097° N              |
|Longitud          |106.667° O             |
|Altitud           |96 msnm                |
|Período           |01/01/1961 — 31/07/2018|
|Total de registros|19,574 filas           |

-----
## Variables del dataset
|Columna |Descripción       |Unidad               |
|--------|------------------|---------------------|
|`FECHA` |Fecha del registro|datetime (dd/mm/yyyy)|
|`PRECIP`|Precipitación     |mm                   |
|`EVAP`  |Evaporación       |mm                   |
|`TMAX`  |Temperatura máxima|°C                   |
|`TMIN`  |Temperatura mínima|°C                   |

-----
## Etapas del proyecto
### Etapa 1 — Carga del archivo
El archivo presentaba las siguientes características que requirieron configuración especial:
- Encoding `ISO-8859-1` (no UTF-8)
- Separador de espacio múltiple (`\s+`)
- 18 líneas de encabezado informativo antes de los datos
- Valor `"Nulo"` como indicador de dato faltante

```python
df = pd.read_csv("25001.txt", encoding='ISO-8859-1',
                 sep="\s+", na_values="Nulo", skiprows=18)
```

### Etapa 2 — Corrección de estructura
- Renombrado de columnas (venían con nombres de unidades en lugar de nombres semánticos)
- Eliminación de la última fila con caracteres de separación (`------`)
- Conversión de la columna `FECHA` de tipo `str` a `datetime64`

### Etapa 3 — Diagnóstico de calidad
Resultados del análisis inicial con `.describe()`, `.isnull().sum()` y `.duplicated().sum()`:

|Columna   |Nulos encontrados|
|----------|-----------------|
|PRECIP    |40               |
|EVAP      |272              |
|TMAX      |5                |
|TMIN      |6                |
|Duplicados|0                |

### Etapa 4 — Limpieza de datos
- Creación de columna `faltantes` para identificar fechas con registros incompletos
- Relleno de valores nulos con la **media de cada columna**
- Verificación final: todas las columnas quedaron con `0` valores nulos

### Etapa 5 — Verificación final
Tras la limpieza, el dataset quedó con **19,574 registros completos** sin valores faltantes ni duplicados.

-----
## Requisitos
```
Python 3.x
pandas
numpy
jupyter
```
Instalación:
```bash
pip install pandas numpy jupyter
```

-----
## Cómo ejecutar el proyecto
1. Clona o descarga este repositorio
1. Coloca el archivo `25001.txt` en la carpeta `Datasets/`
1. Abre Jupyter Notebook:
```bash
jupyter notebook
```
1. Abre `ProyectoModulo2.ipynb` y ejecuta las celdas en orden con `Shift + Enter`

-----
## Autores
Proyecto desarrollado como parte del Módulo 2 — Pandas  
Materia: Ciencia de Datos  
Institución: Instituto Tecnológico de Culiacán

- Denzel Arturo Gutiérrez Chávez
- Juan Carlos Quiñonez Madrid