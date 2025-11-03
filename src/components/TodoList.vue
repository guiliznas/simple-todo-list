<template>
  <div class="tab-container">
    <div class="header">
      <img
        src="../assets/icon-512-white.png"
        width="32"
        height="32"
        alt="To-do icon"
      />
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
      <div
        class="tab-pane"
        v-for="(item, index) in getActiveTabItems"
        :key="index"
      >
        <input
          class="text-input"
          v-model="item.value"
          placeholder="O que precisa ser feito?"
          :name="`item-${index}`"
          :id="`item-${index}`"
        />
        <button
          class="delete-button"
          @click="clearItem(item)"
          v-if="item.value"
        >
          ✓
        </button>
      </div>
    </div>

    <div class="clock-container">
      <DigitalClock />
    </div>
  </div>
</template>

<script>
import DigitalClock from "./DigitalClock.vue";

export default {
  components: { DigitalClock },
  data() {
    return {
      activeTab: "Trabalho",
      tabs: {
        Trabalho: [
          { value: "", placeholder: "" },
          { value: "", placeholder: "" },
          { value: "", placeholder: "" },
          { value: "", placeholder: "" },
          { value: "", placeholder: "" },
        ],
        Casa: [
          { value: "", placeholder: "" },
          { value: "", placeholder: "" },
          { value: "", placeholder: "" },
          { value: "", placeholder: "" },
          { value: "", placeholder: "" },
        ],
      },
    };
  },
  computed: {
    getActiveTabItems() {
      return this.tabs[this.activeTab];
    },
  },
  watch: {
    // Observar mudanças nos dados do componente e salvá-los no localStorage
    "tabs.Trabalho": {
      handler: function (newVal) {
        localStorage.setItem("Trabalho", JSON.stringify(newVal));
      },
      deep: true,
    },
    "tabs.Casa": {
      handler: function (newVal) {
        localStorage.setItem("Casa", JSON.stringify(newVal));
      },
      deep: true,
    },
  },
  mounted() {
    // Recuperar dados do localStorage
    this.tabs.Trabalho =
      JSON.parse(localStorage.getItem("Trabalho")) || this.tabs.Trabalho;
    this.tabs.Casa = JSON.parse(localStorage.getItem("Casa")) || this.tabs.Casa;
  },
  methods: {
    changeTab(tabName) {
      this.activeTab = tabName;
    },
    clearItem(item) {
      item.value = "";
    },
  },
};
</script>

<style scoped>
.tab-container {
  max-width: 720px;
  margin: 0 auto;
  background-color: transparent;
  border-radius: 12px;
  box-shadow: none;
  padding: 30px;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto",
    sans-serif;
}

.header {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
}

.clock-container {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 40px;
}

.header img {
  filter: none;
}

.header-title {
  margin-left: 12px;
  font-size: 20px;
  font-weight: 600;
  color: #f0f0f0;
}

.tab-buttons {
  display: flex;
  margin-bottom: 30px;
}

.tab-button {
  flex: 1;
  padding: 12px 20px;
  background-color: transparent;
  text-align: center;
  cursor: pointer;
  border: none;
  outline: none;
  font-size: 15px;
  font-weight: 500;
  color: #666;
  transition: 0.2s ease all;
  position: relative;
}

.tab-button:not(.active):hover {
  color: #999;
}

.tab-button.active {
  color: #f0f0f0;
}

.tab-button.active::after {
  content: "";
  position: absolute;
  bottom: -2px;
  left: 0;
  right: 0;
  height: 2px;
  background-color: #f0f0f0;
}

.tab-content {
  padding: 0;
}

.tab-pane {
  display: flex;
  margin-bottom: 16px;
  align-items: center;
  position: relative;
}

.text-input {
  flex: 1;
  width: 100%;
  padding: 14px 16px;
  border: 1px solid #444;
  outline: none;
  background-color: transparent;
  color: #f0f0f0;
  border-radius: 8px;
  font-size: 15px;
  transition: 0.2s ease all;
}

.text-input:focus {
  border-color: #888;
}

.text-input::placeholder {
  color: #666;
}

.delete-button {
  padding: 8px 12px;
  background-color: transparent;
  outline: none;
  cursor: pointer;
  color: #f0f0f0;
  border: none;
  position: absolute;
  right: 12px;
  font-size: 18px;
  font-weight: bold;
  transition: 0.2s ease all;
  opacity: 0;
}

.delete-button:hover {
  color: #ccc;
  transform: scale(1.1);
}

/* Estilo para o botão quando o mouse estiver sobre o item */
.tab-pane:hover .delete-button {
  opacity: 1;
}

/* Estilo para o botão em dispositivos móveis */
@media (max-width: 768px) {
  .tab-container {
    padding: 20px;
    border-radius: 0;
  }

  .delete-button {
    opacity: 1;
    position: initial;
    margin-left: 8px;
  }
}
</style>
