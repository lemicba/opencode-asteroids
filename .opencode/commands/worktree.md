---
description: Crea un git worktree en .worktrees/<nombre> a partir del argumento
agent: build
---

Creá un git worktree siguiendo estas reglas EXACTAS:

1. El input del usuario es: $ARGUMENTS
2. Analizá ese input (puede tener espacios) y derivá un nombre de worktree en kebab-case: minúsculas, espacios → guiones, sin caracteres especiales.
3. Ejecutá ÚNICAMENTE: git worktree add .worktrees/<nombre-del-worktree>
4. NO hagas nada más: no cambies de directorio, no corras otros comandos, no agregues commits, no toques archivos.
5. Reporta unicamente el resultado del comando (stdout/stderr y codigo de salida).
6. Si los argumentos es muy largo simplificalo.

El comando debe correrse desde la raíz del proyecto actual.
