---
title: simple-todo-list
description: 'Um projeto simples de lista de tarefas desenvolvido com Vue 3 e Vite.'
---

# Introdução

O **simple-todo-list** é um projeto que implementa uma lista de tarefas simples utilizando o framework Vue.js na versão 3, em conjunto com o Vite como ferramenta de construção. Este projeto serve como um ponto de partida para desenvolvedores que desejam aprender e experimentar com Vue 3 e suas funcionalidades.

## Visão Geral

Este projeto utiliza a abordagem de componentes do Vue para criar uma interface de usuário interativa e responsiva. A estrutura do projeto é organizada de forma a facilitar a manutenção e a escalabilidade, permitindo que novos recursos sejam adicionados com facilidade.

## Requisitos

Para rodar este projeto, você precisará ter instalado em sua máquina:

- Node.js (versão 14 ou superior)
- npm (gerenciador de pacotes do Node.js)

## Como Rodar o Projeto

1. Clone o repositório:
   ```bash
   git clone <URL_DO_REPOSITORIO>
   cd simple-todo-list
   ```

2. Instale as dependências:
   ```bash
   npm install
   ```

3. Inicie o servidor de desenvolvimento:
   ```bash
   npm run dev
   ```

4. Abra seu navegador e acesse `http://localhost:3000` para visualizar a aplicação.

## Estrutura de Pastas

- `src/`: Contém o código-fonte da aplicação.
  - `App.vue`: Componente principal da aplicação.
  - `main.js`: Ponto de entrada da aplicação.
  - `components/`: Diretório para componentes reutilizáveis.
    - `DigitalClock.vue`: Componente que exibe um relógio digital.
    - `TodoList.vue`: Componente que gerencia a lista de tarefas.
  - `assets/`: Diretório para arquivos estáticos, como imagens e estilos.

## Scripts Disponíveis

- `dev`: Inicia o servidor de desenvolvimento.
- `build`: Gera a versão de produção da aplicação.
- `preview`: Visualiza a versão de produção localmente.
- `test`: Executa um comando de teste simples.

Este projeto é uma excelente oportunidade para aprender sobre Vue 3 e Vite, além de ser uma base sólida para desenvolver aplicações mais complexas.