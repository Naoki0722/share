<template>
    <div class="left">
      <div class="header-logo">
        <img src="../assets/logo 2.png">
      </div>
      <div class="left-content">
        <div class="icon-field flexbox">
          <img src="../assets/home.png">
          <p>ホーム</p>
        </div>
        <div class="icon-field flexbox">
          <img src="../assets/profile.png">
          <p>プロフィール</p>
        </div>
        <div class="icon-field flexbox">
          <img src="../assets/logout.png">
          <p>ログアウト</p>
        </div>
      </div>
      <ShareMessage></ShareMessage>
    </div>
</template>

<script>
import ShareMessage from "./ShareMessage.vue";
export default {
  components: {
    ShareMessage
  }
}
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
</style>
