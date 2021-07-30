<template>
	<view class="home">
		<view v-if="shownav">
			<navbar :mapshow="mapshow" ></navbar>	
		</view>
		<view v-if="mapshow">
			<mapcd @backtolists="backtolists"></mapcd>
		</view>
		<scroll-view v-else scroll-y="true" class="scroll" @scrolltolower="showNavbar" @scrolltoupper="hideNavbar">
			<homebanner></homebanner>
			<homeblock @showmap = "showmap"></homeblock>
		</scroll-view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				shownav: false,
				mapshow: false
			}
		},
		onLoad() {

		},
		methods: {
			showNavbar() {
				this.shownav = true
			},
			hideNavbar() {
				this.shownav = false
			},
			showmap() {
				console.log('openn')
				this.mapshow = true
			},
			backtolists() {
				console.log('eqweq')
				this.mapshow = false
			}
		}
	}
</script>

<style lang="scss">
	 page {
	    height: 100%;
	    display: flex;
	 }
	 .home {
		 height: 100%;
		 width: 100%;
	 }
	 .scroll {
		 height: 100%;
		 position: relative;
	 }
</style>
