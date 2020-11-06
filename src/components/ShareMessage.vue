<template>
  <div class="share">
    <p>シェア</p>
    <textarea v-model="share"></textarea>
    <div @click="send">
      <button>シェアする</button>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      share: ""
    };
  },
  methods: {
    send() {
      if (this.share === "") {
        alert("シェアする内容を入力してください");
      } else {
        axios
          .post("https://stormy-sea-56567.herokuapp.com/api/shares", {
            user_id: this.$store.state.user.id,
            share: this.share,
          })
          .then((response) => {
            console.log(response);
            alert("シェアしました");
            this.share = "";
            this.$router.go({
              path: this.$router.currentRoute.path,
              force: true,
            });
          });
      }
    },
  },
  
};
</script>

<style scoped>
.share {
  margin: 15px;
}

.share textarea {
  margin: 15px 0;
  height: 120px;
  background-color: #15202b;
  border: 1px solid white;
  border-radius: 5px;
  width: 85%;
}

button {
  background-color: #4A28D1;
  border-radius: 20px;
  border: none;
  padding: 10px 15px;
  display: block;
  margin: 0 0 0 auto;
  text-align: center;
}
</style>