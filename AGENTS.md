# OpenCV

Reconocimiento facial con OpenCV: captura de rostros desde webcam a carpetas por persona y reconocimiento con clasificadores Haar.

## Visibilidad y rama

- Público.
- Rama por defecto: `master`.

## Stack

- Python 3.
- Dependencias (del README, sin fichero de requisitos): `opencv-contrib-python`, `numpy`, `matplotlib`. Paquete del sistema: `python3-tk`.
- Basado en https://github.com/futurelabmx/FaceRecognition2.

## Estructura

- `capture.py`: captura imágenes de la webcam (`cv2.VideoCapture(0)`) y las guarda en `att_faces/orl_faces/<nombre>` a partir del argumento `sys.argv[1]`.
- `reconocimiento2.py`: reconocimiento facial sobre las capturas (no revisado en detalle).
- `haarcascade_frontalface_default.xml` y `haarcascade_frontalface_alt.xml`: clasificadores Haar (ficheros de OpenCV).
- `README.md`: requisitos y origen.
- `.gitignore`: plantilla estándar de Python (incluye `venv/`, `__pycache__/`).

## Comandos

Del README y del código (no ejecutados):

- Instalar: `sudo apt install python3-tk` (requiere permiso; ver reglas) y `pip3 install opencv-contrib-python`.
- Capturar rostros: `python3 capture.py <nombre>`.
- Reconocimiento: `python3 reconocimiento2.py` (argumentos no verificados).
- Tests: no hay.

## Configuración

- Sin variables de entorno.
- Rutas relativas: `att_faces/orl_faces` y los XML de Haar en el directorio de ejecución.
- Tamaños codificados: `size = 4`, `img_width, img_height = 112, 92`.

## Convenciones para agentes

- Ejecutar desde el directorio del repo para que las rutas relativas funcionen.
- El nombre de la persona es el argumento obligatorio de `capture.py`; sin argumento el script falla.
- No versionar capturas de personas reales: `att_faces/` no está en `.gitignore`.

## Estado

- Sin tests.
- Atención: `capture.py` crea directorios con `os.mkdir` (no `makedirs`); si `att_faces/orl_faces` no existe, falla.
- Atención: `capture.py` importa `matplotlib` y `numpy`, pero no está en el README como requisito explícito (solo `opencv-contrib-python`).
- Atención: el repo contiene datos biométricos potenciales si se suben las capturas; revisar antes de publicar.
- El código tiene comentarios en español y mezcla estilo con código antiguo.
