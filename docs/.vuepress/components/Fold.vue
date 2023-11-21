<template>
	<div class='fold'>
		<button @click='control'>{{btn}}</button>
		<div v-if='isshow' class='show'>
			<slot></slot>
		</div>
	</div>
	
</template>

<script>
	export default{
		data(){
			return {
				btn: "+",
				isshow:false
			}
		},
		methods:{
			control(){
				if(this.btn === "+"){
					this.isshow = true 
					this.btn = '-'
				}else{
					this.isshow = false
					this.btn = '+'
				}				
			}
		}
	}
</script>

<style scoped>
	.fold{
		overflow: hidden;
	}
	button{
		width:100px;
		height:40px;
		line-height: 40px;
		font-size:16px;
		background:#11A8CD;
		color:#FFF;
		border-radius: 4px;
		float: right;
		margin-right:24px;
		border:1px solid transparent;
		cursor:pointer
		/* margin-bottom:40px */
	}
	.show{
		margin-top:50px
	}
</style>