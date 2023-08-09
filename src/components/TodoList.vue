<template>
  <div class="tab-container">
    <div style="display: flex; align-items: center; margin-bottom: 30px;">
      <DigitalClock />
    </div>
    <div class="tab-buttons">
      <button
        class="tab-button"
        :class="{ active: activeTab === 'Trabalho' }"
        @click="changeTab('Trabalho')"
      >
        Trabalho
      </button>
      <button
        class="tab-button"
        :class="{ active: activeTab === 'Casa' }"
        @click="changeTab('Casa')"
      >
        Casa
      </button>
    </div>
    <div class="tab-content">
      <div class="tab-pane" v-for="(item, index) in getActiveTabItems" :key="index">
        <input
          class="text-input"
          v-model="item.value"
          :placeholder="item.placeholder"
        />
        <button class="delete-button" @click="clearItem(item)">
          Done
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import DigitalClock from './DigitalClock.vue';

export default {
  components: {DigitalClock},
  data() {
    return {
      activeTab: 'Trabalho',
      tabs: {
        Trabalho: [
          { value: '', placeholder: '' },
          { value: '', placeholder: '' },
          { value: '', placeholder: '' },
          { value: '', placeholder: '' },
          { value: '', placeholder: '' },
          { value: '', placeholder: '' },
          { value: '', placeholder: '' }
        ],
        Casa: [
          { value: '', placeholder: '' },
          { value: '', placeholder: '' },
          { value: '', placeholder: '' },
          { value: '', placeholder: '' },
          { value: '', placeholder: '' },
          { value: '', placeholder: '' },
          { value: '', placeholder: '' }
        ]
      }
    };
  },
  computed: {
    getActiveTabItems() {
      return this.tabs[this.activeTab];
    }
  },
  watch: {
    // Observar mudanças nos dados do componente e salvá-los no localStorage
    'tabs.Trabalho': {
      handler: function(newVal) {
        localStorage.setItem('Trabalho', JSON.stringify(newVal));
      },
      deep: true
    },
    'tabs.Casa': {
      handler: function(newVal) {
        localStorage.setItem('Casa', JSON.stringify(newVal));
      },
      deep: true
    }
  },
  mounted() {
    // Recuperar dados do localStorage
    this.tabs.Trabalho = JSON.parse(localStorage.getItem('Trabalho')) || this.tabs.Trabalho;
    this.tabs.Casa = JSON.parse(localStorage.getItem('Casa')) || this.tabs.Casa;
  },
  methods: {
    changeTab(tabName) {
      this.activeTab = tabName;
    },
    clearItem(item) {
      item.value = '';
    },
  }
};
</script>

<style scoped>
.tab-container {
  max-width: 600px;
  margin: 0 auto;
}

.tab-buttons {
  display: flex;
}

.tab-button {
  flex: 1;
  padding: 10px;
  background-color: #f0f0f0;
  text-align: center;
  cursor: pointer;
  border: none;
  outline: none;
  font-size: 16px;
  color: #333;
}

.tab-button.active {
  background-color: var(--primary);
  color: #fff;
}

.tab-content {
  padding: 20px;
}

.tab-pane {
  display: flex;
  margin-bottom: 10px;
  align-items: center;
  position: relative;
}

.text-input {
  flex: 1;
  padding: 8px;
  border: none;
  outline: none;
  background-color: #f0f0f0;
  color: #333;
  border-radius: 6px;
}

.delete-button {
  padding: 8px;
  background-color: #f0f0f0;
  border: none;
  outline: none;
  cursor: pointer;
  color: var(--primary);
  position: absolute;
  right: -56px;
}

.delete-button:hover {
  color: #0056b3;
}

.add-button {
  margin-top: 10px;
  padding: 10px;
  background-color: var(--primary);
  border: none;
  outline: none;
  color: #fff;
  cursor: pointer;
}

.add-button:hover {
  background-color: #0056b3;
}

/* Estilo para o botão */
.delete-button {
  /* Especifica o estilo padrão do botão */
  /* ... estilo padrão ... */
  /* Define a opacidade como 0 para que o botão fique invisível por padrão */
  opacity: 0;
  transition: 0.2s ease all;
}

/* Estilo para o botão quando o mouse estiver sobre o item */
.tab-pane:hover .delete-button {
  /* Define a opacidade como 1 para que o botão fique visível quando o mouse estiver sobre o item */
  opacity: 1;
}

/* Estilo para o botão em dispositivos móveis */
@media (max-width: 768px) {
  /* Define a opacidade como 1 para que o botão fique sempre visível em dispositivos móveis */
  .delete-button {
    opacity: 1;
  }
}
</style>
