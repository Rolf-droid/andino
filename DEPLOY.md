# Guía de Despliegue - Colegio Andino

## Opción 1: GitHub Pages (Recomendado - Gratis)

### Paso 1: Crear repositorio en GitHub
1. Ve a [github.com](https://github.com) e inicia sesión
2. Haz clic en "New repository" (botón verde)
3. Nombre del repositorio: `colegio-andino-web` (o el que prefieras)
4. Marca como **Público** (necesario para GitHub Pages gratuito)
5. **NO** marques "Initialize with README" (ya tenemos archivos)
6. Haz clic en "Create repository"

### Paso 2: Conectar tu proyecto local con GitHub

```bash
cd "/Volumes/rolando - Datos/Proyecto Brandon/elearning-1.0.0"

# Agregar todos los archivos
git add .

# Hacer commit
git commit -m "Sitio web Colegio Andino completo"

# Cambiar nombre de rama a main (si es necesario)
git branch -M main

# Agregar el repositorio remoto (reemplaza TU_USUARIO con tu usuario de GitHub)
git remote add origin https://github.com/TU_USUARIO/colegio-andino-web.git

# Subir el código
git push -u origin main
```

### Paso 3: Activar GitHub Pages
1. En tu repositorio de GitHub, ve a **Settings** (Configuración)
2. En el menú lateral, busca **Pages**
3. En "Source", selecciona la rama **main**
4. Haz clic en **Save**
5. Tu sitio estará disponible en: `https://TU_USUARIO.github.io/colegio-andino-web/`

---

## Opción 2: Netlify (Muy Fácil - Gratis)

### Paso 1: Subir a GitHub primero
Sigue los pasos 1 y 2 de la Opción 1

### Paso 2: Conectar con Netlify
1. Ve a [netlify.com](https://netlify.com) e inicia sesión con GitHub
2. Haz clic en "Add new site" → "Import an existing project"
3. Selecciona tu repositorio de GitHub
4. Configuración:
   - **Build command**: (dejar vacío - no necesitas compilar)
   - **Publish directory**: `elearning-1.0.0` (o `.` si subiste solo la carpeta)
5. Haz clic en "Deploy site"
6. Tu sitio estará disponible en una URL como: `https://random-name-123.netlify.app`

**Ventaja**: Netlify te da una URL personalizada y puedes conectar un dominio propio fácilmente.

---

## Opción 3: Vercel (Gratis)

1. Ve a [vercel.com](https://vercel.com) e inicia sesión con GitHub
2. Haz clic en "Add New Project"
3. Selecciona tu repositorio
4. **Root Directory**: `elearning-1.0.0`
5. Haz clic en "Deploy"
6. Tu sitio estará disponible inmediatamente

---

## Notas Importantes

- **GitHub Pages**: Gratis, pero el repositorio debe ser público
- **Netlify**: Gratis, repositorio puede ser privado, mejor para dominios personalizados
- **Vercel**: Gratis, muy rápido, buena para proyectos pequeños

## Solución de Problemas

Si las fuentes no cargan:
- Verifica que las rutas en `css/gilroy-fonts.css` sean correctas
- Asegúrate de que todos los archivos de fuentes estén en el repositorio

Si los colores no se ven:
- Limpia la caché del navegador (Ctrl+Shift+R o Cmd+Shift+R)
- Verifica que `bootstrap.min.css` y `style.css` estén actualizados




