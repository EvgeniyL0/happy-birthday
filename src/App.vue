<template>
  <div id="app">
    <p>Я буду слать тебе поздравления в консоль каждые 5 секунд. Ничто не сможет меня остановить!</p>
    <p>С любовью, твоя</p>
    <p>
      <strong>Ирина Аллегрова</strong>
    </p>
    <p class="message">{{ message }}</p>
  </div>
</template>

<script>
const arr = [
  "Любви до головокружения!",
  "Всех желаний исполнения!",
  "Миллион ночей и дней!",
  "Самых преданных друзей!"
];

function getRandomInt(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min)) + min;
}

export default {
  name: "App",
  data() {
    return {
      message: "С Днём Рождения!"
    };
  },
  beforeUpdate() {
    console.log(`С Днём Рождения! ${this.message}`);
  },
  created() {
    setInterval(() => {
      this.message = arr[getRandomInt(0, 4)];
    }, 5000);
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.message {
  color: white;
}
</style>
