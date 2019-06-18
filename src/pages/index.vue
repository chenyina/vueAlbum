<template>
<div>
  <div>
    <ul>
      <ol
        :key="index" 
        @click="preview(index)"
        v-for="(l, index) in images">
         <img :src="l" alt=""> 
      </ol>
    </ul>
  </div>
</div> 
</template>
<script>
export default {
  name: 'app',
  data() {
    return {
      images: [
        'http://zhangxj-test.oss-cn-shanghai.aliyuncs.com/logoImg/010601/074a29b32e4e4641bc9e02a4c2acbfe0.png',
        'http://zhangxj-test.oss-cn-shanghai.aliyuncs.com/logoImg/010601/074a29b32e4e4641bc9e02a4c2acbfe0.png',
        'http://zhangxj-test.oss-cn-shanghai.aliyuncs.com/logoImg/010601/074a29b32e4e4641bc9e02a4c2acbfe0.png',
        'http://zhangxj-test.oss-cn-shanghai.aliyuncs.com/logoImg/010601/074a29b32e4e4641bc9e02a4c2acbfe0.png',
        'http://zhangxj-test.oss-cn-shanghai.aliyuncs.com/logoImg/010601/074a29b32e4e4641bc9e02a4c2acbfe0.png'
      ]
    }
  },
  created() {
    this.loadImage();
  },
  methods: {
    preview(index) {
      this.$imagePreview({
        images: this.images,
        index: index,
      })
    },
    loadImage(){
      this.axios({
        method: 'post',
        url: '/user/12345',
        data: {
          firstName: 'Fred'
        }
      });
    }
  }
}
</script>
<style scoped>
  img{
	width:215px;
	height:215px;
	margin:5px 0px 0px 5px;
   }
  ol{
  display: inline-block;
	width:225px;
	height:225px;
  margin: 10px;
	background-repeat:no-repeat;
	background-color:#fff;
	cursor:pointer;
	-moz-box-shadow:1px 1px 3px #000;
	-webkit-box-shadow:1px 1px 3px #000;
	box-shadow:1px 1px 3px #000;
  }
</style>