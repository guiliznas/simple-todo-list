---
title: App.vue
description: 'Componente principal da aplicação que integra a lista de tarefas.'
---

# App.vue

O arquivo `App.vue` é o componente principal da aplicação, responsável por renderizar a interface do usuário. Ele utiliza o componente `TodoList` para exibir uma lista de tarefas.

## Estrutura do Componente

### Script

```vue
<script setup>
import TodoList from './components/TodoList.vue'
</script>
```

- O bloco `<script setup>` é utilizado para definir a lógica do componente de forma simplificada.
- O componente `TodoList` é importado para ser utilizado no template.

### Template

```vue
<template>
  <div class="full-center">
    <todo-list />
  </div>
</template>
```

- O bloco `<template>` define a estrutura visual do componente.
- O componente `TodoList` é renderizado dentro de um `div` que centraliza seu conteúdo.

### Estilos

```vue
<style>
:root {
  --primary: #2B5270;
}
.full-center {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
```

- O bloco `<style>` contém as definições de estilo para o componente.
- A variável CSS `--primary` é definida para ser utilizada em outros estilos.
- A classe `.full-center` utiliza Flexbox para centralizar o conteúdo tanto vertical quanto horizontalmente.

## Considerações

Este componente serve como a base da aplicação, permitindo a inclusão de outros componentes e funcionalidades conforme necessário. A centralização do `TodoList` proporciona uma interface limpa e organizada para o usuário.