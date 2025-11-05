# CBIS-DDSM Dataset - Descarga y Organización

Este proyecto permite descargar y organizar el dataset **CBIS-DDSM** (Curated Breast Imaging Subset of DDSM), un conjunto de imágenes de mamografías etiquetadas, que se utiliza para la investigación en la detección de cáncer de mama. Este repositorio incluye un script para descargar, explorar y organizar el dataset en una estructura específica de carpetas, y algunas herramientas básicas para la visualización de las imágenes y las anotaciones.

# CBIS-DDSM Dataset

El **CBIS-DDSM** (Curated Breast Imaging Subset of Digital Database for Screening Mammography) es un conjunto de datos curado y actualizado para tareas de **detección de objetos**, **segmentación de instancias** y **segmentación semántica** en imágenes de mamografía. Este dataset es ampliamente utilizado en investigaciones de sistemas de apoyo a la decisión (CAD) para la detección temprana de cáncer de mama.

## Información General

- **Fecha de lanzamiento**: 14 de septiembre de 2017
- **Autores**: Rebecca Sawyer Lee, Francisco Gimenez, Assaf Hoogi, et al.
- **Institución**: Stanford University

El CBIS-DDSM incluye:
- Imágenes descomprimidas de mamografías con selección y curación realizada por mamógrafos capacitados.
- Segmentación actualizada de masas y cuadros delimitadores (bounding boxes) para calcificaciones y masas.
- Diagnósticos patológicos en los datos de entrenamiento, con un formato similar a los datasets modernos de visión por computadora.

### Propósito del Dataset

Este dataset fue creado para estandarizar la evaluación de algoritmos de CAD en mamografía. Anteriormente, los algoritmos de diagnóstico asistido por computadora (CADx) y detección asistida (CADe) se evaluaban en datasets privados o subconjuntos no especificados, lo que hacía difícil replicar resultados y comparar métodos. El CBIS-DDSM busca resolver este problema al ofrecer un conjunto de datos consistente y curado para la investigación y evaluación en la detección de cáncer de mama.

## Contenido del Dataset

El dataset contiene un total de **3,103 imágenes** y **3,577 objetos etiquetados** pertenecientes a una sola clase (estructura anómala o `abnormal_structure`).

### Estructura del Dataset

- **Total de imágenes**: 3,103
  - **Con calcificaciones**: 753 casos
  - **Con masas**: 891 casos
- **Etiquetas**: Cada imagen contiene anotaciones de instancias a nivel de píxel y puede transformarse para tareas de detección de objetos (cuadros delimitadores) o segmentación semántica.
- **Divisiones**:
  - **Conjunto de entrenamiento**: 2,458 imágenes
  - **Conjunto de prueba**: 645 imágenes
  - Además, el dataset puede dividirse en:
    - **Tipo de caso**: Calcificación (1,511 imágenes) y masa (1,592 imágenes)
    - **Vista de imagen**: MLO (1,643 imágenes) y CC (1,460 imágenes)
    - **Lado**: Izquierdo (1,592 imágenes) y derecho (1,511 imágenes)
    - **Patología**:
      - Maligno: 1,367 imágenes
      - Benigno: 1,336 imágenes
      - Benigno sin callback: 400 imágenes
    - **BI-RADS Assessment**:
      - Assessment 4: 1,544 imágenes
      - Assessment 5: 532 imágenes
      - Assessment 3: 429 imágenes
      - Assessment 2: 357 imágenes
      - Assessment 0: 239 imágenes
      - Assessment 1: 2 imágenes

## Anotaciones Incluidas

Cada imagen en el dataset incluye metadatos y anotaciones en formato DICOM. Las anotaciones y etiquetas disponibles son:
- **Categoría de densidad**
- **Lado de la mama**: Izquierda o derecha
- **Vista de la imagen**: CC o MLO
- **Forma de la masa** (cuando aplica)
- **Bordes de la masa** (cuando aplica)
- **Tipo de calcificación** (cuando aplica)
- **Distribución de la calcificación** (cuando aplica)
- **Clasificación BI-RADS**: Evaluación general de BI-RADS de 0 a 5
- **Patología**: Benigno, Benigno sin callback, o Maligno


## Ejemplo de Uso

Este dataset es adecuado para:
- **Detección de objetos**: Identificación de áreas anómalas mediante cuadros delimitadores.
- **Segmentación de instancias**: Etiquetado a nivel de píxel de estructuras anómalas.
- **Segmentación semántica**: Un solo "máscara" para cada clase anómala en las imágenes de mamografía.


## Conjunto de Validación Externa (Aporte Local)

Adicionalmente a los datos base del CBIS-DDSM, este proyecto incorpora un conjunto de validación esencial para probar la generalización del modelo en un entorno clínico real:

* Imágenes de Validación Externa (Experimento Local): 20 mamografías reales de pacientes peruanas.

* Propósito: Evaluar la eficacia del modelo entrenado en un contexto clínico distinto al del dataset de entrenamiento, simulando su aplicación en hospitales públicos del Perú.


## Enlaces de Referencia

- [Dataset Original](https://www.cancerimagingarchive.net/collection/cbis-ddsm/) - Enlace al sitio de The Cancer Imaging Archive

- [CBIS-DDSM - Dataset Ninja](https://datasetninja.com/cbis-ddsm) - Enlace a Dataset Ninja si está disponible
