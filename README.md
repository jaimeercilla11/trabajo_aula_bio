# Práctica 1: Simulación del Dogma Central y Análisis Bioinformático

**Asignatura:** Bioinformática  
**Titulaciones:** Grado en Ciencia e Ingeniería de Datos 
---

📄 **[Descargar la Memoria Académica en PDF](./MEMORIA_PRAC_1.pdf)**

## Descripción del Proyecto

Este repositorio contiene la resolución práctica y los scripts desarrollados para simular y analizar los procesos clave del **Dogma Central de la Biología Molecular**: Replicación, Transcripción, Traducción, Splicing Alternativo y relación Estructura-Función de las proteínas.

El proyecto está implementado en un entorno **Jupyter Notebook (`.ipynb`)** apoyándose en la librería especializada **Biopython** y consultas mediante API REST a la base de datos biológica **Ensembl**.

---

## Contenido de los Ejercicios

### Ejercicio 1: Replicación del ADN
* **Mecanismo:** Simulación semiconservativa partiendo de la doble hebra $5'\text{--ATG CCG TTA GCT--}3'$.
* **Enzimas analizadas:** Helicasa, Primasa, ADN Polimerasa y Ligasa.
* **Extensión Biopython:** Generación programática de la hebra complementaria y complementaria reversa (`reverse_complement()`).

### Ejercicio 2: Transcripción del ADN a ARN
* **Identificación de hebras:** Diferenciación entre hebra molde ($3' \rightarrow 5'$) y hebra codificante ($5' \rightarrow 3'$).
* **Mecanismo:** Obtención del ARNm sustituyendo Timina (T) por Uracilo (U).
* **Conceptos:** Definición de región promotora (caja TATA) y región codificante.
* **Extensión Biopython:** Cambio de orientación del molde y análisis del efecto en la secuencia del ARNm.

### Ejercicio 3: Traducción del ARNm a Proteína
* **Lectura:** Agrupación en tripletes (codones) de la secuencia $5'\text{--AUG UAU GCU UAA--}3'$.
* **Resultado:** Síntesis del péptido `Met - Tyr - Ala` (`M - Y - A`).
* **Mutaciones:** Análisis del impacto de mutaciones en el codón de inicio (`AUG` $\rightarrow$ `GUG`) y pérdida del codón STOP.
* **Extensión Biopython:** Traducción automatizada con `Bio.Seq.translate()`.

### Ejercicio 4: Splicing Alternativo
* **Isoformas diseñadas:** A partir de un pre-ARNm de 5 exones, se simulan las variantes $1-2-4-5$ (Isoforma A) y $1-3-5$ (Isoforma B).
* **Impacto:** Consecuencias en localización celular, dominios catalíticos y afinidad por ligandos.
* **Reflexión:** Expansión del proteoma sin sobrecargar el tamaño del genoma.
* **Extensión Ensembl:** Consulta vía API REST del gen humano **FGFR2** (`ENSG00000066468`), identificando 59 transcritos/isoformas.

### Ejercicio 5: Introducción a las Proteínas
* **Análisis peptídico:** Secuencia `Met - Ile - Ser - Gly - Val - Lys - His`. Identificación del extremo N-terminal (Met) y C-terminal (His).
* **Estructura y Mutaciones:** Análisis del efecto hidrofóbico en el núcleo proteico y desnaturalización por sustitución de residuos apolares por polares.
* **Extensión PDB:** Carga de la estructura tridimensional de la Mioglobina (`1A6M.cif`) utilizando `MMCIFParser` de Biopython (151 aminoácidos).

### Ejercicio 6: Actividad Integradora (Pipeline Bioinformático)
* **Desarrollo:** Función `pipeline_dogma_central()` que procesa automáticamente una secuencia de ADN en sentido $5' \rightarrow 3'$.
* **Feedback en tiempo real:** Reporte detallado de la acción enzimática en Replicación, Transcripción y Traducción en tripletes hasta el codón STOP.
* **Reflexión:** Justificación de por qué la **Replicación del ADN** es la fase más vulnerable a mutaciones permanentes.

---

## Requisitos e Instalación

Para ejecutar el cuaderno de Jupyter, es necesario disponer de Python 3.10+ y las siguientes librerías:

```bash
pip install biopython requests jupyter
