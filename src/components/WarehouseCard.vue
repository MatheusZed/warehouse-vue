<template>
  <div class="card">
    <table>
      <thead>
        <tr>
          <th>Nome</th>
          <th>Codigo</th>
          <th>CEP</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>{{ name }}</td>
          <td>{{ code }}</td>
          <td>{{ postal_code }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  props: {
    name: String,
    code: String,
    postal_code: String
  }
}
</script>

<style scoped>
  div.card {
    border: solid 1px #6e6e6e;
    padding: 1rem;
  }
</style>