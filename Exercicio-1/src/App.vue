<script setup>
import { ref } from 'vue'

const cidades = ref([    
    'São Paulo',
    'Rio de Janeiro',
    'Belo Horizonte',
    'Salvador',
    'Fortaleza',
    'Curitiba',
    'Manaus',
    'Recife',
    'Porto Alegre',
    'Brasília'
    ]
    )
</script>

<template>
  <div class="display">
  <div class="container tema">
    <h1>Exercicio-1</h1>
    <hr>
    <ul>
      <li v-for="(cidade, index) in cidades" :key="index">{{ cidade }}</li>
    </ul>
  </div>
</div>
</template>

<style scoped>
 .tema{
    background-color: black;
    padding: 30px 30px;
    color: white;
    border-radius: 15px;
    width: 30%;
    text-align: center;
    margin-top: 15%;
  }
</style>
