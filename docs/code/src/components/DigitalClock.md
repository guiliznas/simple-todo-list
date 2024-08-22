---
title: DigitalClock
description: 'Componente Vue que exibe a data e a hora atual, atualizando a cada 10 segundos.'
---

# DigitalClock

O componente `DigitalClock` é um componente Vue que exibe a data e a hora atual. Ele atualiza a cada 10 segundos, garantindo que as informações apresentadas estejam sempre atualizadas.

## Estrutura do Componente

### Template

O template do componente é composto por um `div` que contém dois parágrafos: um para a data e outro para a hora.

```html
<template>
  <div id="clock">
    <p class="date">{{ date }}</p>
    <p class="time">{{ time }}</p>
  </div>
</template>
```

### Script

O script do componente define a lógica para atualizar a data e a hora. Ele contém as seguintes partes:

- **Data**: Armazena as variáveis `time` e `date`.
- **Created**: Inicia um intervalo que chama o método `updateTime` a cada 10 segundos.
- **Methods**:
  - `updateTime`: Atualiza as variáveis `time` e `date` com os valores atuais.
  - `zeroPadding`: Formata números para garantir que tenham um número fixo de dígitos, adicionando zeros à esquerda quando necessário.

```javascript
<script>
export default {
  data() {
    return {
      time: "",
      date: "",
    };
  },
  created() {
    let timerID = setInterval(this.updateTime, 10000);
    this.updateTime();
  },
  methods: {
    updateTime() {
      const week = ["DOM", "SEG", "TER", "QUA", "QUI", "SEX", "SAB"]; 
      const cd = new Date();
      this.time =
        this.zeroPadding(cd.getHours(), 2) +
        ":" +
        this.zeroPadding(cd.getMinutes(), 2) +
        ":" +
        this.zeroPadding(cd.getSeconds(), 2);
      this.date =
        this.zeroPadding(cd.getFullYear(), 4) +
        "-" +
        this.zeroPadding(cd.getMonth() + 1, 2) +
        "-" +
        this.zeroPadding(cd.getDate(), 2) +
        " " +
        week[cd.getDay()];
    },
    zeroPadding(num, digit) {
      let zero = "";
      for (let i = 0; i < digit; i++) {
        zero += "0";
      }
      return (zero + num).slice(-digit);
    },
  },
};
</script>
```

### Estilos

Os estilos do componente são definidos para garantir uma apresentação visual adequada. O fundo é um gradiente radial e o texto é estilizado para ser legível e atraente.

```css
<style scoped>
body {
  background: var(--primary);
  background: radial-gradient(ellipse at center, #0a2e38 0%, #000000 70%);
}
p {
  margin: 0;
  padding: 0;
}
#clock {
  color: #daf6ff;
  text-shadow: 0 0 20px rgba(10, 175, 230, 1), 0 0 20px rgba(10, 175, 230, 0);
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: auto;
}
#clock .time {
  letter-spacing: 0.05em;
  font-size: 24px;
  padding: 5px 0;
}
#clock .date {
  letter-spacing: 0.1em;
  font-size: 11px;
}
</style>
```

## Considerações Finais

O componente `DigitalClock` é uma implementação simples e eficaz para exibir a hora e a data em um formato amigável. Ele pode ser facilmente integrado em qualquer aplicação Vue e customizado conforme necessário.