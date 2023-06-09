<template>
  <div id="arrow">
    <span @click="moveImage('prev')"><< </span>
    &nbsp;&nbsp;&nbsp;
    <span @click="moveImage('next')"> >> </span>
  </div>
</template>

<script>
export default {
  name: 'headerBox',
  props: {
    nameBox: String,
  },
  data() {
    return {
      iamges: [
        {
          id: 1,
          src: 'https://llegumsonline.com/wp-content/uploads/2019/05/Icones-03-e1560838037528.png',
        },
        { id: 2, src: 'https://image.ibb.co/j2qxEK/traking.jpg' },
        {
          id: 3,
          src: 'https://png.pngtree.com/png-vector/20191021/ourlarge/pngtree-vector-location-icon-png-image_1834256.jpg',
        },
        {
          id: 4,
          src: 'https://stroyderevo-91.ru/wp-content/uploads/2021/12/imagentripplannernavigation0big-768x768.png',
        },
        {
          id: 5,
          src: 'https://www.clipartmax.com/png/full/26-269508_geo-fence-icon-geofence-icon.png',
        },
      ],
      pos: 0,
    };
  },
  methods: {
    moveImage(direction) {
      var allImage = this.iamges.length;

      if (direction == 'next') {
        if (this.pos < allImage) {
          let newSrc = this.iamges[this.pos].src;
          console.log(this.pos);
          console.log(newSrc);
          this.pos++;
        } else {
          alert('STOP');
        }
      } else {
      }
    },
  },
};
</script>

<style scoped>
header {
  background-color: #f3f3f3;
}

#arrow span {
  cursor: pointer;
  font-size: 20px;
}
</style>
