---
Fecha: 2024-04-01
tags:
  - til
  - "#terminal"
share: "true"
---
# Cómo encontrar directorios pesados

## Problema

Estuve clonando repositorios y en un caso en particular se tardó demasiado en clonarse. Se descargaron varios MB de información (raro en proyectos chicos) y desconozco el motivo.

## Solución

Si bien se pueden usar las herramientas nativas de la terminal (por ej. df), hay alternativas cómodas y visuales para encontrar directorios innecesariamente pesados.

Comenzamos por instalar la herramienta `ncdu`

```bash
brew install ncdu
```

Y luego simplemente la ejecutamos en el directorio que sabemos que tiene este problema (o en nuestro home, si lo que queremos es limpiar nuestros documentos personales):

```bash
ncdu
```

De esta manera se muestra una interface que nos muestra visualmente todos los directorios y archivos, su peso, y una representacion visual de que tan pesado es el elemento respecto a sus pares.

Para navegar en ncdu utilzamos las teclas `j` o `Down Arrow` para bajar en la lista, `k` o `Up Arrow` para subir en la lista y `Enter` para entrar en un directorio. Para salir de un directorio, presionamos `Enter` en el elemento `..` de la lista.