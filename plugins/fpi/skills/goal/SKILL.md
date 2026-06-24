---
description: Define un objetivo verificable y su condición de "hecho" para esta sesión, y lo guarda para que /loop trabaje hacia él. Úsalo al arrancar un bloque de trabajo enfocado.
argument-hint: [lo que quieres lograr]
allowed-tools: Read, Write, Edit, Bash(mkdir:*)
disable-model-invocation: true
model: Sonnet 4.6
---

# Fijar el objetivo

Objetivo del usuario: $ARGUMENTS

Conviértelo en una meta nítida y verificable, y guárdala.

1. Reformula el objetivo en una sola frase.
2. Define una **condición de hecho** *verificable*, no vaga: algo que un comando pueda confirmar. Bien: "npm test y npm run build pasan sin errores, y la ruta /api/cotizaciones devuelve 200 con un payload válido." Mal: "que funcione" o "mejorarlo".
3. Lista lo que queda **fuera de alcance**, para que el loop no se desvíe.
4. Anota las **acciones irreversibles** que la meta podría tocar (deploy a Vercel/Railway, git push, migración en prod, enviar mensajes, publicar) — necesitarán mi aprobación explícita después.
5. Guarda todo en `.claude/current-goal.md` (crea la carpeta `.claude` si no existe). Sobrescribe cualquier objetivo anterior.

Luego muéstrame el objetivo guardado y dime que corra `/loop` cuando esté listo.
