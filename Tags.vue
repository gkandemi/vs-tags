<template>
  <div class="tag-container">
    <div>
      <appTag
        v-for="(tag, i) in tags"
        :key="tag"
        :tag="tag"
        :index="i"
        @removeTagEvent="removeTheOne($event)"></appTag>
      <input
        type="text"
        @keydown.enter="add"
        @keydown.backspace="remove">
    </div>
    <small class="error" v-if="error != null"> {{ error }}</small>
  </div>

</template>
<script>
  import Tag from "./Tag";

  export default {
    components: {
      appTag: Tag
    },
    props: {
      value: {
        required: false
      }
    },
    data() {
      return {
        tags: [],
        error: null
      }
    },
    methods: {
      add(e) {
        if (e.target.value.length > 0) {
          let matchedTag = false;
          this.tags.forEach((item) => {
            if (item.toLowerCase() == e.target.value.toLowerCase()) {
              matchedTag = true;
            }
          })

          if (!matchedTag) {
            this.tags.push(e.target.value);
            this.$emit("input", this.tags.join(","));
            e.target.value = '';
          } else {
            this.error = "Bu etiket daha önce eklenmiş!";
            setTimeout(() => {
              this.error = '';
            }, 2000)
          }
        }
      },
      remove(e) {
        if (e.target.value.length <= 0) {
          this.tags.splice(this.tags.length - 1, 1);
          this.$emit("input", this.tags.join(","));
        }
      },
      removeTheOne(event) {
        this.tags.splice(event, 1)
        this.$emit("input", this.tags.join(","));
      }
    },
    created() {
      if (this.value) {
        if (this.value.length > 0) {
          const tag_list = this.value.split(",");
          console.log(tag_list);
          this.tags = tag_list;
        }
      }
    }
  }
</script>
<style scoped>
  .tag-container {
    border: 1px solid #ccc;
    padding: 3px;
    width: 100%;
    font-family: Arial;
  }

  input {
    width: 100px;
    height: 30px;
    outline: none;
    font-family: Arial;
  }

  .error {
    color: purple;
  }
</style>
