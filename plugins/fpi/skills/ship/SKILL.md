---
description: Arregla-hasta-verde el repo actual. Detecta el stack, corre tests + typecheck + lint + build, arregla fallos en loop, y se detiene en un resumen del diff y un mensaje de commit para tu revisión. No hace commit, push ni deploy.
argument-hint: [opcional: ruta o área a enfocar]
allowed-tools: Read, Write, Edit, Bash, Glob, Grep
disable-model-invocation: true
model: Sonnet 4.6
---

# Chequeo de ship

## Detectar el stack
!`ls package.json pnpm-lock.yaml yarn.lock package-lock.json pyproject.toml requirements.txt 2>/dev/null`

Usa lo que esté presente para elegir los comandos correctos (p. ej. pnpm/npm/yarn en un repo Next.js + TypeScript: los scripts de test, typecheck, lint y build del package.json; pytest/ruff en Python).

## Qué hacer
Área a enfocar (opcional): $ARGUMENTS

Corre los chequeos del proyecto y llévalos todos a verde, en loop:
1. Corre los tests. Si alguno falla, lee el fallo real, arréglalo, vuelve a correr.
2. Corre el chequeo de tipos (p. ej. tsc --noEmit). Arregla los errores de tipo.
3. Corre el linter. Arregla los errores de lint (usa el autofix primero si existe).
4. Corre el build. Arregla los errores de build.

Repite hasta que cada chequeo pase. **Tope de 8 ciclos.** Si el mismo fallo se repite dos veces, detente y muéstrame el error y tu diagnóstico en vez de adivinar otra vez.

## Frenos
- **No** hagas commit, push, deploy ni migraciones. Detente antes de cualquiera de esas.
- Toca solo los archivos necesarios para que los chequeos pasen. Si un arreglo requiere un cambio más grande o una decisión, detente y pregúntame.

## Cuando esté verde (o tope)
1. Muestra `git status` y un `git diff --stat` corto.
2. Resume qué cambiaste y por qué, en 2–4 viñetas.
3. Propón un único mensaje de commit estilo Conventional Commits para que yo lo use. **No** agregues ningún trailer `Co-Authored-By` ni `Generated-with` — yo firmo mis propios commits.
4. Dime el comando para hacer el commit yo mismo.
