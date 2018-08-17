<template>
   <span class="tag" :class="selectedTheme">
      <p class="content">{{ tag }}</p>
      <span class="close" @click="remove"></span>
   </span>
</template>

<script>
  export default {
    props : {
      tag : String,
      index : Number,
      tagColor : {
        required : false,
        default : "primary"
      }
    },
    created(){
      this.selectedTheme = this.tagColor;
    },
    data(){
      return {
        selectedTheme : "primary"
      }
    },
    methods: {
      remove() {
        this.$emit("removeTagEvent", this.index)
      }
    },

  }
</script>
<style scoped>
  .success{
    background-color: #D5EDDB;
    border: 1px solid #c3e6cb;
    color: #155724;
  }
  .primary{
    color: #004085;
    background-color: #cce5ff;
    border-color: #b8daff;
  }
  .secondary{
    color: #383d41;
    background-color: #e2e3e5;
    border-color: #d6d8db;
  }
  .info{
    color: #0c5460;
    background-color: #d1ecf1;
    border-color: #bee5eb;
  }
  .warning{
    color: #856404;
    background-color: #fff3cd;
    border-color: #ffeeba;
  }
  .danger{
    color: #721c24;
    background-color: #f8d7da;
    border-color: #f5c6cb;
  }
  .tag {
    font-family: Arial;
    border-radius: 5px;
    position: relative;
    padding: 5px 10px;
    padding-right: 0px;
    position: relative;
    margin-right: 5px;
  }
  .tag .content {
    font-weight: bold;
    font-size: 12px;
    margin-right: 20px;
    cursor: default;

  }
  .tag * {
    display: inline-block;
  }
  .close {
    width: 15px;
    font-size: 17px;
    text-align: center;
    position: absolute;
    line-height: 27px;
    cursor: pointer;
    top: 0;
    right: 0px;
    transition: background-color .5s ease-in-out;
  }
  .close:after{
    display: inline-block;
    content: "\00d7";
  }
</style>
