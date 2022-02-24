<template>
  <div>
    <input type="text" v-model="name" />
    <h1>Hey Mate!</h1>
    <p>my name is {{ name }}</p>
    <p v-text="name"></p>
    <p v-html="htmlContent"></p>
    <hr />
    <div>
      <!-- <button @click='count++'>add</button> -->
      <button @click="addCount">add</button>
      <!-- 這裡的v-on寫的是js語法 -->
    </div>
    click <span>{{ count }}</span>
    <hr />
    <button @click="changeLink">change to FB</button>
    <br />
    <!-- <a href="http://www.google.com">google</a> -->
    <a v-bind:href="link" :title="linkName">{{ linkName }}</a>
    <hr />
    <!-- <div class="box" :class='ifActive'></div> -->
    <div class="box" :class='{active : ifActive}' @click="toggleActive"></div>
  </div>
</template>

<script>
export default {
  name: "TestView",
  data() {
    return {
      name: "Max",
      htmlContent: "test <span>content</span>",
      count: 0,
      linkName: "google",
      link: "http://www.google.com",
      // ifActive:active,
      ifActive:false,
    };
  },
  methods: {
    addCount() {
      console.log("click");
      this.count++;
    },
    changeLink() {
      this.linkName = "facebook";
      this.link = "https://www.facebook.com/";
    },
    toggleActive(){
       this.ifActive = !this.ifActive;
    }
  },
};
</script>

<style>

.box {
  width: 150px;
  height: 150px;
  background: pink;
  transition: 0.5s;
}
.box.active {
  background: red;
}
</style>