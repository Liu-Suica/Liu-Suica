# Guía de tu README neón 💙

## ¿Qué es cada cosa?

```
Liu-Suica/                      ← tu repo especial (se llama igual que tu usuario)
├── README.md                   ← lo que GitHub muestra en tu perfil
├── GUIA.md                     ← esta guía (puedes borrarla del repo si quieres)
├── assets/                     ← las imágenes que usa el README
│   ├── banner.svg              ← portada: ventana de vim con VISUAL.MAP (puntos) + profile.yml
│   ├── whoami.svg              ← tarjeta "whoami" con el sol neón animado
│   ├── radar-habilidades.svg   ← gráfico de araña de habilidades (lo crea el script)
│   └── radar-lenguajes.svg     ← gráfico de araña de lenguajes (lo crea el script)
└── scripts/
    ├── generar_banner.py       ← programa que dibuja el banner (y convierte tu foto en puntos)
    └── generar_radares.py      ← programa que dibuja los dos radares
```

**¿Por qué SVG y no PNG?** Un SVG es una imagen escrita como código (parecido a HTML). Por eso puede tener animaciones (las estrellas que parpadean, el cursor `▌`) y se ve nítida en cualquier tamaño. Puedes abrir cualquier `.svg` en VS Code y leerlo.

**Lo que NO está en la carpeta** viene de servicios externos por URL dentro del README:

| Parte del README | Servicio | Qué hace |
|---|---|---|
| Texto que se escribe solo | readme-typing-svg | Anima las frases (`lines=...` en la URL) |
| Contador de visitas | komarev | Cuenta quién visita tu perfil |
| Íconos del stack | skillicons.dev y simpleicons | Dibujan los logos (`i=html,css,...`) |
| Racha | streak-stats | Muestra tus días seguidos haciendo commits |
| Botones de redes | shields.io | Los badges de Gmail, LinkedIn, etc. |

## Cómo subirlo a tu perfil

Ya tienes el repo `Liu-Suica/Liu-Suica`, así que solo reemplazas su contenido:

1. Entra a `github.com/Liu-Suica/Liu-Suica`.
2. **Add file → Upload files** y arrastra `README.md`, `GUIA.md` y las carpetas `assets` y `scripts`.
3. Escribe un mensaje como `README neón 💙` y dale **Commit changes**.
4. Abre `github.com/Liu-Suica` y listo ✨

Con Git desde la terminal sería:

```bash
git clone https://github.com/Liu-Suica/Liu-Suica.git
cd Liu-Suica
# copia aquí los archivos nuevos (reemplaza el README viejo)
git add .
git commit -m "README neón"
git push
```

## Cómo personalizarlo

- **Poner TU foto en el mapa de puntos (como el de macu-dev):**
  1. Instala Pillow una sola vez: `pip install pillow`
  2. Pon tu foto en la carpeta del repo (cara bien iluminada y fondo OSCURO: lo claro se vuelve puntos y lo oscuro queda vacío. Si tu fondo es claro, píntalo de negro con cualquier editor).
  3. Corre `python scripts/generar_banner.py mi_foto.jpg`
  4. Abre `assets/banner.svg` en el navegador para verlo y luego haz commit + push.
- **Cambiar los datos del profile.yml:** edita la lista `YAML` al inicio de `scripts/generar_banner.py` y vuelve a correrlo.

- **Cambiar tus niveles en los radares:** abre `scripts/generar_radares.py`, cambia los números (0 a 100) y corre `python scripts/generar_radares.py`. Luego commit + push.
- **Cambiar las frases animadas:** en el README busca `lines=` y edita el texto. Los espacios van como `+` y cada frase se separa con `;`.
- **Agregar un ícono al stack:** añade su nombre a `icons?i=...` (la lista está en skillicons.dev).
- **Cambiar un dato de la terminal:** abre `assets/whoami.svg` y busca la frase que quieres cambiar y edita el texto que está dentro de su etiqueta `<text>`.
- **Cambiar el color neón:** busca `00d4ff` en los archivos y reemplázalo por otro color hex.

## Ejercicios para practicar 🎯

1. Agrega una línea 18 al `profile.yml` (por ejemplo `languages: Español · English`) y regenera el banner.
2. Agrega un sexto eje al radar de lenguajes (por ejemplo `"TypeScript": 60`): verás que el pentágono se vuelve hexágono solo.
3. En `whoami.svg`, agrega una carpeta nueva en `ls expertise/` (por ejemplo `design/  Figma · UI/UX`).
4. Cambia la velocidad de las olas del sol: busca `dur="6s"` en `whoami.svg` y prueba con `3s`.
