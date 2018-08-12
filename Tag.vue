<template>
   <span class="tag">
      <p>{{ tag }}</p>
      <span class="close" @click="remove">x</span>
   </span>
</template>

<script>
  export default {
    props: ["tag", "index"],
    methods: {
      remove() {
        this.$emit("removeTagEvent", this.index)
      }
    },
  }
</script>
<style scoped>
  .tag {
    font-family: Arial;
    background-color: #fbbd08;
    position: relative;
    padding: 5px 10px;
    padding-right: 0px;
    position: relative;
    margin-right: 5px;
  }

  .tag p {
    font-weight: bold;
    font-size: 12px;
    margin-right: 30px;
    cursor: default;
    color: #666;
  }

  .tag * {
    display: inline-block;
  }

  .close {
    width: 15px;
    font-size: 12px;
    background-color: #666;
    color: #fbbd08;
    text-align: center;
    position: absolute;
    line-height: 27px;
    cursor: pointer;
    top: 0;
    right: 0px;
    transition: background-color .5s ease-in-out;
  }

  .close:hover {
    background-color: #000;
    transition: background-color .5s ease-in-out;
  }
</style>
