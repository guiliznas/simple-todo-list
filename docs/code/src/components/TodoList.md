---
title: TodoList
description: 'Componente Vue para gerenciar uma lista de tarefas simples com suporte a múltiplas categorias.'
---

# TodoList

O componente `TodoList` é uma aplicação Vue que permite aos usuários gerenciar uma lista de tarefas simples, categorizadas em "Trabalho" e "Casa". Ele inclui um relógio digital e armazena as tarefas no `localStorage` do navegador.

## Estrutura do Componente

### Template

O template do componente é composto por:

- Um cabeçalho com um ícone e título.
- Um relógio digital.
- Botões para alternar entre as categorias "Trabalho" e "Casa".
- Uma lista de tarefas que permite a edição e remoção de itens.

### Script

O script do componente define:

- **Componentes Importados**: Importa o componente `DigitalClock`.
- **Data**: Contém o estado do componente, incluindo a aba ativa e as tarefas para cada categoria.
- **Computed Properties**: `getActiveTabItems` retorna as tarefas da aba atualmente ativa.
- **Watchers**: Observa mudanças nas tarefas e as salva no `localStorage`.
- **Lifecycle Hooks**: No `mounted`, recupera as tarefas do `localStorage`.
- **Methods**:
  - `changeTab(tabName)`: Altera a aba ativa.
  - `clearItem(item)`: Limpa o valor de uma tarefa.

### Estilos

Os estilos são definidos para:

- Layout do contêiner e botões.
- Estilização dos campos de entrada e botões de exclusão.
- Comportamento responsivo para dispositivos móveis.

## Funcionalidades

- **Troca de Abas**: O usuário pode alternar entre as listas de tarefas de "Trabalho" e "Casa".
- **Persistência de Dados**: As tarefas são salvas no `localStorage`, permitindo que as informações sejam mantidas entre as sessões do navegador.
- **Interatividade**: Os usuários podem adicionar, editar e remover tarefas de forma intuitiva.

## Uso

Para utilizar o componente `TodoList`, importe-o em seu aplicativo Vue e adicione-o ao template desejado:

```vue
<template>
  <TodoList />
</template>

<script>
import TodoList from './components/TodoList.vue';

export default {
  components: {
    TodoList,
  },
};
</script>
```

## Conclusão

O componente `TodoList` é uma solução simples e eficaz para gerenciar tarefas, com uma interface amigável e funcionalidades que garantem uma boa experiência ao usuário.