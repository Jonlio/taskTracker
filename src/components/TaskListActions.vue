<template>
<el-button
    icon="el-icon-document-copy"
    circle
    type="primary"
    size="mini"
    @click="sendCopyTaskname"
  ></el-button>
  <el-button
    icon="el-icon-video-play"
    circle
    type="primary"
    size="mini"
    @click="sendRestart"
  ></el-button>
  <el-button
    icon="el-icon-delete"
    circle
    size="mini"
    type="danger"
    @click="sendDelete"
  ></el-button>
</template>

<script>
export default {
  props: {
    taskID: {
      type: String,
      required: true,
    },
  },
  emits: ["restart", "delete", "copyTaskname"],
  methods: {
    sendRestart() {
      this.$emit("restart", this.taskID);
    },
    sendDelete() {
      this.$emit("delete", this.taskID);
    },
    sendCopyTaskname() {
        this.$emit('copyTaskname')
    }
  },
};
</script>

<style>
</style>