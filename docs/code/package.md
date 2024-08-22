---
title: package.json
description: 'Arquivo de configuração do projeto que define dependências, scripts e metadados.'
---

# package.json

O arquivo `package.json` é um componente essencial de qualquer projeto Node.js, servindo como um manifesto que contém informações sobre o projeto, suas dependências e scripts de execução.

## Estrutura do arquivo

```json
{
  "name": "simple-todo-list",
  "author": "guiliznas",
  "private": false,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "test": "echo 1"
  },
  "dependencies": {
    "vue": "^3.2.47"
  },
  "devDependencies": {
    "@vitejs/plugin-vue": "^4.1.0",
    "vite": "^4.2.0"
  }
}
```

## Campos principais

- **name**: O nome do projeto. Neste caso, é `simple-todo-list`.
- **author**: O autor do projeto, que é `guiliznas`.
- **private**: Indica se o projeto é privado. Um valor `false` permite que o projeto seja publicado no npm.
- **version**: A versão atual do projeto, que é `0.0.0`.
- **type**: Define o tipo de módulo. Aqui, está configurado como `module`, indicando que o projeto utiliza módulos ES.
  
## Scripts

Os scripts definidos no `package.json` permitem executar tarefas comuns:

- **dev**: Inicia o servidor de desenvolvimento usando o Vite.
- **build**: Compila o projeto para produção.
- **preview**: Exibe uma prévia da versão de produção.
- **test**: Executa um comando de teste simples que, neste caso, apenas ecoa `1`.

## Dependências

- **dependencies**: Lista as dependências necessárias para o funcionamento do projeto. Aqui, a única dependência é o Vue.js na versão `^3.2.47`.
- **devDependencies**: Lista as dependências necessárias apenas para o desenvolvimento. Inclui:
  - `@vitejs/plugin-vue`: Plugin para integrar Vue com Vite.
  - `vite`: Ferramenta de construção e desenvolvimento.

Este arquivo é fundamental para gerenciar o ciclo de vida do projeto e suas dependências, facilitando a colaboração e a manutenção do código.