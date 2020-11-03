<template>
  <div class="header flex">
  <div class="left">
    <img src="../assets/logo 2.png" alt="">
  </div>
  <div class="right">
    <ul class="flex">
      <li><a href="#">新規登録</a></li>
      <li><a href="#">ログイン</a></li>
    </ul>
  </div>
</div>
</template>

<style scoped>
.left img {
  width: 200px;
  margin: 10px;
}

.flex {
  display: flex;
  justify-content:space-between;
  align-items: center;
}

.right li {
  list-style: none;
  margin: 0 20px;
}

.right a {
  text-decoration: none;
}
</style>