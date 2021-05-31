<template>
    <div class="container">
        <div class="goods-list">
            <div v-for="item in filteredGoods" :key="item.id_product" class='goods-item'>
                <img src="https://via.placeholder.com/150x200" alt="test">
                <h3>{{item.product_name}}</h3>
                <p>{{item.price}}</p>
                <button @click="pushCart" class="item-cart-btn">Добавить</button>
            </div>
      </div>
    </div>
</template>

<script>

const API_URL = 'https://raw.githubusercontent.com/GeekBrainsTutorial/online-store-api/master/responses'
export default {
  data: () => ({
    goods: [],
    filteredGoods: [],
  }),
  mounted() {
    this.makeGETRequest(`${API_URL}/catalogData.json`)
  },
  methods: {
    makeGETRequest(url) {
      fetch(url)
        .then((data) => data.json())
        .then((data) => {
          this.goods = data;
          this.filteredGoods = data;
        })  
    },
    pushCart(){
        const pushCart = document.querySelector('.item-cart-btn');
        pushCart.classList.add('color')
        console.log(this.goods)
    }
  }
}

</script>

<style>
.goods-list {
    margin-top: 25px;
    margin-bottom: 25px;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    padding: 0 15px 0 15px;
    
}

.goods-item {
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    outline: 1px solid rgb(202, 194, 194);
}

.goods-item h3 {
    margin-top: 15px;
}

.goods-item p {
    margin-top: 15px;
}
.item-cart-btn {
    margin-top: 10px;
    width: 120px;
    height: 40px;
    background-color: rgb(202, 194, 194);
    /* border: 0; */
    border-radius: 30px;
}
.color{
    background-color: rgb(143, 58, 58);
    border: khaki;
}
</style>