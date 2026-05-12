# Ejercicio 2: Crear y gestionar ramas

## 🎯 Objetivo
Aprender a crear ramas para trabajar en funcionalidades nuevas sin afectar la rama principal.

---

## ¿Qué es una rama?
Una rama es como una copia paralela del proyecto donde puedes experimentar sin miedo a romper nada en `main`.

---

## Pasos

### 1. Crea una rama nueva
En GitHub Desktop: **Branch → New Branch**
Nómbrala: `feature/funcion-dividir`

O en terminal:
```bash
git checkout -b feature/funcion-dividir
```

### 2. Haz cambios en la rama
Abre `src/utils.js` y añade:

```javascript
function dividir(a, b) {
  if (b === 0) return "Error: no se puede dividir por cero";
  return a / b;
}
```

### 3. Haz commit en la rama
Mensaje sugerido: `feat: añadir función dividir con validación`

### 4. Vuelve a main sin los cambios
```bash
git checkout main
```
Abre `utils.js` — ¡la función dividir ha desaparecido! Eso es porque está en la otra rama.

### 5. Vuelve a tu rama
```bash
git checkout feature/funcion-dividir
```
La función vuelve a aparecer. ✨

---

## 🔁 Practica más
Crea otra rama llamada `docs/actualizar-notas` y edita el archivo `docs/notas.md` marcando como completada la tarea de dividir.

---

## ✅ Ver todas tus ramas
```bash
git branch
```
La rama activa aparece con un `*`.
