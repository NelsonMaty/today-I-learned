---
Fecha: 2024-03-03
tags:
  - til
  - "#terminal"
  - "#AI"
share: "true"
---
# Cómo generar un mensaje de commit automáticamente usando IA 

## Problema

Muchas veces es tedioso explicar en un texto corto los cambios realizados.

## Solución

Utilizar chatgpt para sugerir los mensajes de commit.

- Paso 1: Generar una API KEY en openai.com
- Paso 2: Instalar shellgpt y configurar la api key generada
- Paso 3: Realizar cambios en nuestro repo y agregarlos a staged
- Paso 4: Correr el commando `git diff | sgpt "Generate commit message, for my changes, be clear and informative, in 80 characters or less, start with a verb"`

Listo! Con esto tendremos un mensaje conciso y explicativo de nuestros cambios.

Luego se puede hacer que siempre que se realice un commit se genere automaticamente, agregamos lo siguiente a nuestra configuracion de shell (en mi caso, `.zshrc`)

```bash
# shell gpt utilities
generate_commit_message() {
  git_diff=$(git diff --staged)
  if [[ -n $git_diff ]]; then
    sgpt_message=$(echo "$git_diff" | sgpt "Generate commit message, for my changes, be clear and informative, in 80 characters or less, start with a verb")
    echo "- $sgpt_message" 
    echo "🙂 Is it OK? [Y/n]"
    read REPLY
    if [[ $REPLY =~ ^[Nn]$ ]]; then
      echo "🙅 Operation cancelled"
    else
      git commit -m "$sgpt_message"
      echo "👍 Commit done"
    fi
  else
    echo "😓 There are no staged changes"
  fi
}

alias gc=generate_commit_message

```

Con esto, cada vez que quiero commietear cambios sólo debo correr el comando `gc` y confirmar el mensaje de commit si me parece pertinente.