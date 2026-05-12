# Ejercicio 4: Rebase

## 🎯 Objetivo
Entender la diferencia entre merge y rebase, y saber cuándo usar cada uno.

---

## ¿Qué es rebase?
Mientras que **merge** une dos ramas creando un commit de fusión, **rebase** "reescribe" tu rama como si hubiera partido del estado más reciente de `main`. El resultado es un historial más limpio y lineal.

```
ANTES del rebase:        DESPUÉS del rebase:
main:    A - B - C       main:    A - B - C
                 \                         \
mi-rama: A - B - X       mi-rama:           X'
```

---

## Pasos

### 1. Actualiza `main` con un nuevo commit
Edita `docs/notas.md` y añade una línea:
```
## Actualización importante
- Se añadió la función dividir
```
Commit: `docs: registrar nueva función en notas`

### 2. Crea una rama antes de ese commit (simula trabajo en paralelo)
```bash
git checkout -b feature/nueva-funcion HEAD~1
```
> `HEAD~1` significa "un commit atrás"

### 3. Haz un cambio en la rama
Añade en `src/utils.js`:
```javascript
function potencia(base, exponente) {
  return Math.pow(base, exponente);
}
```
Commit: `feat: añadir función potencia`

### 4. Haz el rebase sobre main
```bash
git rebase main
```

### 5. Comprueba el historial
```bash
git log --oneline
```
Tu commit de `potencia` aparecerá DESPUÉS del commit de `docs/notas`, como si hubiera partido de ahí.

---

## 🆚 Merge vs Rebase

| | Merge | Rebase |
|--|-------|--------|
| Historial | Con ramificaciones | Lineal y limpio |
| Uso ideal | Ramas públicas / Pull Requests | Ramas personales antes de subir |
| Riesgo | Bajo | No hacer en ramas compartidas |

> ⚠️ **Regla de oro**: nunca hagas rebase de una rama que ya han descargado tus compañeros.
