<template>
		<div>
			<div v-for="pro in products" :key="pro.id" class="job">
				<h1>{{pro}}</h1>
			</div>
		</div>
</template>
<script>

export default ({
	data(){
		return{
			products: []
		}
	},
	mounted(){
		fetch('http://localhost:3000/products')
			.then(res => res.json())
			.then(data => this.products = data)
			.catch(err => console.log(err.message))
	}
})
</script>
