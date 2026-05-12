# Ejercicio 3: Merge (fusionar ramas)

## 🎯 Objetivo
Aprender a fusionar el trabajo de una rama con la rama principal.

---

## ¿Qué es un merge?
Merge une los cambios de una rama con otra. Es el paso final después de terminar una funcionalidad.

---

## Pasos

### 1. Asegúrate de estar en `main`
```bash
git checkout main
git status
```

### 2. Fusiona la rama `feature/funcion-dividir`
```bash
git merge feature/funcion-dividir
```

En GitHub Desktop: **Branch → Merge into Current Branch** → selecciona `feature/funcion-dividir`

### 3. Comprueba el resultado
Abre `src/utils.js` — la función `dividir` ahora está en `main`. 🎉

### 4. Borra la rama (ya no la necesitas)
```bash
git branch -d feature/funcion-dividir
```

---

## ⚠️ Conflictos de merge

A veces dos personas editan la misma línea. Git no sabe cuál elegir y crea un **conflicto**.

**Simúlalo tú sola:**

1. En `main`, cambia la función `saludar` en `app.js`:
   ```javascript
   function saludar(nombre) {
     return `¡Buenas! Soy ${nombre}`;
   }
   ```
   Haz commit: `test: cambiar saludo en main`

2. Crea rama `feature/saludo-formal` y cambia la misma línea:
   ```javascript
   function saludar(nombre) {
     return `Buenos días, ${nombre}. ¿Cómo está usted?`;
   }
   ```
   Haz commit: `test: saludo formal`

3. Vuelve a `main` e intenta el merge:
   ```bash
   git merge feature/saludo-formal
   ```

4. Git te avisará del conflicto. En el archivo verás:
   ```
   <<<<<<< HEAD
     return `¡Buenas! Soy ${nombre}`;
   =======
     return `Buenos días, ${nombre}. ¿Cómo está usted?`;
   >>>>>>> feature/saludo-formal
   ```

5. Edita el archivo dejando solo la versión que quieras, guarda y haz commit.

---

## ✅ Comprueba el historial
```bash
git log --oneline --graph
```
Verás el punto donde se unieron las ramas.
