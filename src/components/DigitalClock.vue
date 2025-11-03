<template>
  <div id="clock">
    <p class="date" style="border-right: 1px solid #999; padding-right: 8px">
      {{ time }}
    </p>
    <p class="date">{{ date }}</p>
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
    let timerID = setInterval(this.updateTime, 1000);
    this.updateTime();
  },
  methods: {
    updateTime() {
      const week = ["DOM", "SEG", "TER", "QUA", "QUI", "SEX", "SAB"];
      const cd = new Date();
      this.time =
        this.zeroPadding(cd.getHours(), 2) +
        ":" +
        this.zeroPadding(cd.getMinutes(), 2);
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
p {
  margin: 0;
  padding: 0;
}

#clock {
  color: #f0f0f0;
  text-shadow: none;
  display: flex;
  align-items: center;
  gap: 8px;
  margin: auto;
}

#clock .date {
  letter-spacing: 0.1em;
  font-size: 13px;
  color: #999;
  font-weight: 400;
}
</style>
