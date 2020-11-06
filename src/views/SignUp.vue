<template>
  <div>
    <HeaderAuth></HeaderAuth>
    <div class="card">
      <p>新規登録</p>
      <input type="text" placeholder="ユーザーネーム" v-model="name">
      <input type="text" placeholder="プロフィール" v-model="profile">
      <input type="email" placeholder="メールアドレス" v-model="email">
      <input type="password" placeholder="パスワード" v-model="password">
      <button @click="auth">新規登録</button>
    </div>
  </div>
</template>

<script>
import HeaderAuth from "../components/HeaderAuth.vue";
import axios from "axios";
export default {
  data() {
    return {
      name: "",
      profile: "",
      email: "",
      password: ""
    }
  },
  components: {
    HeaderAuth
  },
  methods: {
    auth() {
      axios.post("https://guarded-beyond-52318.herokuapp.com/api/register",{
        name: this.name,
        profile: this.profile,
        email: this.email,
        password: this.password
      })
        .then(response => {
          console.log(response);
          this.$router.replace("/");
        })
        .catch(error => {
          alert(error);
        });
    }
  }
};
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