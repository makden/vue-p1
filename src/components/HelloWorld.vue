<template>
  <div class="hello">
    <h6>{{ msg }}</h6>

    <div style="width: 200px">
      <images
        :srcpath="imgDef"
        titletext="test"
        :name="nameDef"
      />
    </div>

    <hr>

    <arrow @nextImageEvent="nextImage" />
</template>

<script>
import images from './image.vue';
import arrow from './arrow.vue';
export default {
   components: {
    images,
    arrow,
  },
  data(){
    return{
      imgDef:"https://mobilius-shop.ru/bitrix/templates/.default/components/bitrix/catalog.element/.default/images/no_photo.png",
      nameDef:"-=1100=-",
      defaultImage:"",

    }
  },
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  methods:{
    nextImage(src){
      if(this.defaultImage==""){
        this.defaultImage=this.imgDef;
      }
      if(src){
        this.imgDef = src;
      }else{
        this.imgDef = this.defaultImage;
      }
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
