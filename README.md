# 🎗️ De la mamografía a la detección: Pensando como una IA

Taller práctico e introductorio para explorar cómo una IA analiza mamografías y apoya la detección de anomalías mediante un simulador interactivo.

## Taller listo para usar

1. [Taller guiado con mamografías](notebooks/01_taller_mamografia.ipynb): tres casos para practicar con deslizadores y una galería final que se dibuja al ejecutar el cuaderno con ocho mamografías marcadas.
2. [Cómo trabaja un detector público](notebooks/02_modelo_publico.ipynb): actividad opcional que muestra paso a paso la imagen de entrada, la preparación de tres canales, la predicción y sus recuadros. Después repite el proceso con cuatro casos de masas.

[Paquete para Google Colab](taller_colab.zip): los dos notebooks, ocho mamografías PNG, las coordenadas de referencia y el modelo público en un solo archivo.

### Uso local

Abre los notebooks en el orden indicado arriba y ejecuta las celdas de cada uno en orden. El cuaderno 02 es opcional e instala Ultralytics si hace falta.

### Uso en Google Colab

1. Descomprime `taller_colab.zip` en tu computadora y abre `notebooks/01_taller_mamografia.ipynb` en Colab. Cuando lo solicite, sube **el archivo ZIP completo**. En cada caso elige la posición con los controles, ejecuta la celda que muestra tu cuadrado celeste y después revela el recuadro rojo de referencia.
2. Si quieres ver cómo se usa un modelo real, abre `notebooks/02_modelo_publico.ipynb`. En una sesión nueva de Colab, sube el mismo ZIP cuando lo solicite. Ejecuta las celdas en orden: primero seguirás un caso paso a paso y luego verás los resultados de cuatro mamografías de masas.

El cuaderno 01 usa los deslizadores integrados de Colab; no necesita `ipywidgets`. Si lo abres en otro entorno, puedes cambiar los dos números de 0 a 100 en la celda correspondiente. Ninguna celda queda esperando una respuesta de teclado.

Los cuadernos usan ocho PNG en `data/taller/imagenes/`: tres en la actividad guiada y los ocho en la galería que genera el cuaderno 01 al ejecutarse. Los cuatro casos de calcificaciones se llaman `calcificaciones_1` a `calcificaciones_4`. Cada caso de `data/taller/casos.json` guarda `recuadro_referencia` como cuatro números: izquierda, arriba, derecha y abajo, en píxeles de ese mismo PNG. Calculamos esas coordenadas una vez a partir de la máscara DICOM original y comprobamos su alineación con la imagen. El cuaderno 01 convierte los porcentajes elegidos con los deslizadores en la posición del cuadrado celeste. El cuaderno 02 calcula el recuadro amarillo con el modelo al ejecutarse. Los recuadros rojos usan las coordenadas guardadas: son referencias del conjunto de datos, no detecciones de una IA.

Los PNG se prepararon a partir de CBIS-DDSM con el mismo ajuste de contraste que antes se hacía al mostrar la imagen. Las copias DICOM de trabajo se eliminaron de este proyecto; el ZIP tampoco contiene DICOM. La carpeta fuente original no se modificó. Este material es docente y no sirve para interpretación clínica.

Fuente: [CBIS-DDSM en The Cancer Imaging Archive](https://www.cancerimagingarchive.net/collection/cbis-ddsm/) (CC BY 3.0).

El modelo del cuaderno 02 es una copia del checkpoint `yolo11_n.pt` de [Digital Eye for Mammography, versión shared-models.v2](https://github.com/cbddobvyz/digitaleye-mammography/releases/tag/shared-models.v2) (GPL-3.0). Su SHA-256 se verifica antes de cargarlo. Busca masas; no se usa para el caso de calcificaciones. Sus recuadros y puntuaciones son salidas del modelo, no diagnósticos.
