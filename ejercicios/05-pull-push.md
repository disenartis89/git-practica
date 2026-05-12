# Ejercicio 5: Pull y Push

## 🎯 Objetivo
Aprender a sincronizar tu trabajo local con el repositorio remoto en GitHub.

---

## Conceptos clave

| Término | Significado |
|---------|-------------|
| **local** | Tu ordenador |
| **remoto (origin)** | El repositorio en GitHub |
| **push** | Subir tus commits al remoto |
| **pull** | Bajar los commits del remoto a tu ordenador |
| **fetch** | Comprobar si hay cambios sin descargarlos |

---

## Ejercicio A: Push (subir cambios)

### 1. Haz algún cambio y commítalo
Por ejemplo, añade un comentario en `src/app.js`:
```javascript
// Versión 1.1 - actualizado
```
Commit: `chore: actualizar comentario de versión`

### 2. Súbelo a GitHub
```bash
git push origin main
```
En GitHub Desktop: botón **Push origin**

### 3. Comprueba en GitHub
Ve a tu repositorio en github.com y verás el commit recién subido.

---

## Ejercicio B: Pull (bajar cambios)

Simula que un compañero hizo cambios:

### 1. Edita un archivo DIRECTAMENTE en GitHub
- Ve a tu repo en github.com
- Abre `docs/notas.md`
- Haz clic en el ✏️ (editar)
- Añade una línea y haz commit desde la web

### 2. Baja los cambios a tu ordenador
```bash
git pull origin main
```
En GitHub Desktop: **Fetch origin** → **Pull origin**

### 3. Comprueba el archivo
Abre `docs/notas.md` — los cambios que hiciste en GitHub ya están en tu ordenador.

---

## Ejercicio C: Pull con conflicto

### 1. Edita `src/app.js` en GitHub (web) y haz commit
### 2. SIN hacer pull, edita la misma línea en tu ordenador y haz commit
### 3. Intenta hacer push:
```bash
git push origin main
# ❌ ERROR: el remoto tiene cambios que no tienes en local
```

### 4. Solución:
```bash
git pull origin main   # baja los cambios y hace merge automático
git push origin main   # ahora sí puedes subir
```

---

## 💡 Flujo recomendado al empezar a trabajar cada día
```bash
git pull origin main       # 1. Primero baja lo nuevo
# ... haces tus cambios ...
git add .
git commit -m "feat: ..."  # 2. Commiteas
git push origin main       # 3. Subes
```
