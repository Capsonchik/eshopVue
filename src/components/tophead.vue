<template>
    <div class="container">
        <div class="top">
            <h1>eShop</h1>
            <div class="top-search">
                <input @click="FilterGoods" type="text" name="search" id="search">
                <button class="search-btn">search</button>
            </div>
            <button @click="hidden" class="cart-button" type="button">Корзина</button>
            <div class="top-cart">
                
            </div> 
        </div>
    </div>
</template>

<script>


export default {
    methods: {
        hidden(){
            const cartcl = document.querySelector('.top-cart');
            cartcl.classList.toggle('hidden')
            console.log(this.FilterGoods)
        },
        FilterGoods(){
            
        }

        
    }
}
</script>

<style>
.header {
    padding-top: 15px;
}

.top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: rgb(202, 194, 194);
    padding: 15px;
}

.cart-button {
    background-color: #fff;
    width: 100px;
    height: 35px;
    border: 0;
    border-radius: 30px;
    cursor: pointer;
}

.cart-button:hover {
    background-color: rgb(230, 141, 141);
}

.top-cart {
    position: absolute;
    width: 300px;
    height: 300px;
    background-color: rgb(230, 141, 141);
    z-index: 10;
    top: 125px;
    right: 140px;
}

.hidden {
    opacity: 0;
}

</style>