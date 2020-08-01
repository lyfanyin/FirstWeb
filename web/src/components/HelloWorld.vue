<template>
 <div id="background" class="background">
   <button style="float:right;margin-right:10%;margin-top:3%" @click="changebackgroundimg">修改图片</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      number: 0,
      picture: ['/static/picture/72441709_p0.png', '/static/picture/81046044_p0.png', '/static/picture/79583564_p0.png']
    }
  },
  methods: {
    changebackgroundimg() {
      document.getElementById('background').style.backgroundImage = "url(" + this.picture[this.number] + ")";
      this.number++;
      if (this.number > 2){
        this.number = 0;
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
.background{
  height: 100%;
  width: 100%;
  background-image: url('/static/picture/79583564_p0.png');
  position: absolute;             /* 绝对定位，必要 */
  background-size:cover;          /* 图片拉伸覆盖，这个词条非常方便 */
  /*background-repeat:no-repeat;  图片不重复
  background-attachment: fixed;   图片不平铺，随动
  filter:blur(1px);               背景虚化，值越大越模糊 */
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
