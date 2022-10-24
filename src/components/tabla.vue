<template>
  <div>
    <h2>Tabla Vehiculos</h2>
    <table class="table" id="datatable">
      <thead>
      <tr>
        <th>ID</th>
        <th>Modelo</th>
        <th>Año Fabricación</th>
        <th>Fabricante</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="vehiculo in vehiculos" :key="vehiculo.id">
        <td>{{ vehiculo.id }}</td>
        <td>{{ vehiculo.modelo }}</td>
        <td>{{ vehiculo.fabricacion }}</td>
        <td>{{ vehiculo.fabricante.nombre }}</td>
      </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
import "jquery/dist/jquery.min.js";
import "bootstrap/dist/css/bootstrap.min.css";
import "datatables.net-dt/js/dataTables.dataTables";
import "datatables.net-dt/css/jquery.dataTables.min.css";
import axios from "axios";
import $ from "jquery";
export default {
  mounted() {
    axios.get("/vehiculo/list").then((response) => {
      this.vehiculos = response.data;
      console.log(response.data);
      $("#datatable").DataTable();
    });
  },
  data: function () {
    return {
      vehiculos: [],
    };
  },
};
</script>