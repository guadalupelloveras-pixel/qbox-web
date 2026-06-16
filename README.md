# qBox — Sitio web (landing)

Sitio **estático de un solo archivo**. `index.html` es completamente autónomo:
todo (HTML, CSS, JS, fuentes, logo, video del hero e imágenes) está embebido dentro
del propio archivo. **No requiere build, ni dependencias, ni servidor** — se abre solo.

## Contenido
- `index.html` — la página completa (~6 MB). Listo para servir tal cual.

## Objetivo
Publicarlo en **GitHub Pages** para obtener un link público y compartirlo con el cliente.

---

## Instrucciones para Claude Code

> El usuario quiere subir este sitio a GitHub y tener un enlace público para compartir.
> El sitio ya está terminado: **no hay que compilar ni modificar nada**, solo publicarlo.

### Opción A — GitHub Pages (recomendada, gratis)

1. Crear un repositorio nuevo (público) en la cuenta del usuario, p. ej. `qbox-web`.
2. Subir el contenido de esta carpeta a la raíz del repo (debe quedar `index.html` en la raíz):
   ```bash
   git init
   git add .
   git commit -m "qBox landing — sitio estático autónomo"
   git branch -M main
   git remote add origin https://github.com/<usuario>/qbox-web.git
   git push -u origin main
   ```
3. Activar GitHub Pages:
   - Repo → **Settings** → **Pages**
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` / carpeta `/ (root)` → **Save**
   - (Alternativa por CLI: `gh repo create`, luego habilitar Pages con la API/CLI.)
4. En 1–2 minutos el sitio queda disponible en:
   ```
   https://<usuario>.github.io/qbox-web/
   ```
   Ese es el link para compartir con el cliente.

### Opción B — Dominio propio
Si el usuario tiene el dominio `qboxmodular.com.ar`, se puede apuntar a GitHub Pages
agregando un archivo `CNAME` con el dominio y configurando los registros DNS
(A records de GitHub Pages o un CNAME hacia `<usuario>.github.io`).

---

## Notas importantes
- El archivo pesa ~6 MB porque trae el video y las imágenes embebidas; es normal y carga bien.
- Esta es **una sola página** (la home). El panel de administración y las páginas de
  categorías son archivos aparte del proyecto y **no** forman parte de este paquete.
- Los botones de **WhatsApp** (+54 9 264 443-1309) y de **agendar visita** funcionan en el sitio publicado.
- No editar `index.html` a mano: fue generado por un empaquetador. Para cambios de diseño,
  se regenera desde el proyecto original y se reemplaza el archivo.
