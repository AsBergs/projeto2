<script setup>
import { ref }  from 'vue'

const carrinho = ref({})
const produtos = ref ({
  
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
    },
    {
        id: 8,
        nome: 'TAYLOR SWIFT THE ERAS TOUR VELVET COSMETIC BAG',
        preco: 35.00,
        quantidade: 0
    },
    {
        id: 9,
        nome: 'ALL TOO WELL NOTEBOOK',
        preco: 30.00,
        quantidade: 0
    },
    {
        id: 10,
        nome: 'TAYLOR SWIFT THE ERAS TOUR LUGGAGE STICKERS',
        preco: 15.00,
        quantidade: 0

    } 


)


function addToCart (id, nome, preco, quantidade){
if(quantidade == 0){
    alert("Add the products first")
} else{
    carrinho.value.push({id, nome, preco, quantidade})
   
}


}



</script>


