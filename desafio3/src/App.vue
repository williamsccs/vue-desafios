<template>
  <div id="app">
    <TablaDescripcion :data="users" background1="gray" background2="yellow" font1="blue" font2="red" colortitle="green"
      title="Tabla Usuarios">
    </TablaDescripcion>

    <TablaDescripcion :data="animal" background1="red" background2="black" font1="brow" font2="green" colortitle="#FCC"
      title="Tabla Animales">
    </TablaDescripcion>

    <TablaDescripcion :data="juegos" background1="gray" background2="darkgray" font1="yellow" font2="red"
      colortitle="lightgray" title="Tabla de Juegos">
    </TablaDescripcion>
  </div>
</template>

<script>
import TablaDescripcion from './components/TablaDescripcion.vue'


export default {
  name: 'App',
  components: {
    TablaDescripcion
  },
  data: function () {
    return {

      users: [
        {
          "ID": "01",
          "Usuario": "Williams Fuentes",
          "Clave": "admin",
          "Correo": "Williamsfuentes@gmail.com",
          "Telefono": 23876060,
          "Habilitado": true
        },
        {
          "ID": "02",
          "Usuario": "Batman",
          "Clave": "Robin",
          "Correo": "BatmanyRobin@gmail.com",
          "Telefono": 50505050,
          "Habilitado": true
        },
        {
          "ID": "03",
          "Usuario": "Rick Sanchez",
          "Clave": "Morty",
          "Correo": "rickymorty@gmail.com",
          "Telefono": 123465348,
          "Habilitado": true
        },
        {
          "ID": "04",
          "Usuario": "Bruce Wayne",
          "Clave": "admin",
          "Correo": "bruceWayne@hotmail.com",
          "Telefono": 12121212,
          "Habilitado": true
        },
        {
          "ID": "05",
          "Usuario": "Chris Redfield",
          "Clave": "admin",
          "Correo": "CRedfield@umbrellacorp.com",
          "Telefono": 34353636,
          "Habilitado": false
        },
      ],
      animal: [
        {
          Nombre: "Murcielago",
          Tipo: "Volador",
          Color: "Negro"
        },
        {
          Nombre: "Dalmata",
          Tipo: "Perro",
          Color: "Manchas"
        },
        {
          Nombre: "Chupacabras",
          Tipo: "Desconocido",
          Color: "Desconocido"
        },
      ],
      juegos: [
        {
          Titulo: "Metal Gear",
          Consola: "Playstation 1",
          Release: "1998",
          Puntuacion: "9/10"
        },
        {
          Titulo: "Super Mario 64",
          Consola: "Nintendo 64",
          Release: "1996",
          Puntuacion: "10/10"
        },
        {
          Titulo: "Cyber Punk 2077",
          Consola: "Playstation 5",
          Release: "2021",
          Puntuacion: "4/10"
        },
        {
          Titulo: "God of War 3",
          Consola: "Playstation 3",
          Release: "2008",
          Puntuacion: "8/10"
        },
        {
          Titulo: "Destiny 2",
          Consola: "Playstation 4",
          Release: "2017",
          Puntuacion: "10/10"
        },
        {
          Titulo: "dead Space",
          Consola: "Playstation 3",
          Release: "2007",
          Puntuacion: "8/10"
        },
      ],
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
