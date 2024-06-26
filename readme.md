# Organizador de Archivos en Python

Este script en Python organiza los archivos de un directorio en carpetas específicas según su tipo. El script crea carpetas para diferentes tipos de archivos y mueve los archivos correspondientes a sus respectivas carpetas.

## Estructura de Carpetas y Tipos de Archivos

El script organiza los archivos en las siguientes categorías:

- **Audios**: mp3, mp2, opus
- **Documentos**: docx, xlsx, xls, pdf, vbs
- **Fotos**: jpg, png, gif, ico
- **Videos**: avi, mp4, mpg, mkv
- **Zips**: rar, zip

## Requisitos

- Python 3.x
- Módulos estándar de Python (`os`, `shutil`)

## Cómo Usar

1. **Clona el repositorio o descarga los archivos**:
    ```sh
    git clone https://github.com/tu-usuario/organizador-de-archivos.git
    cd organizador-de-archivos
    ```

2. **Ubica el script en el directorio que deseas organizar**.

3. **Ejecuta el script**:
    ```sh
    python organizador.py
    ```

## Descripción del Código

### Importación de Módulos

```python
import os
import shutil
```

### Definición de Tipos y Formatos

Se definen las categorías de archivos y los formatos correspondientes:

```python
tipos = ['audios', 'documentos', 'fotos', 'videos', 'zips']
formatos = {
    'audios': ['mp3', 'mp2', 'opus'],
    'documentos': ['docx', 'xlsx', 'xls', 'pdf', 'vbs'],
    'fotos': ['jpg', 'png', 'gif', 'ico'],
    'videos': ['avi', 'mp4', 'mpg', 'mkv'],
    'zips': ['rar', 'zip']
}
```

### Función para Crear Carpetas

Crea las carpetas especificadas en `tipos` si no existen:

```python
def crear_carpetas(tipos):
    for tipo in tipos:
        try:
            os.mkdir(os.getcwd() + '/' + tipo)
        except OSError as e:
            print(e)
```

### Función para Mover Archivos

Mueve los archivos a las carpetas correspondientes basándose en su extensión:

```python
def mover_ficheros(formatos):
    for fichero in os.listdir(os.getcwd()):
        if formatos['audios'].__contains__(fichero.split('.')[-1].lower()):
            shutil.move(os.getcwd() + '/' + fichero, os.getcwd() + '/audios')
            print(fichero)
        elif formatos['documentos'].__contains__(fichero.split('.')[-1].lower()):
            shutil.move(os.getcwd() + '/' + fichero, os.getcwd() + '/documentos')
            print(fichero)
        elif formatos['fotos'].__contains__(fichero.split('.')[-1].lower()):
            shutil.move(os.getcwd() + '/' + fichero, os.getcwd() + '/fotos')
            print(fichero)
        elif formatos['videos'].__contains__(fichero.split('.')[-1].lower()):
            shutil.move(os.getcwd() + '/' + fichero, os.getcwd() + '/videos')
            print(fichero)
        elif formatos['zips'].__contains__(fichero.split('.')[-1].lower()):
            shutil.move(os.getcwd() + '/' + fichero, os.getcwd() + '/zips')
            print(fichero)
```

### Ejecución del Script

```python
if __name__ == '__main__':
    crear_carpetas(tipos)
    mover_ficheros(formatos)
```

## Contacto

- **Autor**: Mario Luis Martínez
- **Correo**: [marioveloper@gmail.com](mailto:marioveloper@gmail.com)
- **Redes Sociales**: En casi todas las redes sociales como [@marioveloper](https://www.twitter.com/marioveloper).

## Licencia

Este proyecto no tiene una licencia específica y su uso está destinado principalmente para fines educativos y personales. Si encuentras algo útil, siéntete libre de utilizarlo.