# Ejercicio 6: Pull Requests y Revisión de Código

## 🎯 Objetivo
Aprender a proponer cambios mediante Pull Requests y revisar el trabajo de compañeros.

---

## ¿Qué es un Pull Request (PR)?
Es una solicitud para fusionar tu rama con `main`. Permite que tus compañeros **revisen tu código** antes de integrarlo. Es la forma estándar de colaborar en equipo.

---

## Parte 1: Crear un Pull Request

### 1. Crea una rama nueva con una funcionalidad
```bash
git checkout -b feature/funcion-saludo-personalizado
```

### 2. Añade una función nueva en `src/app.js`
```javascript
function saludoPersonalizado(nombre, idioma) {
  const saludos = {
    es: `¡Hola, ${nombre}!`,
    en: `Hello, ${nombre}!`,
    fr: `Bonjour, ${nombre}!`
  };
  return saludos[idioma] || saludos.es;
}
```

### 3. Haz commit y push de la rama
```bash
git add .
git commit -m "feat: añadir saludo personalizado por idioma"
git push origin feature/funcion-saludo-personalizado
```

### 4. Abre el Pull Request en GitHub
- Ve a tu repositorio en github.com
- Verás un banner amarillo con **"Compare & pull request"** — haz clic
- Rellena:
  - **Título**: `feat: añadir saludo personalizado por idioma`
  - **Descripción**: Explica qué hace el cambio y por qué
- Haz clic en **Create pull request**

---

## Parte 2: Revisar un Pull Request (como compañero)

Cuando un compañero/a te pida revisar su PR:

### 1. Ve a la pestaña **Pull Requests** del repositorio
### 2. Abre el PR a revisar
### 3. Haz clic en **Files changed**
   Verás las líneas en verde (añadidas) y rojo (eliminadas)

### 4. Deja comentarios
- Pasa el ratón por una línea → aparece un `+` azul
- Haz clic y escribe tu comentario
- Tipos de revisión:
  - **Comment**: solo un comentario sin aprobación
  - **Approve**: apruebas el cambio ✅
  - **Request changes**: pides modificaciones antes de fusionar ❌

### 5. El autor responde y actualiza si es necesario
Simplemente hace más commits en la misma rama — el PR se actualiza automáticamente.

---

## Parte 3: Fusionar el Pull Request

Una vez aprobado:

### Opción A: desde GitHub web
- Haz clic en **Merge pull request** → **Confirm merge**
- Luego **Delete branch** para limpiar

### Opción B: desde terminal
```bash
git checkout main
git merge feature/funcion-saludo-personalizado
git push origin main
git branch -d feature/funcion-saludo-personalizado
```

---

## 🔄 Flujo completo en equipo

```
1. main (estable)
2. Creas rama feature/xxx
3. Trabajas y haces commits
4. Push de la rama
5. Abres Pull Request
6. Compañero/a revisa y aprueba
7. Se fusiona en main
8. Se borra la rama
9. Todos hacen pull de main
```

---

## 💡 Buenas prácticas en PRs
- Los PRs deben ser **pequeños y enfocados** (mejor varios pequeños que uno enorme)
- Escribe una descripción clara de **qué** cambia y **por qué**
- Responde siempre a los comentarios de revisión
- No apruebes tu propio PR si trabajas en equipo
