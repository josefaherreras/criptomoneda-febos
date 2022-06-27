<template>
  <tbody>
    <tr :key="monedas.id">
      <td> <img src="../assets/wrxCoin.9d1266c9.png" width="25px" alt=""> <span class="crypto">{{ monedas.symbol }}</span></td>
      <td>{{monedas.lastPrice}}</td>
      <td>{{monedas.lowPrice}}</td>
      <td>{{monedas.highPrice}}</td>
      <td>
        <button class="btn btn-vermas" @click="showMore(monedas.symbol)" type="button"  data-bs-toggle="modal"
                    data-bs-target="#exampleModal">
          Más detalles
        </button>
      </td>
    </tr>
  </tbody>
</template>
<script>
export default {
  props: ["monedas"],
  methods:{
    showMore(s){
        this.$emit('showModal', s)
    }
  }
};
</script>
<style>
.btn-vermas{
  background-color: #65ce97;
  color: white;
  border-radius: 30px;
  font-weight: bold;
}
tbody tr td{
  padding: 15px 20px !important;
}

.crypto{
  font-weight: bold;
}
</style>