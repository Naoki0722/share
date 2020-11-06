<template>
  <div class="flex">
    <SideNavi></SideNavi>
    <div class="right">
      <div class="title">
        <p>ホーム</p>
      </div>
      <Message :id="id"></Message>
      <div class="comment">
        <div class="comment-title">
          <p>コメント</p>
        </div>
        <div class="message" v-for="(comment,index) in data" :key="index">
          <div class="flex">
            <p class="name">{{comment.comment_user.name}}</p>
          </div>
          <div>
            <p class="text">{{comment.comment.content}}</p>
          </div>
        </div>
        <input v-model="content" type="text" />
        <div @click="send">
          <button>コメント</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SideNavi from "../components/SideNavi.vue";
import Message from "../components/Message.vue";
import axios from "axios";
export default {
  props: ["id"],
  data() {
    return {
      content: "",
      data: "",
    };
  },
  components: {
    SideNavi,
    Message
  },
  methods: {
    send() {
      axios
        .post("https://guarded-beyond-52318.herokuapp.com/api/comment", {
          share_id: this.id,
          user_id: this.$store.state.user.id,
          content: this.content,
        })
        .then((response) => {
          console.log(response);
          this.content = "",
          this.$router.go({
            path: this.$$router.currentRoute.path,
            force: true,
          });
        });
    },
    comment() {
      axios
        .get("https://guarded-beyond-52318.herokuapp.com/api/shares/" + this.id)
        .then((response) => {
          this.data = response.data.comment;
        });
    },
  },
  created() {
    this.comment();
  }
};
</script>

<style scoped>
.flex {
  display: flex;
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

.right {
  width: 100%;
}

.title {
  padding: 25px 20px;
  border-bottom: solid 1px white;
  border-left: solid 1px white;
  font-size: 20px;
  font-weight: bold;
}

.message {
  padding-top: 10px;
  padding-left: 10px;
  padding-bottom: 10px;
  border-bottom: 1px solid white;
  border-left: 1px solid white;
}

.comment input {
  display: block;
  width: 95%;
  height: 30px;
  margin: 10px auto;
  background-color: #15202b;
  border: 1px solid white;
  border-radius: 5px;
}

.comment-title {
  border-bottom: solid 1px white;
  border-left: solid 1px white;
  text-align: center;
  padding: 15px 0;
}

.text {
  margin-top: 10px;
  font-size: 10px;
}

</style>
