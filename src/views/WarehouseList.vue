<template>
  <div>
    <h1>Lista de Galpoes</h1>
    <div v-for="w in warehouses" :key="w.code">
      <WarehouseCard :name = w.name :code = w.code :postal_code = w.postal_code />
    </div>
  </div>
</template>
<script>
import WarehouseCard from '@/components/WarehouseCard.vue'
export default {
  name: 'WarehouseList',
  components: {
    WarehouseCard
  },
  data(){
    return {
      warehouses: []
    }
  },
  async mounted() {
    this.warehouses = await this.getWarehouses();
  },
  methods: {
    async getWarehouses() {
      const response = await this.$http.get('http://localhost:3000/api/v1/warehouses');
      return response.json();
    }
  }
}
</script>