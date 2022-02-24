<template>
  <nav>
    <router-link to="/">Inicio</router-link> |
    <router-link to="/about">Sobre</router-link> |
    <router-link to="/warehouses">Galpoes</router-link> |
    <router-link to="/warehouses/new">Criar Galpao</router-link> |
    <span>{{ username }}</span>
  </nav>
</template>

<script>
export default {
  name: 'MenuView',
  props: ['username']
}
</script>
