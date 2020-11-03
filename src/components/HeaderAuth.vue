<template>
  <div class="header flex">
  <div class="left">
    <img src="../assets/logo 2.png" alt="">
  </div>
  <div class="right">
    <ul class="flex">
      <li @click="$router.push('/signup')">新規登録</li>
      <li @click="$router.push('/')">ログイン</li>
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
  cursor: pointer;
}

.right a {
  text-decoration: none;
}
</style>