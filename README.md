# 🧮 Calculadora en Python — Práctica de Git Avanzado

Proyecto simple de calculadora con operaciones básicas, usado 
para practicar comandos avanzados de Git.

## ⚙️ Funcionalidades
- Sumar
- Restar
- Multiplicar

## 📝 Cómo ejecutar
```
python calculadora.py
```

---

## 📚 Teoría — Comandos que vas a usar

### git commit --amend
Modifica el ÚLTIMO commit que hiciste (cambia su mensaje y/o 
agrega archivos que olvidaste). No crea un commit nuevo, corrige 
el anterior.
```
git commit --amend -m "nuevo mensaje"
```

### git reset
Deshace commits. `HEAD~1` significa "un commit atrás del actual" 
(`HEAD~2` serían dos atrás, etc.)

Tiene 3 tipos:
- `--soft`: deshace el commit, pero tus cambios siguen listos 
  para volver a commitear
- `--mixed` (el que se usa si no escribes nada): deshace el 
  commit y el "add", los cambios quedan en tus archivos sin preparar
- `--hard`: borra TODO, incluso los cambios en tus archivos 
  (¡cuidado, esto no se puede deshacer!)

```
git reset --soft HEAD~1
```

---

## 🎯 Tu tarea

### Paso 1 — Configurar tu identidad
```
git config user.name "Tu Nombre"
git config user.email "tu-correo"
```

### Paso 2 — Explorar el historial
```
git log --oneline
```
Verás algo como:
```
a1b2c3d agrego cosas
cbf1618 arreglo
fd78525 agrego funcion
e6375a2 primer commit
```

### Paso 3 — Corregir el ÚLTIMO commit con amend
El mensaje "agrego cosas" no sigue el formato de conventional 
commits. Corrígelo:
```
git commit --amend -m "docs: agregar instrucciones del proyecto"
```
Verifica con `git log --oneline` — el mensaje del último commit 
ya cambió.

### Paso 4 — Practicar reset
Deshaz el commit que acabas de corregir, usando `--soft`:
```
git reset --soft HEAD~1
```
Ejecuta `git log --oneline` — notarás que ese commit YA NO 
aparece. Ejecuta `git status` — verás que los cambios siguen 
ahí, listos para commitear de nuevo:
```
git commit -m "docs: agregar instrucciones del proyecto"
```

### Paso 5 — Nuevos commits (conventional commits)
Agrega al menos 2 mejoras al proyecto. Escribe TÚ MISMO el 
mensaje, siguiendo el formato:
- `feat:` para funcionalidad nueva
- `docs:` para cambios en documentación
- `fix:` para corregir un error

### Paso 6 — Subir a tu repositorio
```
git push -u origin main
```
## Investigación adicional
El comando git reflog muestra el historial de movimientos y cambios que ha tenido HEAD en el repositorio. Permite consultar acciones anteriores como commits, resets y cambios de referencia, incluso cuando un commit ya no aparece en el historial normal.

## 🚀 Actividad — Versionado, Stash y Tag

### 📦 ¿Qué es git stash?

`git stash` permite guardar temporalmente los cambios que todavía no hemos hecho commit. Esto deja el proyecto limpio para poder realizar otra tarea sin perder nuestro trabajo.

Por ejemplo:

```bash
git stash
```

Para recuperar los cambios guardados:

```bash
git stash pop
```

También podemos consultar los stash que tenemos guardados:

```bash
git stash list
```

Si tenemos varios stash, podemos recuperar uno específico:

```bash
git stash apply "stash@{1}"
```

Para eliminar un stash específico:

```bash
git stash drop "stash@{1}"
```

Y para eliminar todos los stash:

```bash
git stash clear
```

### 🏷️ ¿Qué es git tag?

`git tag` permite colocar una etiqueta sobre un commit específico para identificar una versión importante del proyecto.

Por ejemplo:

```bash
git tag v1.0
```

Para ver las etiquetas existentes:

```bash
git tag
```

Y para subir las etiquetas a GitHub:

```bash
git push --tags
```

En este proyecto se creó la etiqueta `v1.0` para identificar la versión actual de la calculadora.

### 📌 Versionado semántico

El versionado semántico utiliza tres números:

**MAJOR.MINOR.PATCH**

* **MAJOR:** cambia cuando se realizan modificaciones grandes que pueden romper la compatibilidad con versiones anteriores. Ejemplo: `v1.0.0` → `v2.0.0`.
* **MINOR:** cambia cuando se agrega una nueva funcionalidad sin romper lo que ya funcionaba. Ejemplo: `v1.0.0` → `v1.1.0`.
* **PATCH:** cambia cuando se corrigen errores pequeños sin agregar cambios importantes. Ejemplo: `v1.1.0` → `v1.1.1`.

En este proyecto, `v1.0` representa una versión estable de la calculadora después de practicar y aplicar los comandos de versionado de Git.
## ✅ Entrega
Link de tu repositorio (fork) + pantallazo de "git log --oneline"
## Entrega


