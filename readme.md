hola
holaa
hoojdjdjdj
d
d
d
d
d
ax

codi workflows

name: "Lint Markdown"

on:
  push:
    branches: ["main", "develop"]
  pull_request:
    branches: ["main", "develop"]

jobs:
  markdown-lint:
    runs-on: ubuntu-latest
    steps:
      - name: "Checkout"
        uses: actions/checkout@v4

      - name: "Run Markdownlint"
        uses: davidanson/markdownlint-cli2-action@v16
        with:
          config: '.markdownlint.json'
          globs: '**/*.md'

commands

1. Preparar el terreno (Ramas)

Antes de tocar el código, siempre hay que saber dónde estamos parados.

    git branch: Te dice en qué rama estás (la que tiene el asterisco *).

    git checkout -b feature-nombre: Crea una rama nueva y te cambia a ella de inmediato.

    git checkout develop: Te cambia a una rama que ya existe (por ejemplo, para volver a desarrollo).

2. El ciclo diario (Guardar y Subir)

Este es el "pan de cada día". Hazlo cada vez que termines una pequeña parte de tu tarea.

    git status: El más importante. Te dice qué archivos cambiaste y si Git los está viendo o no.

    git add .: Le dice a Git: "Toma todo lo que cambié en esta carpeta y prepáralo para el envío".

    git commit -m "explicación corta": Le pone una etiqueta a tu cambio. Es como guardar la partida en un videojuego.

    git push origin nombre-de-la-rama: Sube tus cambios desde tu PC a la nube de GitHub.

3. El Flujo GitFlow (La lógica que pide el profe)

Para que no se te olvide el orden de los Pull Requests en la web de GitHub:

    Feature → Develop: Para probar que el código/linter está bien.

    Develop → Main: Para dejar el trabajo listo para la entrega final.

4. Limpieza y Actualización

    git pull origin main: Si hiciste cambios en la web (como un Merge) y quieres que aparezcan en tu VS Code, usa esto para bajar la información.