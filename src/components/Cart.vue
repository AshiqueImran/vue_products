<template>
	
	<div>
		<ul class="list-group my-3">

			<li class="list-group-item" v-for="item in items" :key="item.id">
				name: <b>{{item.title}}</b> - price: <b>{{item.price}}</b>
				<button @click="$emit('remove_item',item)" class="btn badge badge-danger float-right">Remove</button>
			</li>
		</ul>

		<div class="card my-3 p-2">
			<h4 class="text-center">Total: {{ totalPriceCount }}</h4>
			<button :disabled="items.length==0" @click="$emit('pay')" class="btn btn-info">Pay now</button>
		</div>
	</div>

</template>

<script >
	export default {
		
		props:['items'],

		computed:{
			totalPriceCount()
			{
				return this.items.reduce((acc,item)=>acc+Number(item.price),0)
			}
		}
	}
	</script>