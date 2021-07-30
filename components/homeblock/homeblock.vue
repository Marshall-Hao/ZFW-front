<template>
	<view class="homeblock">
		<profileblock></profileblock>
		<view class="resblock">
			<mapbutton @showmap="showmap"></mapbutton>
			<resrecommend></resrecommend>
			<reslists></reslists>
		</view>
	</view>
</template>

<script>
	import profileblock from './profileblock.vue';
	import mapbutton from './mapbutton.vue';
	import resrecommend from './resrecommend.vue';
	import reslists from './reslists.vue';
	export default {
		name:"homeblock",
		components: {
			profileblock,
			mapbutton,
			resrecommend,
			reslists
		},
		data() {
			return {
				
			};
		},
		methods: {
			showmap () {
				this.$emit('showmap')
			}
		}
	}
</script>

<style lang="scss">
	.homeblock {
		position: absolute;
		top: 200px;
		left: 0;
		width: 100%;
		box-sizing: border-box;
		border-radius: 20px 20px 0 0;
		background-color: #F7F7F7;
		.resblock {
			margin-top: 20px;
			padding: 0 10px;
		}
	}
</style>
