<template>
  <div>
    <img v-bind:src="user.avatar" alt="" />
    <ul>
      <li><span>Имя</span>: {{user.first_name}}</li>
      <li><span>Фамилия</span>: {{user.last_name}}</li>
      <li><span>Email</span>: {{user.email}}</li>
      <li><span>Дата рождения</span>: {{user.date_of_birth}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "MainItem",
  props: {
    user: {
      type: Object,
      required: true,
    }
  }
}
</script>

<style scoped>
  div {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: lemonchiffon;
    border-radius: 10px;
    padding: 20px;

  }
  img {
    border: 1px solid black;
    border-radius: 50%;
    background-color: #fff;
    max-width: 100%;
    margin-bottom: 20px;
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
  @media (max-width: 375px) {

    li {
      font-size: 18px;
    }
  }
</style>