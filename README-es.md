<div align="center">
<h1 align="center">MoneyPrinterTurbo 💸</h1>

<p align="center">
  <a href="https://github.com/harry0703/MoneyPrinterTurbo/stargazers"><img src="https://img.shields.io/github/stars/harry0703/MoneyPrinterTurbo.svg?style=for-the-badge" alt="Stargazers"></a>
  <a href="https://github.com/harry0703/MoneyPrinterTurbo/issues"><img src="https://img.shields.io/github/issues/harry0703/MoneyPrinterTurbo.svg?style=for-the-badge" alt="Issues"></a>
  <a href="https://github.com/harry0703/MoneyPrinterTurbo/network/members"><img src="https://img.shields.io/github/forks/harry0703/MoneyPrinterTurbo.svg?style=for-the-badge" alt="Forks"></a>
  <a href="https://github.com/harry0703/MoneyPrinterTurbo/blob/main/LICENSE"><img src="https://img.shields.io/github/license/harry0703/MoneyPrinterTurbo.svg?style=for-the-badge" alt="License"></a>
</p>

<h3><a href="README.md">简体中文</a> | <a href="README-en.md">English</a> | Español</h3>

<div align="center">
  <a href="https://trendshift.io/repositories/8731" target="_blank"><img src="https://trendshift.io/api/badge/repositories/8731" alt="harry0703%2FMoneyPrinterTurbo | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>
</div>

Simplemente proporciona un <b>tema</b> o <b>palabra clave</b> para un video, y generará automáticamente el guion, los materiales, los subtítulos y la música de fondo antes de sintetizar un video corto en alta definición.

### Interfaz Web

![](docs/webui.jpg)

### Interfaz API

![](docs/api.jpg)

</div>

## Características 🎯

- [x] **Arquitectura MVC** completa, código **bien estructurado**, fácil de mantener, soporta `API` e `Interfaz Web`
- [x] Soporta **generación automática por IA** del guion del video, así como **guion personalizado**
- [x] Soporta varios tamaños de **video en alta definición**
    - [x] Vertical 9:16, `1080x1920`
    - [x] Horizontal 16:9, `1920x1080`
- [x] Soporta **generación por lotes** de videos, permite crear varios videos a la vez y elegir el más satisfactorio
- [x] Soporta configuración de la **duración de los clips de video**, facilita ajustar la frecuencia de cambio de materiales
- [x] Soporta guiones de video en **español**, **inglés**, **chino** y más
- [x] Soporta **múltiples voces** de síntesis, con **vista previa en tiempo real**
- [x] Soporta **generación de subtítulos**, con ajustes de `fuente`, `posición`, `color`, `tamaño`, y también `contorno de subtítulos`
- [x] Soporta **música de fondo**, aleatoria o archivos específicos, con `volumen de música de fondo` ajustable
- [x] Las fuentes de materiales de video son en **alta definición** y **libres de derechos**, y también puedes usar tus propios **materiales locales**
- [x] Soporta integración con múltiples modelos como **OpenAI**, **Moonshot**, **Azure**, **gpt4free**, **one-api**, **Qwen**, **Google Gemini**, **Ollama**, **DeepSeek**, **MiniMax**, **ERNIE**, **Pollinations**, **ModelScope** y más

## Requisitos del sistema 📦

- Plataformas recomendadas: Windows 10+, macOS 11+, o una distribución Linux convencional
- No se requiere GPU, pero se recomienda si desea transcripción local más rápida, procesamiento de video más veloz o generación por lotes más fluida

| Componente | Mínimo | Recomendado | Óptimo |
| --- | --- | --- | --- |
| CPU | 4 núcleos | 6 a 8 núcleos | 8+ núcleos |
| RAM | 4 GB | 8 GB | 16+ GB |
| GPU | No requerida | 4+ GB VRAM | 8+ GB VRAM |

- Si depende principalmente de LLMs en la nube, TTS en la nube y fuentes de materiales en línea, CPU y RAM importan más que la GPU
- Si usa `faster-whisper`, generación por lotes o procesamiento local pesado, una GPU mejorará notablemente el rendimiento

## Inicio rápido 🚀

### Rutas recomendadas

- Usuarios de Windows: usar el paquete de un clic para la prueba local más rápida
- Usuarios de macOS / Linux: usar `uv sync --frozen` para la instalación local principal
- Si desea un entorno más aislado: usar despliegue con Docker

### Ejecutar en Google Colab

¿Quieres probar MoneyPrinterTurbo sin configurar un entorno local? ¡Ejecútalo directamente en Google Colab!

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/harry0703/MoneyPrinterTurbo/blob/main/docs/MoneyPrinterTurbo.ipynb)


### Windows

