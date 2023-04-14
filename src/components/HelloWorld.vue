<template>

  <h2 v-if="produtos.length > 0">Lista com {{ produtos.length }} produtos</h2>
  <h2 v-else>Lista vazia</h2>
  <fieldset>
    <ul v-if="produtos.length > 0">
      <li v-for="el in produtos">
        {{el.title  }}: {{ el.sub }} (R${{ el.valor }})
      </li>
    </ul>
    <span v-else>Não há produtos</span>
  </fieldset>
  
  <br>

  <h2 v-if="produtos.length > 0">Lista com {{ produtos.length }} produtos com clique</h2>
  <h2 v-else>Lista vazia</h2>
  <fieldset>
    <ul v-if="produtos.length > 0">
      <li v-for="produto in produtos">
        <Item v-bind="produto" />
      </li>
    </ul>
    <span v-else>Não há produtos</span>
  </fieldset>
</template>
<script lang="ts" setup>
  import Item from './Item.vue';
  const produtos = [
    {title: 'Pizza da mãe', sub: 'Saboroza pizza caseira', valor: 79.9},
    {title: 'Churrasquinho', sub: 'Delicioso espetinho', valor: 29.9},
    {title: 'Espaguete', sub: 'Apetitoso macarrão', valor: 59.9},
  ]
</script>
<style>
ul > li {
  text-align: left;
}
</style>