---
Fecha: 2024-03-04
tags:
  - til
share: "true"
---
# Cómo ir y volver de una rama rápidamente en git 

## Problema

Suelo saltar de la rama dev una rama de historia en desarrollo frecuentemente. Ir y volver entre ramas se hace muy verboso y algo tedioso.

## Solución

Utilizar el shorthand `-` para referirse a la rama previamente visitada. Por ejemplo, asumamos que estamos en la rama `mi-rama-donde-estoy-desarrollando-una-historia`.

```shell
> git branch --show-current
mi-rama-donde-estoy-desarrollando-una-historia
```

Luego visitamos la rama main:

```shell
git checkout main
```

Cómo hacer para volver a la rama que en la que estaba desarrollando? Puedo escribir `git checkout mi-rama-donde-estoy-desarrollando-una-historia`, pero es un comando extenso y puedo equivocarme con el nombre. La solución es correr:

```shell
git checkout -
```

Listo! Git recuerda cuál es la rama previamente visitada y nos lleva allí. Si quisiera retornar a la rama `main`, puedo tocar la flecha para arriba en mi terminal y volver a ejecutar el mismo comando para retornar a la rama anterior.