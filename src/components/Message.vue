<template>
  <div>
    <div v-for="(value, index) in shares" :key="index">
      <div class="message">
        <div class="flexbox">
          <p class="name">{{value.name}}</p>
          <img class="icon" src="../assets/heart.png">
          <p class="name">{{value.like.length}}</p>
          <img class="icon" src="../assets/cross.png">
          <img class="icon detail" src="../assets/detail.png">
        </div>
        <p class="shares">{{value.share}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      shares: [
        {
        name: "太郎",
        like: [],
        share: "初めまして"
        },{
        name: "なお",
        like: [],
        share: "こんにちは"
        },
      ]
    };
  }
};
</script>

<style scoped>
.flexbox {
  display: flex;
  align-items: center;
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