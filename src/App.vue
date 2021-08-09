<template>
  <div id="app">
    <h1 style="text-align: center;color:grey;">ACCESSORIES</h1>
    <div class="row" style="text-align: center;">
      <span v-for="item in head" :key="item.id"> 
        <button class="btn success">{{item.name}}</button>
        </span>
    </div>
    <div class="product-row flex-space-between" style="margin-top: 30px" >
  <section>
    <div class="product-wrapper" v-for="item in products" :key="item.id">
      <div class="product-image-container">
            <!-- <span v-for="pictures in picture" :key="pictures"> -->
          <img :src="item.featured_image.src" alt="" 
          class="img-fluid" style="height: 100%; width: 100%; object-fit: cover;">
           <!-- </span> -->
        <div class="wishlist-control">
        <img src="@/assets/product-like.4dda6fe3.svg" alt="">
        </div>
        </div>
        <div class="product-data-wrapper">
        <div class="company-name-wrapper" >
            <h6>{{item.brand_info.name}}</h6>
      </div>
      <div class="product-name">{{item.name}}</div>
    <div class="product-price" style="margin-top: 50px; floa; float: left;" >
      <span>₹{{item.base_price.value}}
      </span>
      </div>
    </div>
    </div>
  </section>
</div>
          
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      user: null,
      products: Object,
      head: Object
    };
  },

  mounted() {
    this.getProduct();
    this.getHeader();
  },

  methods: {
    getProduct: function() {
      axios
        .get("https://run.mocky.io/v3/44831fd2-d7e9-4069-8d27-4829ad2e152e")
        .then((res) => {
          this.products = res.data;
        });
    },
    getHeader: function() {
      axios
        .get("https://run.mocky.io/v3/41c4ca6c-9071-4eda-aea8-50188abe37d4")
        .then((res) => {
          this.head = res.data;
        });
    },
  },
};
</script>

<style scoped>

#rcorners2 {
  border-radius: 25px;
  padding: 20px;
  width: 100px;
  height: 100px;
}


.flex-space-between {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.products-row {
  -moz-column-gap: 28px;
  column-gap: 28px;
  flex-wrap: wrap;
  justify-content: space-between;
}

.product-image-container {
  background-color: #eee;
  border-radius: 20px;
  height: 320px;
  width: 100%;
  display: block;
  overflow: hidden;
}

.product-wrapper {
  max-width: 300px;
  min-width: 150px;
  max-height: 800px;
  min-height: 300px;
  height: 100%;
  width: calc(25vw - 109px);
  position: relative;
  cursor: pointer;
  outline: none;
}

.company-name-wrapper h6 {
  background-color: #342546;
  color: #fff;
  font-weight: bolder;
  float: left;
  padding: 6px 12px;
  font-size: 12px;
  font-family: Gilroy-Bold;
  display: block;
  border-top-right-radius: 8px;
  border-bottom-right-radius: 8px;
  height: 15px;
  max-width: 126px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.company-name-wrapper {
  width: 100%;
  display: block;
  position: absolute;
  top: -16px;
}

.product-name {
  padding: 30px 15px;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  height: 38px;
  margin-top: 4px;
}

.product-name,
.product-price {
  color: #342546;
}

.product-data-wrapper {
  background-color: #fff;
  box-shadow: 3px 3px 10px rgb(0 0 0 / 10%);
  border-radius: 20px;
  width: calc(100% - 17px);
  margin-top: -15%;
  padding-top: 18px;
  padding-bottom: 12px;
  padding-bottom: 1px;
  position: relative;
  height: 100px;
}

.product-price {
  font-size: 13px;
  font-family: Edmondsans-Bold;
  padding: 0 15px;
  margin-top: 6px;
}

.grid {
  border: 1px solid #000;
  min-height: 100%;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
}
.grid > div {
  display: flex;
  flex-basis: calc(25% - 40px);
  justify-content: center;
  flex-direction: column;
}
.grid > div > div {
  display: flex;
  justify-content: center;
  flex-direction: row;
}

body {
  margin: 0;
}
.w {
  overflow: hidden;
}
section {
  margin: -1%;
  padding: 20px;
}
section div {
  /* background: whitesmoke; */
  float: left;
  height: 24vw;
  margin: 3%;
  width: 23%;
}
.btn {
  border: none;
  background-color: inherit;
  padding: 14px 28px;
  font-size: 20px;
  border-block: 1px;
  cursor: pointer;
  display: inline-block;
}

.btn:hover {background: #eee;}

.success {color: grey;}

</style>

//import HelloWorld from './components/HelloWorld.vue'
