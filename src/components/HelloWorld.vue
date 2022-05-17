<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <table style="margin: auto; width:800px" class="table table-striped">
      <th style="width: 400px" v-for="(titulo, j) in titulos" :key="j">
        <tr>
          <td style="width: 800px">
            {{ titulo }}
          </td>
        </tr>
      </th>
      <tbody>
        <tr v-for="(fila, index) in usuarios" :key="index">
          <td v-for="(celda, index) in fila" :key="index" style="width: 200px">
            {{ celda }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",

  data() {
    return {
      msg: "Tabla props - Pablo Bustos",
      titulos: ["ID", "Nombre", "Apellido", "Edad", "País"],

      usuarios: [
        {
          id: 1,
          nombre: "Pablo",
          apellido: "Bustos",
          edad: 25,
          pais: "Colombia",
        },
        {
          id: 2,
          nombre: "Juan",
          apellido: "Perez",
          edad: 30,
          pais: "Peru",
        },
        {
          id: 3,
          nombre: "Pedro",
          apellido: "Gonzalez",
          edad: 35,
          pais: "Brasil",
        },
      ],
      props: {
        titulos: {
          type: Array,
          required: true,
        },
      },
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
