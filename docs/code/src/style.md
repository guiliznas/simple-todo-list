---
title: style.css
description: 'Estilos globais para a aplicação, definindo tipografia, cores e layout.'
---

# style.css

Este arquivo contém os estilos globais da aplicação, definindo a tipografia, cores e layout. Abaixo estão as principais seções e suas descrições:

## Variáveis Globais

```css
:root {
  font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  line-height: 1.5;
  font-weight: 400;

  color-scheme: light dark;
  color: rgba(255, 255, 255, 0.87);
  background-color: #242424;

  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -webkit-text-size-adjust: 100%;
}
```
Define a fonte padrão, a altura da linha, o peso da fonte e as cores de fundo e texto. Também inclui propriedades para otimização de legibilidade.

## Links

```css
a {
  font-weight: 500;
  color: #646cff;
  text-decoration: inherit;
}
a:hover {
  color: #535bf2;
}
```
Estiliza os links, definindo a cor e o comportamento ao passar o mouse.

## Corpo da Página

```css
body {
  margin: 0;
  display: flex;
  place-items: center;
  min-width: 320px;
  min-height: 100vh;
}
```
Configura o corpo da página para usar flexbox, centralizando o conteúdo e garantindo um tamanho mínimo.

## Títulos

```css
h1 {
  font-size: 3.2em;
  line-height: 1.1;
}
```
Define o estilo do título principal, incluindo tamanho e altura da linha.

## Botões

```css
button {
  border-radius: 8px;
  border: 1px solid transparent;
  padding: 0.6em 1.2em;
  font-size: 1em;
  font-weight: 500;
  font-family: inherit;
  background-color: #1a1a1a;
  cursor: pointer;
  transition: border-color 0.25s;
}
button:hover {
  border-color: #646cff;
}
button:focus,
button:focus-visible {
  outline: 4px auto -webkit-focus-ring-color;
}
```
Estiliza os botões, incluindo bordas, preenchimento e efeitos de foco e hover.

## Cartões

```css
.card {
  padding: 2em;
}
```
Define o preenchimento para elementos com a classe `.card`.

## Container Principal

```css
#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}
```
Configura o container principal da aplicação, limitando a largura máxima e centralizando o conteúdo.

## Mídia Queries

```css
@media (prefers-color-scheme: light) {
  :root {
    color: #213547;
    background-color: #ffffff;
  }
  a:hover {
    color: #747bff;
  }
  button {
    background-color: #f9f9f9;
  }
}
```
Adiciona estilos para o esquema de cores claro, alterando cores de texto, fundo e comportamento de hover para links e botões.