El paquete descargable es la versión empaquetada anterior `v1.2.6`. Después de descargar, ejecute `update.bat` primero para actualizar al código más reciente.

Google Drive (v1.2.6): https://drive.google.com/file/d/1HsbzfT7XunkrCrHw5ncUjFX8XX4zAuUh/view?usp=sharing

Después de descargar, se recomienda **hacer doble clic** en `update.bat` primero para actualizar al **código más reciente**, luego hacer doble clic en `start.bat` para iniciar

Tras iniciar, el navegador se abrirá automáticamente (si se abre en blanco, se recomienda usar **Chrome** o **Edge**)

### Otros sistemas

Aún no se han creado paquetes de inicio de un clic. Consulte la sección **Instalación y despliegue** más abajo. Se recomienda usar **Docker** para el despliegue, es más conveniente.

## Instalación y despliegue 📥

### Requisitos previos

- Evite usar **rutas con caracteres especiales** o **espacios** para prevenir problemas impredecibles
- Asegúrese de que su **red** funcione correctamente; si usa VPN, active el modo de `tráfico global`

#### ① Clonar el proyecto

```shell
git clone https://github.com/harry0703/MoneyPrinterTurbo.git
```

#### ② Modificar el archivo de configuración (opcional, también puede configurarse desde la interfaz Web)

- Copie el archivo `config.example.toml` y renómbrelo como `config.toml`
- Siga las instrucciones en `config.toml` para configurar `pexels_api_keys` y `llm_provider`, y configure la clave API correspondiente al proveedor elegido

### Despliegue con Docker 🐳

#### ① Iniciar el contenedor Docker

Si no tiene Docker instalado, instálelo primero: https://www.docker.com/products/docker-desktop/

Si usa Windows, consulte la documentación de Microsoft:

1. https://learn.microsoft.com/es-es/windows/wsl/install
2. https://learn.microsoft.com/es-es/windows/wsl/tutorials/wsl-containers

```shell
cd MoneyPrinterTurbo
docker-compose up
```

> Nota: La última versión de Docker instala docker compose como complemento automáticamente. El comando de inicio cambia a `docker compose up`

#### ② Acceder a la interfaz Web

Abra su navegador y visite http://0.0.0.0:8501

#### ③ Acceder a la documentación de la API

Abra su navegador y visite http://0.0.0.0:8080/docs o http://0.0.0.0:8080/redoc

### Despliegue manual 📦

#### ① Crear un entorno virtual de Python

