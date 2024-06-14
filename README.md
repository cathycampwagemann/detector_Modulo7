# UTILIZACIÓN DE REDES NEURONALES PARA LA DETECCIÓN DE NEUMONÍA

# Descripción del proyecto

Este proyecto utiliza como base un dataset de radiografías de tórax de niños del Centro para Mujeres y Niños de Cantón, China, para entrenar un modelo de clasificación binaria que determina si una radiografía presenta signos de neumonía o no.

# Tabla de contenidos

1. [Instalación](#instalación)
2. [Uso](#uso)
3. [Estructura de directorios](#estructura-de-directorios)
4. [Modelo](#modelo)
5. [Análisis exploratorio](#análisis-exploratorio)
6. [Transformación de imágenes](#transformación-de-imágenes)
7. [Autores](#autores)
8. [Licencia](#licencia)
9. [Agradecimientos](#agradecimientos)

#  Instalación

1. Crear y activar un Entorno Virtual
   
-  Crea un entorno virtual llamado 'detector_neumonia' usando la herramienta de tu preferencia (por ejemplo, conda):

   conda create --name detector_neumonia

-  Activa el entorno virtual:
  
   conda activate detector_neumonia
     
2. Clonar Repositorio
   
-  Clona este repositorio en tu máquina local:
  
   https://github.com/cathycampwagemann/detector_M7.git
   
-  Selecciona la branch "principal":

   cd detector_M7
   git checkout principal
   
4. Instalar Requisitos

-  Instala los paquetes requeridos listados en 'requirements.txt'

   pip install -r requirements.txt

5. Ejecutar API

-  Selecciona la carpeta "app"

   cd app  

-  Ejecuta el script `api.py` para iniciar el servidor de la API:

   python api.py
   
6. Hacer predicciones
   
-  Una vez que el servidor de la API esté en funcionamiento, navega a la dirección IP que te indique el entorno virtual.

-  Para hacer las predicciones puedes utilizar las imágenes que se encuentran en el siguiente enlace:
  
   https://drive.google.com/drive/folders/1PAq-0GYDzyJonPPt-_XfywslH2xnWZpe?usp=sharing  

#  Uso

Una vez que la aplicación esté en funcionamiento, puedes acceder a ella desde tu navegador visitando la dirección IP que te indique el entorno virtual. 

La aplicación te proporcionará una interfaz interactiva donde podrás ingresar la imagen que quieres analizar y la carpeta donde se encuentra esta (por ejemplo, 'C:\Users\catyc\Downloads\img\') y obtener predicciones si la imagen muestra signos de neumonía o no.

#  Estructura de directorios

1. 'app/': Contiene los archivos de la aplicación Flask.
   
2. 'experimentos/': Contiene notebooks con el resumen ejecutivo, el análisis y exploración de los datos, la transformación      de las imágenes y el entrenamiento, prueba y validación del modelo, y los resultados y conclusiones.

3. 'modelo/': Contiene el modelo de clasificación de clasificación entrenado, que también se puede encontrar en el 
   siguiente enlace: https://drive.google.com/file/d/1Ed9g2Rj_k7CPF8ClBalaYfDhfbNlsuTC/view?usp=drive_link.
   
#  Modelo

Es una red neuronal convolucional que tiene como base una DenseNet, que customicé según los requerimientos de mi modelo (entre ellos, ser un modelo de clasificación binaria).

#  Análisis exploratorio

El dataset utilizado fueron radiografías de tórax de niños del Centro Médico para mujeres y niños de Cantón, China.
En el análisis exploratorio se detectó que: las imágenes tenían distintas dimensiones; la mayoría de las imágenes estaba en escala de grises, pero otras en RGB; existía desbalanceo de las categorías.

Puedes descargar el dataset en el siguiente enlace: https://drive.google.com/file/d/1Ed9g2Rj_k7CPF8ClBalaYfDhfbNlsuTC/view?usp=drive_link.

También puedes descargar el dataframe creado a partir del dataset en el siguiente enlace: https://drive.google.com/file/d/1sN2rvCDgIcXmjCeJG2EmllCb2un4cddc/view?usp=sharing

#  Tansformación de imágenes

Para que las imágenes fueran procesadas correctamente, fueron:

1. Redimensionadas según 3 altos distintos (447, 800 y 1440 píxeles). El ancho se redimensionó según las proporcionales        originales.
   
2. Convertidas a escala de grises.
   
3. Para que tuvieran el mismo alto y ancho, sin que perdieran la calidad, se le aplicó padding a todas las imágenes para 
   que quedaran en 1440x1440 píxeles.

4. Luego, fueron nuevamente redimensionadas a 720x720 píxeles para que pudieran ser procesadas sin problemas.

#  Autor

Catherine Campbell Wagemann (https://github.com/cathycampwagemann)

#  Licencia

Este proyecto está bajo la licencia GNU General Public License v3.0. Consulta el archivo [LICENSE] (LICENSE) para más detalles.

#  Agradecimientos

A los profesores y compañeros del Bootcamp de Ciencia de Datos e Inteligencia Artificial C4 de la Universidad del Desarrollo, Santiago, Chile.
