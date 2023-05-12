<script setup>
import { ref } from 'vue'

const carrinho = ref([])
const produtos = ref([

    {

        id: 1,
        nome: 'TAYLOR SWIFT THE ERAS TOUR BEIGE HOODIE',
        preco: 75.00,
        quantidade: 0
    },
    {
        id: 2,
        nome: 'TAYLOR SWIFT THE ERAS TOUR BLACK SWEATPANTS',
        preco: 65.00,
        quantidade: 0
    },
    {
        id: 3,
        nome: 'TAYLOR SWIFT THE ERAS TOUR CROPPED BEIGE PULLOVER',
        preco: 65.00,
        quantidade: 0
    },
    {
        id: 4,
        nome: 'TAYLOR SWIFT THE ERAS TOUR MUG',
        preco: 20.00,
        quantidade: 0
    },
    {
        id: 5,
        nome: 'TAYLOR SWIFT THE ERAS TOUR GUITAR PICKS',
        preco: 15.00,
        quantidade: 0
    },
    {
        id: 6,
        nome: 'TAYLOR SWIFT THE ERAS TOUR POSTER',
        preco: 30.00,
        quantidade: 0
    },
    {
        id: 7,
        nome: 'TAYLOR SWIFT THE ERAS TOUR PORTABLE CHARGER',
        preco: 30.00,
        quantidade: 0
    }

]

)
const enviar = ref(false)

function addToCart(item) {
    if (item.quantidade === 0) {
        alert("Add the products first")
    } else {
        carrinho.value.push({...item})
        calcularCart()
    }


}
const valorCart = ref(0)
function calcularCart() {
    valortotal.value = item.preco * item.quantidade
    for (let index = 0; index < carrinho.value.length; index++) {
        valorCart.value = valorCart.value + carrinho.value[index].valortotal
    }
}

function addQtd(index) {
    produtos.value[index].quantidade++


}

function removeQtd(index) {
    if (produtos.value[index].quantidade > 0) { produtos.value[index].quantidade-- }

}

function cleanCart() {
    carrinho.value = []
    valorCart.value = 0
}

function remove(index) {
    carrinho.value.splice(index, 1)
    calcularCart()
}

function showCart() {
    if (carrinho.value < [0]) {
        alert('Empty Cart')
    } else {
        enviar.value = !enviar.value
    }
}


</script>



<template>
    <div>

        <ul>
            <li v-for="(item, index) in produtos" :key="index">
                <p>Item: {{ item.nome }}</p>
                <p>Price: {{ (item.preco) }}</p>
                <p>Amount: {{ item.quantidade }}</p>                    
                <button @click="addQtd(index)">+</button>
                <button @click="removeQtd(index)">-</button>
                <p><button @click="addToCart(item)">Add To The Cart</button>

                </p>
            </li>
        </ul>
        <button @click="(showCart)">Show Cart</button>
    </div>

    <div v-if="enviar">
        <ul>
            <li v-for="(item, index) in carrinho" :key="index">
                <p>Produto: {{ item.nome }}</p>
                <p>Preço:{{ (item.preco) }}</p>
                <p>Quantidade: {{ item.quantidade }}</p>
                <button @click="remove(index)">Remove Item</button>
            </li>
        </ul>

        <p>Total Price: {{ (valortotal) }}</p>
        <button @click="cleanCart()">Clean Cart</button>
        <button @click="enviar = !enviar"> Close Cart</button>

    </div>
</template>

