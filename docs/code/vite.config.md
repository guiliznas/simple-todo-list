---
title: vite.config.js
description: 'Configuração do Vite para um projeto Vue.js.'
---

# vite.config.js

Este arquivo contém a configuração do Vite, uma ferramenta de construção para projetos modernos de front-end, especialmente otimizada para aplicações Vue.js.

## Conteúdo do Arquivo

```javascript
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [vue()],
})
```

## Descrição

- **Importações**:
  - `defineConfig`: Função do Vite que permite definir a configuração de forma tipada.
  - `@vitejs/plugin-vue`: Plugin que adiciona suporte ao Vue.js.

- **Configuração**:
  - O objeto passado para `defineConfig` contém a propriedade `plugins`, que é um array onde o plugin Vue é adicionado. Isso permite que o Vite processe arquivos `.vue` corretamente.

## Referências

Para mais informações sobre a configuração do Vite, consulte a [documentação oficial do Vite](https://vitejs.dev/config/).