<template>
  <div class="container">
    <div class="row">
      <div class="col-md-7">
        <div class="row">

          <div class="col-md-6" :key="product.id" v-for="product in products">

            <product :product="product"></product>
            
          </div>
          
        </div>
      </div>

      <div class="col-md-5"></div>
      
    </div>
    
  </div>
</template>

<script>

  import products from '@/products.json';
  import product from '@/components/Product.vue';

  export default {
    name: 'app',

    components:{

      product

    },

    data(){
      return {
        products
      }
    }
    
  }

</script>


<style >

  body{
    background-color: #a29bfe;
  }

</style>

