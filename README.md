# 🌐 Sitio oficial de International Technical Supply Ltda. (ITSL)

Este repositorio contiene el código fuente del sitio informativo **www.itsl.cl**, desplegado en **Netlify** con dominio gestionado en **Cloudflare + NIC Chile**.

---

## 🧩 Estructura del sitio

| Carpeta / Archivo | Descripción |
|--------------------|-------------|
| `/index.html` | Página principal (bilingüe ES/EN) |
| `/gracias.html` | Página de confirmación tras envío del formulario |
| `/assets/` | Imágenes y recursos (logos, banners, íconos) |
| `/_redirects` | Reglas de redirección para Netlify (incluye dominio y rutas amigables) |
| `/README.md` | Este documento (guía de mantenimiento) |

---

## 🚀 Flujo de publicación

1. **Desarrollo local (opcional):**
   - Editar HTML/CSS directamente o en VSCode.
   - Ver cambios en navegador local con extensión *Live Server* o similar.

2. **Commit y Push:**
   ```bash
   git add -A
   git commit -m "actualización contenido / estilo"
   git push
