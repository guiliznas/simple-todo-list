<template>
  <div id="clock">
    <p class="date">{{ date }}</p>
    <p class="time">{{ time }}</p>
  </div>
</template>

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
