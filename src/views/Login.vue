<template>
  <div>
    <HeaderAuth></HeaderAuth>
    <div class="card">
      <p>ログイン</p>
      <input type="email" placeholder="メールアドレス" v-model="mail">
      <input type="password" placeholder="パスワード" v-model="password">
      <button @click="auth">ログイン</button>
    </div>
  </div>
</template>

<script>
import HeaderAuth from "../components/HeaderAuth.vue";
export default {
  data() {
    return {
      mail: "",
      password: ""
    }
  },
  components: {
    HeaderAuth
  },
  methods: {
    auth() {
      this.$store.dispatch("login", {
        email: this.email,
        password: this.password
      })
    }
  }
}
</script>

<style scoped>
.card {
  background-color: white;
  width: 350px;
  margin: 150px auto;
  padding: 35px 25px;
  color: black;
  text-align: center;
  border-radius: 10px;
}

.card p {
  color: black;
  font-weight: bold;
}

.card input {
  display: block;
  margin: 15px auto;
  color: black;
  width: 70%;
  height: 30px;
  padding: 5px;
  border-radius: 10px;
  border: 1px solid black;
}

.card button {
  background-color: #4A28D1;
  border-radius: 20px;
  border: none;
  padding: 10px 15px;
}

</style>