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
   
3. **Deploy automático (Netlify)**

- El sitio se despliega desde la rama main.
- Verifica que Continuous Deployment esté ON (Site settings → Build & deploy → Continuous Deployment).

4. **Dominio**

- DNS administrado en Cloudflare.
- Certificados SSL gestionados automáticamente por Netlify.

## 💬 Formulario de contacto (Netlify Forms)

El formulario principal se encuentra en index.html y utiliza Netlify Forms sin backend.

<form name="contacto" method="POST" data-netlify="true" netlify-honeypot="bot-field" action="/gracias">
  <input type="hidden" name="form-name" value="contacto" />
  ...
</form>

## 🔑 Requisitos para que funcione correctamente

Form detection debe estar activado:
Settings → Build & deploy → Post processing → Forms → Enable form detection (ON)

Redirección 303 POST→GET definida en _redirects
Redeploy completo después de cambios

## 📍 Reglas relevantes en _redirects

/gracias   /gracias.html   303!
/thanks    /gracias.html   303!

`https://itsl.cl/*      https://www.itsl.cl/:splat  301!`

`http://itsl.cl/*       https://www.itsl.cl/:splat  301!`

`http://www.itsl.cl/*   https://www.itsl.cl/:splat  301!`

El código 303! convierte el POST en GET y evita el 404 tras el envío del formulario.

## 🌎 Idiomas

Selector ES/EN en la parte superior (#lang-toggle).

Script JS muestra/oculta bloques según el idioma y desactiva campos ocultos del formulario.

La preferencia del idioma se guarda en localStorage y se mantiene en /gracias.

## 🧰 Mantenimiento

| Tarea | Acción |
|--------------------|-------------|
| Cambios no visibles | Cloudflare → Caching → Purge Everything y recargar con Cmd+Shift+R |
| Form 404 después de enviar | Activar Form detection y redeploy |
| Auto deploy desactivado | Volver a activar en Build & deploy → Continuous Deployment |
| Página rota o sin traducción | Revisar bloques data-lang="es" / data-lang="en" |
| Nueva imagen | Guardar en /assets/ con nombre en minúsculas y sin espacios |

## 📱 Compatibilidad y diseño responsivo

Diseño adaptativo móvil / escritorio.

Se recomienda probar cada cambio en dispositivos iPhone y Android.

Usar imágenes comprimidas para mantener buena velocidad de carga.

## 🧠 Notas adicionales

- No eliminar los archivos _redirects ni gracias.html, ambos son esenciales.
- Los correos corporativos @itsl.cl están gestionados vía Google Workspace.
- Para soporte o recuperación del dominio, acceder a www.nic.cl
- El contenido es 100% estático (sin framework JS ni base de datos).

<p align="center"> <strong>© International Technical Supply Ltda. — Versión inicial del sitio 2025</strong><br/> <sub>Mantenimiento: Luis Cáceres / Rene Cáceres</sub> </p> ```
