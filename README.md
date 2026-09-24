# 🎗️ De la mamografía a la detección: Pensando como una IA

Taller práctico e introductorio para explorar cómo una IA analiza mamografías y apoya la detección de anomalías mediante un simulador interactivo.

## Taller listo para usar

1. [Antes de mirar una mamografía](notebooks/00_antes_de_la_mamografia.ipynb): lectura breve de anatomía, mamografía, masas y calcificaciones, con dos esquemas explicados. No incluye preguntas ni revela los casos reales.
2. [Conociendo CBIS-DDSM](notebooks/01_conociendo_cbis_ddsm.ipynb): lectura breve sobre archivos, filas, series DICOM y particiones, con dos gráficos explicados. No incluye preguntas ni revela los resultados de los casos.
3. [Taller guiado con mamografías](notebooks/02_taller_mamografia.ipynb): tres casos reales. En cada uno puedes mover un punto azul sobre la imagen antes de revelar la máscara de referencia.

[Paquete para Google Colab](taller_colab.zip): los tres notebooks, CSV de metadatos y copias DICOM de los tres casos en un solo archivo.

### Uso local

Abre los tres notebooks en el orden indicado arriba y ejecuta las celdas de cada uno en orden. Necesitas Python con NumPy y Matplotlib; los notebooks que leen DICOM instalan pydicom si falta.

### Uso en Google Colab

1. Descomprime `taller_colab.zip` en tu computadora y abre primero `notebooks/00_antes_de_la_mamografia.ipynb` en Colab. Este notebook funciona sin subir datos.
2. Después abre `notebooks/01_conociendo_cbis_ddsm.ipynb` en Colab. Cuando lo solicite, sube **el archivo ZIP completo**.
3. Abre `notebooks/02_taller_mamografia.ipynb`. Si Colab inició una sesión nueva, vuelve a subir el ZIP cuando lo solicite. En cada caso elige la posición con los controles, ejecuta la celda que muestra tu punto azul y después revela la máscara.

Si tu entorno local no dispone de controles visuales, el cuaderno muestra cómo indicar la posición como dos porcentajes. Ninguna celda queda esperando una respuesta de teclado.

Los tres casos del taller están en `data/taller/dicom/` como copias intactas de las mamografías y máscaras DICOM, junto con `data/taller/casos.json`. El notebook no necesita acceder al conjunto completo. Verificamos que las copias coinciden byte por byte con los archivos de origen; la fuente original no se modificó. Las máscaras son anotaciones de referencia del conjunto de datos, no detecciones generadas por una IA. Este material es docente y no sirve para interpretación clínica.

Fuente: [CBIS-DDSM en The Cancer Imaging Archive](https://www.cancerimagingarchive.net/collection/cbis-ddsm/) (CC BY 3.0).
