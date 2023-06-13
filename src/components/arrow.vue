<template>
  <div id="arrow">
    <span v-show="displayPrev" @click="moveImage('prev')"><< </span>
    <span v-show="displayNext" @click="moveImage('next')"> >> </span>
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
      displayPrev: false,
      displayNext: true,
    };
  },
  methods: {
    moveImage(direction) {
      var allImage = this.iamges.length - 1;

      if (direction == 'next') {
        if (this.pos <= allImage) {
          this.displayPrev = true;
          let newSrc = this.iamges[this.pos].src;
          this.$emit('nextImageEvent', newSrc);
          if (this.pos == allImage) {
            this.displayNext = false;
            this.pos--;
          }
          this.pos++;
        }
      } else {
        if (this.pos != 0) {
          this.pos--;
          this.displayNext = true;
          let newSrc = this.iamges[this.pos].src;
          this.$emit('nextImageEvent', newSrc);
        } else {
          this.pos++;
          let newSrc = false;
          this.displayPrev = false;
          this.$emit('nextImageEvent', newSrc);
        }
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
