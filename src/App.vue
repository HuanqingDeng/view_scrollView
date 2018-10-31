<template>
	<!-- 首页轮播图 -->
	<div class="carousel">
		<div>
			<a href="#" v-for="(list,index) in carouselbooks" v-show="index==currentindex" :key="index"  >
				<img :src="list" alt=""/>
			</a>
		</div>
	</div>
</template>

<script>
import Vue from "vue";

/*导出该模块 */
export default {
  data() {
    return {
      carouselbooks: [
        "http://t2.hddhhn.com/uploads/tu/201612/98/st93.png",
        "http://t2.hddhhn.com/uploads/tu/201611/228/st87.png",
        "http://p0.so.qhimgs1.com/t013e7b12d08f155a4c.jpg"
      ],
      currentindex: 0
    };
  },
  created () {
    this.play()
  },
  methods: {
    autoplay() {
      this.currentindex++;
      if (this.currentindex === 3) {
        this.currentindex = 0;
      }
    },
    play() {
      setInterval(this.autoplay, 3000);
    }
  }
};
</script>

<style scoped>
</style>