<template>
  <div class="container">
    <div class="content">
      <h1>Usuarios</h1>
      <table>
        <tr>
          <th>Nombre</th>
          <th>DNI</th>
          <th>Email</th>
          <th>Sexo</th>
          <th>Juego Fav</th>
          <th>Pais</th>
        </tr>
        <tr v-for="(row, index) in usuarios" :key="index"
          :style="{ 'background-color': (index % 2 === 0) ? 'gray' : 'darkgray', 'color': (index % 2 === 0) ? 'blue' : 'blue' }">
          <td v-for="(ro, k) in row" :key="k"> {{ ro | capitalize }}</td>
          <td contenteditable></td>
          <td contenteditable></td>
        </tr>
      </table>

    </div>
  </div>
</template>
  
<script>
export default {
  name: 'TablaFormulario',
  props: {
    usuarios: Object
  },
  filters: {
    capitalize: function (value) {
      if (!value) return ''
      value = value.toString()
      return value.charAt(0).toUpperCase() + value.slice(1)
    }
  }
}
</script>  

<style scoped>
a {
  color: #42b983;
}

label {
  margin-left: 0.5em !important;
}

.content {
  height: 100%;
  width: 100%;
  align-self: center;
  background-color: #CCFFFF;
  color: black;
  /* margin-left: 25%; */
  padding-bottom: 100px;
  margin-bottom: 50px;
}

.container {
  padding-bottom: 50px;
  margin-bottom: 200px;
}


td,
th {
  border: 1px solid black;
  width: 16%;
  /* text-align : center; */
}


table {
  border-collapse: collapse;
  width: 100%;
  /* margin-left: 20%; */
  border: 1px solid black;
}

td,
h1 {
  text-align: center;
}
</style>
  