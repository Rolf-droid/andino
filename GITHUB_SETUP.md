# Solución de Autenticación GitHub

## Problema
Git está intentando usar credenciales de otro usuario (rolando35) pero el repositorio es de Rolf-droid.

## Soluciones

### Opción 1: Usar SSH (Recomendado)

1. **Generar clave SSH** (si no tienes una):
```bash
ssh-keygen -t ed25519 -C "tu-email@ejemplo.com"
```

2. **Agregar la clave a GitHub**:
   - Copia el contenido de: `~/.ssh/id_ed25519.pub`
   - Ve a GitHub → Settings → SSH and GPG keys → New SSH key
   - Pega la clave y guarda

3. **Cambiar la URL del remoto a SSH**:
```bash
cd "/Volumes/rolando - Datos/Proyecto Brandon/elearning-1.0.0"
git remote set-url origin git@github.com:Rolf-droid/andino.git
git push -u origin main
```

### Opción 2: Usar Personal Access Token

1. **Crear un token en GitHub**:
   - Ve a GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
   - Generate new token (classic)
   - Selecciona permisos: `repo` (todos)
   - Copia el token (solo se muestra una vez)

2. **Usar el token al hacer push**:
```bash
cd "/Volumes/rolando - Datos/Proyecto Brandon/elearning-1.0.0"
git push -u origin main
# Cuando pida usuario: Rolf-droid
# Cuando pida contraseña: pega el token (NO tu contraseña)
```

### Opción 3: Actualizar credenciales guardadas

**En macOS:**
```bash
# Eliminar credenciales guardadas
git credential-osxkeychain erase
host=github.com
protocol=https

# O usar GitHub CLI
gh auth login
```

**En Windows:**
- Ve a: Panel de Control → Credenciales de Windows
- Busca "github.com" y elimínalas
- Intenta hacer push de nuevo

## Después de autenticarte

Una vez que puedas hacer push, activa GitHub Pages:

1. Ve a: https://github.com/Rolf-droid/andino/settings/pages
2. En "Source", selecciona la rama **main**
3. En "Folder", selecciona **/** (root)
4. Haz clic en **Save**
5. Tu sitio estará en: `https://rolf-droid.github.io/andino/`




