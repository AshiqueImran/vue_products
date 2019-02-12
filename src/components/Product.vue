<template>
	
	<div class="card my-2">

		<div class="card-body">

			<h5 class="text-center card-title"> {{ product.title }} </h5>
			<p class="text-center card-text text-muted display-4"> {{ product.price }} </p>
			<button class="btn btn-success form-control">Add to cart</button>
			
		</div>
		
	</div>

</template>

<script >
	
	export default {
		props:['product']
	}

</script>