<template>
  <div class="container">
    <div class="row">
      <div class="col-md-7">
        <div class="row">
          <div class="col-md-6" :key="product.id" v-for="product in products">

            <product v-on:add-to-cart="addtoCart(product)" :product="product" :is_in_cart="isInTheCart(product)"></product>
            
          </div>
          
        </div>
      </div>

      <div class="col-md-5">
        <cart v-on:pay="pay()" v-on:remove_item="removeFromCate($event)" :items="cart"></cart>
      </div>
      
    </div>
    
  </div>
</template>

<script>

  import products from '@/products.json';
  import product from '@/components/Product.vue';
  import cart from '@/components/Cart.vue';

  export default {
    name: 'app',

    components:{

      product,
      cart

    },

    data(){
      return {
        products,
        cart:[]
      }
    },

    methods:{

      addtoCart(product)
      {
        // console.log(product.price);
        this.cart.push(product);
      },
      isInTheCart(product)
      {
        const item = this.cart.find(item=>item.id==product.id);

        if(item)
        {
          return true;
        }
        else{
          return false;
        }
      },
      removeFromCate(product)
      {
        this.cart=this.cart.filter(item => item.id != product.id);
      },

      pay()
      {
        alert('payment completed');
        this.cart=[];
      }

    }
    
  }

</script>


<style >

  body{
    background-color: #a29bfe;
  }

</style>

