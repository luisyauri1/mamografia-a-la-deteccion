# 🎗️ De la mamografía a la detección: Pensando como una IA

Taller práctico e introductorio para explorar cómo una IA analiza mamografías y apoya la detección de anomalías mediante un simulador interactivo.

## Taller listo para usar

1. [Antes de mirar una mamografía](notebooks/00_antes_de_la_mamografia.ipynb): lectura breve de anatomía, mamografía, masas y calcificaciones, con dos esquemas explicados. No incluye preguntas ni revela los casos reales.
2. [Conociendo CBIS-DDSM](notebooks/01_conociendo_cbis_ddsm.ipynb): lectura breve sobre archivos, filas, series DICOM y particiones, con dos gráficos explicados. No incluye preguntas ni revela los resultados de los casos.
3. [Taller guiado con mamografías](notebooks/02_taller_mamografia.ipynb): tres casos reales. En cada uno puedes mover un punto azul sobre la imagen antes de revelar la máscara de referencia.
4. [Un detector público frente a dos mamografías](notebooks/03_modelo_publico.ipynb): actividad opcional para comparar los recuadros de un modelo de masas con las máscaras de referencia.

[Paquete para Google Colab](taller_colab.zip): los cuatro notebooks, CSV de metadatos, copias DICOM de los tres casos y el modelo público en un solo archivo.

### Uso local

Abre los notebooks en el orden indicado arriba y ejecuta las celdas de cada uno en orden. El cuaderno 03 es opcional e instala Ultralytics si hace falta.

### Uso en Google Colab

1. Descomprime `taller_colab.zip` en tu computadora y abre primero `notebooks/00_antes_de_la_mamografia.ipynb` en Colab. Este notebook funciona sin subir datos.
2. Después abre `notebooks/01_conociendo_cbis_ddsm.ipynb` en Colab. Cuando lo solicite, sube **el archivo ZIP completo**.
3. Abre `notebooks/02_taller_mamografia.ipynb`. Si Colab inició una sesión nueva, vuelve a subir el ZIP cuando lo solicite. En cada caso elige la posición con los controles, ejecuta la celda que muestra tu punto azul y después revela la máscara.
4. Si quieres ver una predicción real, abre `notebooks/03_modelo_publico.ipynb`. En una sesión nueva de Colab, sube el mismo ZIP cuando lo solicite. Ejecuta las celdas en orden y compara el recuadro amarillo del modelo con la zona roja de referencia.

Si tu entorno local no dispone de controles visuales, el cuaderno muestra cómo indicar la posición como dos porcentajes. Ninguna celda queda esperando una respuesta de teclado.

Los tres casos del taller están en `data/taller/dicom/` como copias intactas de las mamografías y máscaras DICOM, junto con `data/taller/casos.json`. El notebook no necesita acceder al conjunto completo. Verificamos que las copias coinciden byte por byte con los archivos de origen; la fuente original no se modificó. Las máscaras son anotaciones de referencia del conjunto de datos, no detecciones generadas por una IA. Este material es docente y no sirve para interpretación clínica.

Fuente: [CBIS-DDSM en The Cancer Imaging Archive](https://www.cancerimagingarchive.net/collection/cbis-ddsm/) (CC BY 3.0).

El modelo del cuaderno 03 es una copia del checkpoint `yolo11_n.pt` de [Digital Eye for Mammography, versión shared-models.v2](https://github.com/cbddobvyz/digitaleye-mammography/releases/tag/shared-models.v2) (GPL-3.0). Su SHA-256 se verifica antes de cargarlo. Busca masas; no se usa para el caso de calcificaciones. Sus recuadros y puntuaciones son salidas del modelo, no diagnósticos.
