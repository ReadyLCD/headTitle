<template>
  <div class="commentMain">
    <Parent :parentData="comment.parent" @replyParent="replyMoudle" v-if="comment.parent" />
    <div class="newContent">{{comment.content}}</div>
  </div>
</template>

<script>
import Parent from "./parent";
export default {
  components: {
    Parent
  },
  props: ["comment"],
  methods: {
    replyMoudle(userObj) {
      // console.log(userObj);
      this.$emit("replyModule", userObj);
    }
  }
};
</script>

<style lang="less" scoped>
.commentMain {
  padding: 2.78vw 0;
  .newContent {
    margin: 5.56vw 0 2.78vw;
  }
}
</style>
