<template lang="">
  <section id="products">
    <form action="" class="m-auto filter-form bg-black">
      <div class="filter-form-price">
        <label for="price-range">Price Range</label>
        <select name="price-range" id="price-range" class="m-auto" onchange="filterItems()">
          <option value="any">Any</option>
          <option value="1500">&#62 R1500</option>
          <option value="500">&#62 R500</option>
          <option value="200">&#62 R200</option>
        </select>
      </div>

      <div class="filter-form-color">
        <label for="base-color">Base Colour</label>
        <select name="base-color" id="base-color" class="m-auto" onchange="filterItems()">
          <option value="any">Any</option>
          <option value="black">Black</option>
          <option value="brown">Brown</option>
          <option value="blue">Blue</option>
          <option value="grey">Grey</option>
        </select>
      </div>

      <div class="filter-form-gender">
        <label for="gender">Gender</label>
        <select name="gender" id="gender" class="m-auto" onchange="filterItems()">
          <option value="any">Any</option>
          <option value="male">Male</option>
          <option value="female">Female</option>
        </select>
      </div>
    </form>

    <h2 class="text-center">Products:</h2>

    <div class="container products-grid">
      <div v-for="product in products" :key="product">
        <Card :name="product.itemName" :price="product.price" :imgSrc="product.imageSrc"/>
      </div>
    </div>

  </section>
</template>
<script>
import Card from '../components/Card.vue'
export default {
  components: {
    Card
  },
  data(){
    return {
      products: [
        {
          itemName: "men's cotton tshirt blue",
          id: 1,
          price: 199,
          stock: 100,
          color: 'blue',
          gender: 'male',
          imageSrc: 'https://i.postimg.cc/ncCCNvGM/mens-cotton-tshirt-blue.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
        {
          itemName: "men's cotton tshirt white",
          id: 2,
          price: 199,
          stock: 100,
          color: 'white', 
          gender: 'male',
          imageSrc: 'https://i.postimg.cc/rFmrM6MV/mens-cotton-tshirt-white.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
        {
          itemName: "men's leather jacket black",
          id: 3,
          price: 2699,
          stock: 100,
          color: 'black',
          gender: 'male',
          imageSrc: 'https://i.postimg.cc/pTRmS4st/mens-leather-jacket-black.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
        {
          itemName: "men's leather jacket brown",
          id: 4,
          price: 2499,
          stock: 100,
          color: 'brown',
          gender: 'male',
          imageSrc: 'https://i.postimg.cc/FRpYXp6k/mens-leather-jacket-brown.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
        {
          itemName: "women's denim top blue",
          id: 5,
          price: 129,
          stock: 100,
          color: 'blue',
          gender: 'female',
          imageSrc: 'https://i.postimg.cc/8P0rCyzh/womens-denim-top-blue.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
        {
          itemName: "women's leather jacket black",
          id: 6,
          price: 2699,
          stock: 100,
          color: 'black',
          gender: 'female',
          imageSrc: 'https://i.postimg.cc/SK026J8R/womens-leather-jacket-black.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
        {
          itemName: "women's leather jacket brown",
          id: 7,
          price: 2699,
          stock: 100,
          color: 'brown',
          gender: 'female',
          imageSrc: 'https://i.postimg.cc/MGycdqbD/womens-leather-jacket-brown.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
        {
          itemName: "men's cotton trousers cream",
          id: 8,
          price: 599,
          stock: 100,
          color: 'white',
          gender: 'male',
          imageSrc: 'https://i.postimg.cc/wxW1WWJS/mens-cotton-trousers-cream.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
        {
          itemName: "men's cotton trousers tan",
          id: 9,
          price: 599,
          stock: 100,
          color: 'brown',
          gender: 'male',
          imageSrc: 'https://i.postimg.cc/RhbqNF4M/mens-cotton-trousers-tan.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
        {
          itemName: "men's track pants grey",
          id: 10,
          price: 199,
          stock: 100,
          color: 'grey',
          gender: 'male',
          imageSrc: 'https://i.postimg.cc/RZJJJcW2/mens-track-pants-grey.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
        {
          itemName: "women's palazzo pants azure",
          id: 11,
          price: 479,
          stock: 100,
          color: 'blue',
          gender: 'female',
          imageSrc: 'https://i.postimg.cc/HnLVY5GZ/womens-palazzo-pants-azure.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
        {
          itemName: "women's track pants black",
          id: 12,
          price: 249,
          stock: 100,
          color: 'black',
          gender: 'female',
          imageSrc: 'https://i.postimg.cc/vH9mLxgC/womens-track-pants-black.jpg',
          description: `These comfortable socks from 'Happy Socks', are guaranteed to keep your feet satisfied.`
        },
      ]
    }
  }
}
</script>
<style>
  .products-grid {
  width: 80%;
  margin: auto;
  display: grid;
  grid-template-columns: repeat(3, auto);
  gap: 20px;
}

.products-grid>* {
  grid-column: span 1;
  margin: auto;
  width: 100% !important;
}

</style>