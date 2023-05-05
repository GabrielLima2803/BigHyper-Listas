<script setup>
import { ref } from 'vue'
const produtos = ref([
    {
        id: 1,
        nome: 'Camiseta',
        quantidade: 0,
        preco: 49.90
    },
    {
        id: 2,
        nome: 'Calça',
        quantidade: 0,
        preco: 99.90
    },
    {
        id: 3,
        nome: 'Meia',
        preco: 9.90,
        quantidade: 0
    },
    {
        id: 4,
        nome: 'Sapato',
        quantidade: 0,
        preco: 199.90
    },
    {
        id: 5,
        nome: 'Boné',
        preco: 29.90,
        quantidade: 0
    },
    {
        id: 6,
        nome: 'Óculos',
        quantidade: 0,
        preco: 99.90
    },
    {
        id: 7,
        nome: 'Relógio',
        quantidade: 0,
        preco: 299.90
    },
    {
        id: 8,
        nome: 'Bermuda',
        quantidade: 0,
        preco: 79.90
    },
    {
        id: 9,
        nome: 'Cueca',
        quantidade: 0,
        preco: 19.90
    },
    {
        id: 10,
        nome: 'Meia',
        preco: 9.90,
        quantidade: 0
    }
]
)

// Carrinho
const carrinho = ref({
  items: [],
  total: 0
})
// Valor total 
let valorTotal = ref(0)
// Função adicionar carrinho
function adicionarCarrinho(produto) {
  carrinho.value.items.push({
    id: produto.id, 
    nome: produto.nome, 
    preco: produto.preco, 
    quantidade: produto.quantidade,
    total: produto.preco * produto.quantidade
  });
  carrinho.value.total += produto.preco * produto.quantidade
}
// Função adicionar item
function mais(index){
  produtos.value[index].quantidade++
  const pos = carrinho.value.items.indexOf(carrinho.value.items.find(c => c.id===produtos.value[index].id))
  if(pos != -1) {
    carrinho.value.total -= carrinho.value.items[pos].total
    carrinho.value.items[pos].total = ++carrinho.value.items[pos].quantidade * carrinho.value.items[pos].preco 
    carrinho.value.total += carrinho.value.items[pos].total
 
  }
}

function menos(index){
  produtos.value[index].quantidade--
}

</script>

<template>
<div class="container row">

  <!-- div que tem o v-for -->
 
<div v-for="(produto, index) in produtos" :key="produto.id"> 
 
  <div  class="tema col-3"> 
      <b> {{ produto.id }} - {{ produto.nome }} </b>
  <br>
  <h6>Preço: {{ produto.preco }}</h6>
  <h6>Quantidade: {{ produto.quantidade }}</h6>

    <button type="button" @click="menos(index)" class="btn bg-white p-1 h-r">-</button>
    <button type="button" @click="mais(index)" class="btn bg-white p-1 ml-b h-g">+</button>
    <button type="button" @click="adicionarCarrinho(produto)" class="btn bg-white p-1 ml-b h-g">Adicionar</button>
  </div>

<!-- FIM DIV FOR-V -->
</div>
<!-- FIM DIV.CONTAINER -->
{{  carrinho }}
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
    padding: 25px;
    color: white;
    border-radius: 15px;
    width: 30%;
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
