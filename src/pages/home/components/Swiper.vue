<template>
	<div class="wrapper">
		<swiper :options="swiperOption" v-if="showSwipter">
	    <!-- slides -->
	    <swiper-slide v-for='item of swiperList' :key='item.id'>
	    	<img class="swiper-img" :src="item.imgUrl" />
	    </swiper-slide>
	    <!-- Optional controls -->
	    <div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>
	</div>
</template>

<script>
	export default {
		name: 'HomeSwiper',
		data (){
			return {
				swiperOption: {
					pagination:'.swiper-pagination',
					loop:true
				},
			}
			
		},
		props:{
			swiperList:Array
		},
		computed:{
			showSwipter(){
				return this.swiperList.length
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.wrapper >>> .swiper-pagination-bullet-active
	  background: #fff
	.wrapper
	  overflow:hidden
	  width: 100%
	  height:0
	  padding-bottom: 31.25%
	  background: #eee
	  .swiper-img
	    width: 100%
</style>