---
title: index.html
description: 'Arquivo HTML principal para a aplicação de lista de tarefas.'
---

# index.html

O arquivo `index.html` é o ponto de entrada da aplicação de lista de tarefas. Ele define a estrutura básica do documento HTML e inclui as configurações necessárias para a execução da aplicação.

## Estrutura do Documento

### Cabeçalho (`<head>`)

- **Base URL**: Define a base para URLs relativas.
  ```html
  <base href="/" />
  ```

- **Meta Tags**:
  - **Charset**: Define a codificação de caracteres como UTF-8.
    ```html
    <meta charset="UTF-8" />
    ```
  - **Compatibilidade**: Garante que o navegador use o modo mais recente.
    ```html
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    ```
  - **Viewport**: Configura a visualização em dispositivos móveis.
    ```html
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1" />
    ```
  - **Favicon**: Define o ícone da aba do navegador.
    ```html
    <link rel="shortcut icon" href="/favicon.ico" />
    ```
  - **Cores do Tema**: Define cores para o tile do Windows e tema do navegador.
    ```html
    <meta name="msapplication-TileColor" content="#2B5270" />
    <meta name="theme-color" content="#2B5270" />
    ```

- **Título**: Define o título da página que aparece na aba do navegador.
  ```html
  <title>To-do list</title>
  ```

- **Manifesto**: Link para o arquivo de manifesto da aplicação.
  ```html
  <link rel="manifest" href="/site.webmanifest" />
  ```

- **Descrição**: Fornece uma descrição da aplicação para motores de busca e compartilhamento.
  ```html
  <meta name="description" value="A simple to-do list to manage personal tasks" />
  ```

### Corpo (`<body>`)

- **Estilo de Fundo**: Define a cor de fundo da página.
  ```html
  <body style="background-color: #242424;">
  ```

- **Div Principal**: Contém o aplicativo Vue.
  ```html
  <div id="app"></div>
  ```

- **Script**: Importa o arquivo JavaScript principal da aplicação.
  ```html
  <script type="module" src="/src/main.js"></script>
  ```

## Considerações Finais

Este arquivo é essencial para a inicialização da aplicação, pois carrega o framework Vue e define a estrutura básica da interface do usuário. É importante garantir que todas as referências e links estejam corretos para o funcionamento adequado da aplicação.