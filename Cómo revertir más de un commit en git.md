---
Fecha: 2024-04-01
tags:
  - til
  - git
share: "true"
---
# Cómo revertir más de un commit en git 

## Problema

Quiero revertir los últimos N commits de mi proyecto y no quiero revertirlos uno por uno.

## Solución

git revert admite una flag --no-comit, lo que nos permite utilizar el comando revert con más de un commit (en este ejemplo, 3 commits):

```bash
git revert --no-commit HEAD~3..HEAD
```

Esto va a revertir el estado del repositorio al estado deseado sin crear ni destruir commits, por lo que para concluir el revert es necesario crear un commit nuevo:

```bash
git commit -m "Revert last 3 commits"
```