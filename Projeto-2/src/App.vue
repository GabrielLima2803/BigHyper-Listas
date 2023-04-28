<script setup>
import { ref } from 'vue'
const produtos = ref([
    {
        id: 1,
        nome: 'Camiseta',
        preco: 49.90
    },
    {
        id: 2,
        nome: 'Calça',
        preco: 99.90
    },
    {
        id: 3,
        nome: 'Meia',
        preco: 9.90
    },
    {
        id: 4,
        nome: 'Sapato',
        preco: 199.90
    },
    {
        id: 5,
        nome: 'Boné',
        preco: 29.90
    },
    {
        id: 6,
        nome: 'Óculos',
        preco: 99.90
    },
    {
        id: 7,
        nome: 'Relógio',
        preco: 299.90
    },
    {
        id: 8,
        nome: 'Bermuda',
        preco: 79.90
    },
    {
        id: 9,
        nome: 'Cueca',
        preco: 19.90
    },
    {
        id: 10,
        nome: 'Meia',
        preco: 9.90
    }
]
)

// Carrinho

const carrinho = ref([
    {
        id: 1,
        nome: 'Camiseta',
        preco: 49.90,
        quantidade: 1,
        valorTotal: 49.90
    },
    {
        id: 2,
        nome: 'Calça',
        preco: 99.90,
        quantidade: 2,
        valorTotal: 199.80
    },
    {
        id: 3,
        nome: 'Meia',
        preco: 9.90,
        quantidade: 4,
        valorTotal: 39.60
    }
    // total: 288.30
]
)


</script>

<template>
<div class="container row">

  <!-- div que tem o v-for -->
 
  <div v-for="(produto, id) in produtos" :key="id">{{ id }}: {{ produto.nome }}>

  </div>


  <div class="tema col-3">
    <p v-for="(produto, id) in produtos" :key="id">{{ id }}: {{ produto.nome }}</p>
    <p v-for="(produto, id) in produtos" :key="id">{{  }} Preço do produto: {{ produto.preco }}</p>
    <button type="button" class="btn bg-white p-1 h-r">-</button>
    <button type="button" class="btn bg-white p-1 ml-b h-g">+</button>
    <button type="button" class="btn bg-white p-1 ml-b h-g">Adicionar</button>
  </div>
  

  
</div>
</template>

<style scoped>

*{
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

/* .display-site{
  display: grid;
  grid-template-columns: auto auto auto auto;
  grid-template-rows: auto auto auto;
} */
.tema{
    background-color: black;
    padding: 30px 30px;
    color: white;
    border-radius: 15px;
    width: 30%;
    text-align: center;
    margin-top: 30px;
  }
  .ml-b{
    margin-left: 5px;
  }
  .h-g:hover{
    transition: 0.5s;
    color: rgb(16, 207, 63);
  }
  .h-r:hover{
    transition: 0.5s;
    color: rgb(255, 0, 0);
  }
</style>
