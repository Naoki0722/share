<template>
  <div class="flex">
    <SideNavi></SideNavi>
    <div class="right">
      <div class="title">
        <p>プロフィール</p>
      </div>
      <div class="profile flexbox">
        <div>
          <p class="p-name">{{name}}</p>
        </div>
        <div>
          <button type="submit">変更する</button>
        </div>
        <p class="p-content" v-if="active">{{profile}}</p>
        <input type="text" v-model="profile" v-else >
      </div>
      <Message></Message>
    </div>
  </div>
</template>

<script>
import SideNavi from "../components/SideNavi.vue";
import Message from "../components/Message.vue";
import axios from "axios";

export default {
  data() {
    return {
      active: true,
      name: this.$store.state.user.name,
      profile: this.$store.state.user.profile
    };
  },
  methods: {
    edit() {
      if (!this.active) {
        axios
          .put("https://stormy-sea-56567.herokuapp.com/api/user", {            
            email: this.$store.state.user.email,
            profile: this.profile,
          })
          .then((response) => {
            this.$store.dispatch("changeUserData", {
              profile: this.profile,
            })
            console.log(response);
          });
      }
      this.active = !this.active;
    },
  },
  components: {
    SideNavi,
    Message
  }
};
</script>

<style scoped>
.flex {
  display: flex;
}

.flexbox {
  display: flex;
  align-items: center;
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

.profile {
  border-bottom: solid 1px white;
  border-left: solid 1px white;
  justify-content:space-between;
  padding: 20px;
}

.p-name {
  font-size: 18px;
  font-weight: bold;
}

.p-content {
  margin-top: 10px;
}
</style>
