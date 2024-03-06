---
Fecha: 2024-03-05
tags:
  - til
  - terminal
share: "true"
---
# Cómo excluir un directorio en una búsqueda 

## Problema

Quiero buscar todos los archivos donde ocurra una búsqueda por 100 elementos como tamaño de página, pero al hacer un grep casi todos resultados son de archivos dentro de node_modules.

## Solución

Excluir el directorio node modules de la búsqueda. Para ello, el comando grep ofrece un parámetro `--exclude-dir`. En mi caso particular, quería excluir node_modules y la carpeta dist, quedando el comando:

```bash
grep -rl --exclude-dir={node_modules,dist} 'limit=100' .
```
