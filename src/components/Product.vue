<template>
	
	<div class="card my-2">

		<div class="card-body">

			<h5 class="text-center card-title"> {{ product.title }} </h5>
			<p class="text-center card-text text-muted display-4"> {{ product.price }} </p>
			<button :disabled="is_in_cart" class="btn btn-success form-control" @click="$emit('add-to-cart',product)">{{ is_in_cart ? 'Added' : 'Add to cart'}}</button>
			
		</div>
		
	</div>

</template>

<script >
	
	export default {
		props:['product','is_in_cart']
	}

</script>