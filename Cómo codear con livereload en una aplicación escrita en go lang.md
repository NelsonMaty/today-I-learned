---
Fecha: 2024-03-02
tags:
  - til
  - "#programming"
  - "#golang"
share: "true"
---
# Cómo codear con livereload en una aplicación escrita en go lang 

## Problema

Cada vez que actualizo un archivo `.go` necesito volver a compilar y correr la aplicación en la terminal, haciendo el proceso tedioso.

## Solución

Utilizar la herramienta `air` para que cada vez que se actualice un archivo en el proyecto, se vuelva a correr automáticamente en la terminal la aplicación en desarrollo.

Paso 1, instalar la utilidad:

```bash
go get -u github.com/cosmtrek/air
```

Paso 2, correr la aplicación ejecutando el comando:

```bash
air
```

Listo! Air quedará corriendo en segundo plano, volviendo a correr la aplicación cuando efectuemos cambios en cualquier archivo go del proyecto.