Se recomienda usar [uv](https://docs.astral.sh/uv/) para gestionar el entorno Python y las dependencias, con Python `3.11` como versión por defecto.

```shell
git clone https://github.com/harry0703/MoneyPrinterTurbo.git
cd MoneyPrinterTurbo
uv python install 3.11
uv sync --frozen
```

Si aún no usa `uv`, puede continuar con `venv + pip`.

```shell
python3.11 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Notas:
- `pyproject.toml` es el manifiesto de dependencias principal.
- `uv.lock` fija el entorno resuelto, por lo que se recomienda `uv sync --frozen` por defecto.
- `requirements.txt` se mantiene solo para instalación heredada con `pip`.

#### ② Instalar ImageMagick

###### Windows:

- Descargue desde https://imagemagick.org/script/download.php eligiendo la versión Windows. Asegúrese de seleccionar la versión de **biblioteca estática**, como ImageMagick-7.1.1-32-Q16-x64-**static**.exe
- Instale ImageMagick, **no cambie la ruta de instalación**
- Modifique el archivo `config.toml`, estableciendo `imagemagick_path` con la ruta de instalación real

###### macOS:

```shell
brew install imagemagick
```

###### Ubuntu

```shell
sudo apt-get install imagemagick
```

###### CentOS

```shell
sudo yum install ImageMagick
```

#### ③ Iniciar la interfaz Web 🌐

Nota: Ejecute los siguientes comandos en el **directorio raíz** del proyecto MoneyPrinterTurbo

###### Windows

```shell
uv run streamlit run ./webui/Main.py --browser.gatherUsageStats=False
```

Si ya activó el entorno virtual manualmente, también puede ejecutar:

```bat
webui.bat
```

###### macOS o Linux

```shell
uv run streamlit run ./webui/Main.py --browser.gatherUsageStats=False
```

Si ya activó el entorno virtual manualmente, también puede ejecutar:

```shell
sh webui.sh
```

Tras iniciar, el navegador se abrirá automáticamente

#### ④ Iniciar el servicio API 🚀

```shell
uv run python main.py
```

Si ya activó el entorno virtual manualmente, también puede ejecutar:

```shell
python main.py
```

Tras iniciar, puede ver la `documentación de la API` en http://127.0.0.1:8080/docs y probar las interfaces directamente en línea para una experiencia rápida.

## Síntesis de voz 🗣

La lista completa de voces soportadas se puede consultar aquí: [Lista de voces](./docs/voice-list.txt)

2024-04-16 v1.1.2 Se añadieron 9 nuevas voces de síntesis de Azure que requieren configuración de CLAVE API. Estas voces suenan más naturales.

## Generación de subtítulos 📜

Actualmente hay 2 formas de generar subtítulos:

- **edge**: Velocidad de generación más rápida, mejor rendimiento, sin requisitos especiales de hardware, pero la calidad puede ser inestable
- **whisper**: Velocidad de generación más lenta, mayor consumo de recursos, requiere mejor hardware, pero calidad más confiable

Puede cambiar entre ellos modificando `subtitle_provider` en el archivo `config.toml`

Se recomienda usar el modo `edge`, y cambiar a `whisper` si la calidad de los subtítulos generados no es satisfactoria.

> Nota:
>
> 1. En modo whisper, necesita descargar un archivo de modelo desde HuggingFace, de unos 3 GB. Asegúrese de tener buena conexión a internet
> 2. Si se deja vacío, no se generarán subtítulos

## Música de fondo 🎵

La música de fondo para los videos se encuentra en el directorio `resource/songs` del proyecto.
> El proyecto incluye algo de música predeterminada de videos de YouTube. Si hay problemas de derechos de autor, elimínela.

## Fuentes de subtítulos 🅰

Las fuentes para renderizar los subtítulos del video se encuentran en el directorio `resource/fonts` del proyecto. También puede añadir sus propias fuentes.

## Preguntas frecuentes 🤔

### ❓RuntimeError: No ffmpeg exe could be found

Normalmente, ffmpeg se descarga y detecta automáticamente.
Sin embargo, si su entorno tiene problemas que impiden la descarga automática, puede encontrar este error:

```
RuntimeError: No ffmpeg exe could be found.
Install ffmpeg on your system, or set the IMAGEIO_FFMPEG_EXE environment variable.
```

En este caso, puede descargar ffmpeg desde https://www.gyan.dev/ffmpeg/builds/, descomprimirlo y establecer `ffmpeg_path` con la ruta de instalación real.

```toml
[app]
# Configure según su ruta real. Nota: en Windows los separadores de ruta son \\
ffmpeg_path = "C:\\Users\\usuario\\Descargas\\ffmpeg.exe"
```

### ❓ImageMagick no está instalado en su equipo

1. Siga la `configuración de ejemplo` proporcionada en la `dirección de descarga` para instalar https://imagemagick.org/archive/binaries/ImageMagick-7.1.1-30-Q16-x64-static.exe, usando la biblioteca estática
2. No instale en una ruta con caracteres especiales para evitar problemas impredecibles

Para sistemas Linux, puede instalarlo manualmente consultando https://cn.linux-console.net/?p=16978

### ❓La política de seguridad de ImageMagick impide operaciones con archivos temporales @/tmp/tmpur5hyyto.txt

Puede encontrar estas políticas en el archivo de configuración de ImageMagick `policy.xml`.
Este archivo suele estar en `/etc/ImageMagick-X/` o una ubicación similar en el directorio de instalación.
Modifique la entrada que contiene `pattern="@"`, cambiando `rights="none"` por `rights="read|write"` para permitir operaciones de lectura y escritura en archivos.

### ❓OSError: [Errno 24] Too many open files

Este problema se debe al límite del sistema en la cantidad de archivos abiertos. Puede resolverlo modificando el límite del sistema.

Verifique el límite actual:

```shell
ulimit -n
```

Si es muy bajo, puede aumentarlo, por ejemplo:

```shell
ulimit -n 10240
```

### ❓Error al descargar el modelo Whisper

LocalEntryNotFoundError: Cannot find an appropriate cached snapshot folder for the specified revision on the local disk and outgoing traffic has been disabled.

o

An error occurred while synchronizing the model Systran/faster-whisper-large-v3 from the Hugging Face Hub:
An error happened while trying to locate the files on the Hub and we cannot find the appropriate snapshot folder for the specified revision on the local disk. Please check your internet connection and try again.

Solución: [Clic para ver cómo descargar el modelo manualmente](#generación-de-subtítulos-)

## Comentarios y sugerencias 📢

- Puede enviar un [issue](https://github.com/harry0703/MoneyPrinterTurbo/issues) o un [pull request](https://github.com/harry0703/MoneyPrinterTurbo/pulls).

## Licencia 📝

Haga clic para ver el archivo [`LICENSE`](LICENSE)

## Historial de estrellas

[![Star History Chart](https://api.star-history.com/svg?repos=harry0703/MoneyPrinterTurbo&type=Date)](https://star-history.com/#harry0703/MoneyPrinterTurbo&Date)
