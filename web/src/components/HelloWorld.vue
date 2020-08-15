<template>
  <div id="background" class="background">
    <a style="float:right;margin-right:1%;color:white;margin-top:44%">{{display}}</a>
    <button style="float:right;margin-top:1%" @click="changebackgroundimg">切换背景</button>
    <div style="opacity:0.8;margin-left:10%;background-color:white;margin-top:3%;height:90%;width:80%;border:true">
      <br>
      <h1 style="margin-left:5%;">网站</h1>
      <td>
      </td>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      number: 0,
      picture: ['72441709_p0.png', '81046044_p0.png', '79583564_p0.png'],
      display: '79583564_p0.png'
    }
  },
  methods: {
    changebackgroundimg() {
      document.getElementById('background').style.backgroundImage = "url(/static/picture/" + this.picture[this.number] + ")";
      this.display = this.picture[this.number];
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
  opacity: 0.8;
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
/*a {
  color: #42b983;
}*/
</style>
