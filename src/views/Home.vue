<template>
  <div class="flex">
    <SideNavi></SideNavi>
    <div class="right">
      <div class="title">
        <p>ホーム</p>
      </div>
      <Message></Message>
    </div>
  </div>
</template>

<script>
import SideNavi from "../components/SideNavi.vue";
import Message from "../components/Message.vue";

export default {
  components: {
    SideNavi,
    Message
  }
};
</script>

<style scoped>
.left {
  width: 30%;
  height: 100vh;
}

.flex {
  display: flex;
}

.flexbox {
  display: flex;
  align-items: center;
}

.header-logo img {
  width: 200px;
  margin: 10px 10px 20px;
}

.icon-field {
  margin: 10px 20px;
}

.icon-field img {
  width: 35px;
  margin-right: 20px;
}

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
  padding: 20px;
  border-bottom: solid 1px white;
  border-left: solid 1px white;
}

.name {
  font-size: 18px;
  font-weight: bold;
  margin-right: 10px;
}

.icon {
  width: 35px;
  padding: 0 5px;
}

.detail {
  margin-left: 50px;
}

.shares {
  margin-top: 10px;
}
</style>
