---
description: Trabaja solo hacia el objetivo actual en ciclos verificar-actuar, con frenos duros, hasta cumplir la condición de hecho. Lee .claude/current-goal.md, o toma un objetivo en línea como argumento.
argument-hint: [objetivo en línea si no corriste /goal]
allowed-tools: Read, Write, Edit, Bash, Glob, Grep
disable-model-invocation: true
model: Sonnet 4.6
---

# Correr el loop

## El objetivo
Primero lee el objetivo. Si existe `.claude/current-goal.md`, úsalo:

!`cat .claude/current-goal.md 2>/dev/null || echo "SIN_OBJETIVO_GUARDADO"`

Si imprimió SIN_OBJETIVO_GUARDADO, el objetivo es lo que pasé en línea: $ARGUMENTS. Si ambos están vacíos, detente y pregúntame cuál es el objetivo — no adivines.

## Cómo trabajar
Avanza en ciclos hacia la condición de hecho. Cada ciclo:
1. Di el sub-objetivo actual en una línea corta.
2. Toma la siguiente acción concreta (leer, editar, correr un comando).
3. **Verifica** contra la condición de hecho — corre el test/build/chequeo real, no lo asumas.
4. Imprime una línea: `ciclo N — <qué hiciste> — <pasa/falla>`.

Repite hasta que la condición de hecho se cumpla **verificablemente**.

## Frenos (innegociables)
- **Tope:** detente tras 8 ciclos aunque no esté listo, salvo que te dé otro número en el argumento. Reporta hasta dónde llegaste.
- **No dar vueltas:** si el mismo error o chequeo falla dos veces seguidas, detente y muéstrame el error y tu diagnóstico en vez de intentar una tercera vez. Quemar ciclos contra la misma pared cuesta dinero.
- **El freno — acciones irreversibles:** nunca hagas ninguna de estas por tu cuenta. Detente, muéstrame exactamente qué vas a correr y espera mi sí: git push, cualquier deploy (Vercel/Railway/etc.), migraciones contra una base no-local o de producción, borrar archivos o datos, enviar cualquier email/mensaje, publicar algo, cambiar accesos o secretos. El trabajo local reversible (editar archivos, correr tests, commits locales) no necesita aprobación.
- **Conciencia de costo:** prefiere el camino más barato que igual verifique (corre solo el archivo de test relevante mientras iteras; la suite completa una sola vez al final).
- **Bitácora:** mantén la línea-por-ciclo para que yo pueda auditar la trayectoria después.

## Al salir
Resume: qué quedó hecho, si se cumplió la condición de hecho, qué falta (si algo), y el siguiente paso irreversible exacto (si lo hay) para que yo lo apruebe.
