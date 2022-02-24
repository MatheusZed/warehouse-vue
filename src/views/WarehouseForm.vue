<template>
  <div>
    <h1>Novo Galpao</h1>
    <div>{{ msg }}</div>
    <form v-on:submit.prevent="postWarehouse">
      <input v-model="form.name" placeholder="nome">
      <input v-model="form.code" placeholder="codigo">
      <input v-model="form.description" placeholder="descricao">
      <input v-model="form.address" placeholder="endereco">
      <input v-model="form.city" placeholder="cidade">
      <input v-model="form.state" placeholder="estado">
      <input v-model="form.postal_code" placeholder="cep">
      <input v-model="form.total_area" placeholder="area total">
      <input v-model="form.useful_area" placeholder="area util">
      <input type="submit" value="Enviar" />
    </form>
  </div>
</template>
<script>
export default {
  name: 'WarehouseForm',
  data() {
    return {
      msg: null,
      form: {
        name: null,
        code: null,
        description: null,
        address: null,
        city: null,
        state: null,
        postal_code: null,
        total_area: null,
        useful_area: null,
      },
      product_category_ids: [ 2 ]
    }
  },
  methods: {
    async postWarehouse(){
      try {
        await this.$http.post("http://localhost:3000/api/v1/warehouses", {
        name: this.form.name,
        code: this.form.code,
        description: this.form.description,
        address: this.form.address,
        city: this.form.city,
        state: this.form.state,
        postal_code: this.form.postal_code,
        total_area: this.form.total_area,
        useful_area: this.form.useful_area,
        product_category_ids: this.product_category_ids
        });
        this.msg = "Galpao cadastrado"
        this.form = {}
      }
      catch(error){
        const error_msg = await error.json();
        this.msg = error_msg;
      }
    }
  }
}
</script>
