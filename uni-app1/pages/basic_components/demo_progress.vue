<template>
	<view class="flex">
		<view class="flex-item">
			 <progress percent="20" show-info/>
		</view>
		<view class="flex-item">
			 <progress active percent="40" stroke-width="9"/>
		</view>
		<view class="flex-item">
			 <progress percent="60" stroke-width="3" backgroundColor="#999"/>
		</view>
		<view class="flex-item">
			 <progress percent="80" stroke-width="3" activeColor="#FF0000"/>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
