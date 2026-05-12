# Ejercicio 1: Commits básicos

## 🎯 Objetivo
Aprender a registrar cambios en el repositorio con buenos mensajes de commit.

---

## Pasos

### 1. Haz un cambio en `src/app.js`
Abre el archivo y añade esta función al final:

```javascript
function calcularEdad(anioNacimiento) {
  return new Date().getFullYear() - anioNacimiento;
}
```

### 2. Guarda el archivo y ve a GitHub Desktop
Verás el cambio marcado en el panel izquierdo.

### 3. Escribe un mensaje de commit descriptivo
En el campo **Summary** escribe:
```
feat: añadir función calcularEdad
```

> 💡 Buenas prácticas para mensajes de commit:
> - Usa prefijos: `feat:` (nueva función), `fix:` (corrección), `docs:` (documentación)
> - Sé breve pero descriptivo
> - Usa el imperativo: "añadir" en vez de "añadí"

### 4. Haz clic en **Commit to main**

---

## 🔁 Practica más
Repite el proceso añadiendo una función nueva en `src/utils.js`:

```javascript
function multiplicar(a, b) {
  return a * b;
}
```

Commit sugerido: `feat: añadir función multiplicar en utils`

---

## ✅ ¿Lo conseguiste?
Ejecuta en terminal para ver tu historial:
```bash
git log --oneline
```
Deberías ver tus commits listados.
