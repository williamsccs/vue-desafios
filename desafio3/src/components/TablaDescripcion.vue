<template>
    <div class="hello">
        <h1>{{ title }}</h1>
        <table>
            <tbody :style="{ 'background-color': colortitle, 'text-align': 'center' }" v-for="(row, name) in data"
                v-bind:key="name">

            </tbody>
            <tr v-if="name === 0">
                <th v-for="(ro, selected) in row" v-bind:key="selected">{{ selected }}</th>
            </tr>
            <tr v-for="(row, index) in data" :key="index"
                :style="{ 'background-color': (index % 2 === 0) ? background1 : background2, 'color': (index % 2 === 0) ? font1 : font2 }">
                <td v-for="(ro, k) in row" :key="k">{{ ro }}</td>
            </tr>
        </table>
    </div>
</template>
  
<script>
export default {
    name: 'TablaDescripcion',
    props: {
        data: Array,
        background1: String,
        background2: String,
        font1: String,
        font2: String,
        colortitle: String,
        title: String,
    }
}
</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

table,
td,
th {
    border: 1px solid black;
    /* text-align : center; */
}

table {
    border-collapse: collapse;
    width: 60%;
    margin-left: 20%;
}

td,
h1 {
    text-align: center;
}
</style>
  