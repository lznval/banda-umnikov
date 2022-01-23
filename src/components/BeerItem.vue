<template>
  <div class="body">
    <h1>Как тебе такой вариант?</h1>
    <ul>
      <li><span>Бренд</span>: {{beer.brand}}</li>
      <li><span>Название</span>: {{beer.name}}</li>
      <li><span>Вкус</span>: {{beer.style}}</li>
      <li><span>Алкоголь</span>: {{beer.alcohol}}</li>
    </ul>
    <div class="btn">
      <button v-on:click="$emit('newBeer', beer.id)">Подбери лучшее пиво!</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "BeerItem",
  props: ["beer"]
}
</script>

<style scoped>
  h1 {
    text-align: center;
  }
  .body {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: lemonchiffon;
    border-radius: 10px;
    padding: 20px;
    width: 450px;
    height: 400px;
    justify-content: space-between;
  }

  ul {
    display: flex;
    align-items: center;
    flex-direction: column;
    list-style: none;
    text-align: center;
  }
  li {
    margin-bottom: 20px;
    color: black;
    font-size: 24px;
  }
  li span {
    font-weight: bold;
  }
  li:last-child {
    margin-bottom: 0;
  }
  button {
    justify-self: flex-end;
    background-color: yellowgreen;
    padding: 15px;
    font-size: 18px;
    font-weight: bold;
    border: none;
    border-radius: 30px;
  }
  button:hover {
    cursor: pointer;
  }
  @media (max-width: 960px) {
    .body {
      margin-top: 50px;
      width: 100%;
      height: 100%;
    }
    .btn {
      margin-top: 20px;
    }
  }
  @media (max-width: 375px) {
    li {
      font-size: 18px;
    }
    h1 {
      font-size: 24px;
      margin-bottom: 20px;
    }

  }
</style>