---
Fecha: 2024-02-29
tags:
  - til
  - dotfiles
share: "true"
---
# Cómo conseguir una terminal minimalista

## Problema

No utilizo los botones de maximizar/minimizar/cerrar de mi terminal `kitty`.

## Solución

Para ocultar la barra del título de una terminal `kitty`, se necesita modificar el archivo su archivo de configuración (normalmente ubicado en `~/.config/kitty/kitty.conf`) y agregar la siguiente línea:

```
hide_window_decorations titlebar-and-corners
```

Tener en cuenta que si se suelen utilizar aplicaciones de pantalla completa en la terminal (como tmux o vim) puede quedar un margen incomodo en la parte de arriba.

Para nivelar el margen, agregar la siguiente linea al archivo kitty.conf:

```
window_margin_width 2 
```
