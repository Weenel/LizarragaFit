# Lizarraga Fit

Sitio de una sola página para Lizarraga Fit, entrenador personal certificado IIAFF.
HTML, CSS y JavaScript sin dependencias ni proceso de compilación: se sube tal cual.

## Estructura

```
lizarraga-fit/
├── index.html      todo el sitio: marcado, estilos y scripts
├── .nojekyll       evita que GitHub Pages ignore archivos al publicar
├── README.md
└── images/         10 fotografías optimizadas en WebP (420 KB en total)
    ├── hero.webp
    ├── about.webp
    ├── method1.webp  method2.webp  method3.webp  method4.webp
    ├── bento1.webp
    └── avatar1.webp  avatar2.webp  avatar3.webp
```

Las únicas peticiones externas son las tipografías Archivo y Newsreader desde Google Fonts.

## Publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub, por ejemplo `lizarraga-fit`.
2. Sube el contenido de esta carpeta a la raíz del repositorio. `index.html` debe quedar en la raíz, no dentro de otra carpeta.

   Desde la terminal:

   ```bash
   cd lizarraga-fit
   git init
   git add .
   git commit -m "Primera versión del sitio"
   git branch -M main
   git remote add origin https://github.com/TU-USUARIO/lizarraga-fit.git
   git push -u origin main
   ```

   Desde el navegador: en el repositorio vacío, usa «uploading an existing file» y arrastra `index.html`, `README.md` y la carpeta `images`. El archivo `.nojekyll` empieza con punto y el navegador puede ocultarlo; créalo después con «Add file → Create new file», escribe `.nojekyll` como nombre y déjalo vacío.

3. Entra en **Settings → Pages**. En «Source» elige **Deploy from a branch**, rama `main` y carpeta `/ (root)`. Guarda.
4. En un par de minutos el sitio queda en `https://TU-USUARIO.github.io/lizarraga-fit/`.

## Dominio propio

En **Settings → Pages → Custom domain** escribe el dominio y guarda: GitHub creará un archivo `CNAME`. En tu proveedor de dominio apunta un registro `CNAME` de `www` a `TU-USUARIO.github.io`, o cuatro registros `A` del dominio raíz a `185.199.108.153`, `185.199.109.153`, `185.199.110.153` y `185.199.111.153`. Deja activada la casilla **Enforce HTTPS** cuando se habilite.

## Cambiar contenido

Todo el texto está en `index.html` y se puede editar directamente.

- **Correo de contacto:** busca `hola@lizarragafit.com`, aparece dos veces.
- **Precios y programas:** en la sección `<!-- PROGRAMAS -->`.
- **Testimonios:** en la sección `<!-- RESULTADOS -->`.

## Cambiar fotografías

Sustituye el archivo dentro de `images/` conservando el nombre. Si la nueva foto queda mal encuadrada, ajusta el `object-position` de esa etiqueta `<img>`: el primer valor mueve el recorte en horizontal y el segundo en vertical, donde `0%` es el borde superior y `100%` el inferior. Las fotos verticales de teléfono suelen necesitar un valor bajo para que no domine el techo.

Antes de subir una foto nueva conviene reducirla a un ancho de 600 a 900 píxeles y guardarla en WebP con calidad cercana a 70. Las actuales pesan entre 15 y 63 KB cada una.

## Accesibilidad y rendimiento

Navegable por teclado con foco visible, estados `aria-expanded` correctos en el acordeón de programas, textos alternativos en todas las imágenes y respeto a `prefers-reduced-motion`: quien tenga reducida la animación en su sistema ve el sitio completo sin movimiento.
