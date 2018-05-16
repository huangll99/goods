<template>
  <div>
    <div v-for="item in res.data">
      {{item.author_name}} <br>
      {{item.date}} <br>
      {{item.title}} <br>
      <img :src="item.thumbnail_pic_s">
    </div>
  </div>
</template>

<script type="application/ecmascript">
export default {
  name: 'HelloWorld',
  data () {
    return {
      res:{}
    }
  },
  created(){
    const that = this;
    this.$axios.post('/news/index',{}).then(function (res) {
      console.log(res.data);
      that.res = res.data
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
