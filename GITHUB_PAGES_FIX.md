# Solución para Error 404 en GitHub Pages

## Problema
El sitio muestra 404 en GitHub Pages.

## Soluciones

### 1. Verificar Configuración de GitHub Pages

Ve a: https://github.com/Rolf-droid/andino/settings/pages

**Configuración correcta:**
- **Source**: Deploy from a branch
- **Branch**: `main`
- **Folder**: `/` (root) - **IMPORTANTE: Debe ser root, NO una subcarpeta**
- Haz clic en **Save**

### 2. Verificar que el Repositorio sea Público

GitHub Pages gratuito requiere que el repositorio sea **público**.

1. Ve a: https://github.com/Rolf-droid/andino/settings
2. Desplázate hasta "Danger Zone"
3. Si el repositorio es privado, cámbialo a público

### 3. Esperar a que se Despliegue

Después de configurar GitHub Pages:
- Espera 1-5 minutos
- Refresca la página: https://rolf-droid.github.io/andino/
- Si aún no funciona, espera hasta 10 minutos

### 4. Verificar la URL Correcta

La URL debe ser exactamente:
```
https://rolf-droid.github.io/andino/
```

**NO** debe ser:
- `https://rolf-droid.github.io/andino/index.html` (aunque esto también debería funcionar)
- `https://github.com/Rolf-droid/andino` (esta es la página del repositorio, no el sitio)

### 5. Verificar que index.html esté en la Raíz

El archivo `index.html` debe estar en la raíz del repositorio, no en una subcarpeta.

Estructura correcta:
```
andino/
├── index.html  ← Debe estar aquí
├── css/
├── img/
└── ...
```

### 6. Verificar el Estado del Despliegue

1. Ve a: https://github.com/Rolf-droid/andino/actions
2. Busca workflows de "pages build and deployment"
3. Verifica que no haya errores

### 7. Si Nada Funciona - Usar Netlify (Alternativa)

Si GitHub Pages sigue dando problemas:

1. Ve a: https://app.netlify.com
2. Inicia sesión con GitHub
3. "Add new site" → "Import an existing project"
4. Selecciona el repositorio `andino`
5. **Build command**: (dejar vacío)
6. **Publish directory**: `/` (root)
7. Deploy

Netlify te dará una URL como: `https://random-name.netlify.app`

## Verificación Rápida

Ejecuta estos comandos para verificar:

```bash
cd "/Volumes/rolando - Datos/Proyecto Brandon/elearning-1.0.0"
git status
git log --oneline -1
```

Si todo está bien, el problema es solo de configuración en GitHub.




