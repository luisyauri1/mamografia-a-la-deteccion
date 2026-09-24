# 🎗️ De la mamografía a la detección: Pensando como una IA

Taller práctico e introductorio para explorar cómo una IA analiza mamografías y apoya la detección de anomalías mediante un simulador interactivo.

## Taller listo para usar

- [Notebook guiado](notebooks/taller_mamografia.ipynb): tres casos, observación, lectura de metadatos y revelación de máscaras.
- [Paquete para Google Colab](taller_colab.zip): notebook y datos reducidos en un solo archivo.

### Uso local

Abre `notebooks/taller_mamografia.ipynb` en Jupyter o VS Code y ejecuta las celdas en orden. Necesitas Python con NumPy, Pillow y Matplotlib.

### Uso en Google Colab

1. Descomprime `taller_colab.zip` en tu computadora y abre `notebooks/taller_mamografia.ipynb` en Colab.
2. Ejecuta la primera celda de preparación. Cuando lo solicite, sube **el archivo ZIP completo**.
3. Continúa celda por celda y registra cada hipótesis antes de revelar la máscara.

Los tres casos del taller están en `data/taller/` como imágenes PNG reducidas y un archivo de metadatos. El notebook no necesita acceder al conjunto completo. Los DICOM originales de CBIS-DDSM no se modificaron. Este material es docente y no sirve para interpretación clínica.

Fuente: [CBIS-DDSM en The Cancer Imaging Archive](https://www.cancerimagingarchive.net/collection/cbis-ddsm/) (CC BY 3.0).
