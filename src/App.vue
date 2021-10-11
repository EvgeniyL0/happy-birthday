<template>
  <div id="app">
    <p>
      Я буду слать тебе поздравления в консоль каждые 5 секунд. Ничто не сможет
      меня остановить!
    </p>
    <p>С любовью, твоя</p>
    <p>
      <strong>Ирина Аллегрова</strong>
    </p>
    <img class="image" src="../assets/images/ira.jpg" alt="">
    <p class="message">{{ message }}</p>
  </div>
</template>

<script>
const arr = [
  "Успеха, радости, везения!",
  "Любых желаний исполнения!",
  "Миллион ночей и дней!",
  "Любви до головокружения!",
  "Чумового настроения!",
  "Самых преданных друзей!",
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
      message: "С Днём Рождения!",
    };
  },
  beforeUpdate() {
    console.log(this.message);
  },
  created() {
    console.log(this.message);
    setInterval(() => {
      this.message = arr[getRandomInt(0, arr.length - 1)];
    }, 5000);
  },
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

.image {
  width: 200px;
  object-fit: cover;
}

.message {
  color: white;
}
</style>
