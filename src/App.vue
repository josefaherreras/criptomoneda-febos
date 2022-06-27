<template>
  <div id="app">
    <section id="home">
<nav class="navbar">
  <div class="container-fluid">
    <a class="navbar-brand"><img src="./assets/wrxCoin.9d1266c9.png" width="20%;" alt=""></a>
    <form class="d-flex">
      <p>Prueba técnica FEBOS - Desarrollo Front-end</p>
    </form>
  </div>
</nav>
      <div class="container">
        <div class="row">
          <div class="col-md-1"></div>
          <div class="col-md-10 mt-5">
            <h1 class="text-center">
              WAZIRX ES EL INTERCAMBIO DE crypCoin Y CRIPTOMONEDAS MÁS CONFIABLE
              DE LA INDIA
            </h1>
          </div>
          <div class="col-md-1"></div>
        </div>
      </div>
    </section>
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <table class="table table-borderless mb-5">
            <thead>
              <tr>
                <th scope="col">CRIPTOMONEDAS</th>
                <th>ULTIMO PRECIO</th>
                <th>PRECIO BAJO</th>
                <th>PRECIO ALTO</th>
                <th>PRECIO OFERTA</th>
              </tr>
            </thead>
            <Coin_component @showModal="showModal" v-for="i in crypCoin" :key="i.id" v-bind:monedas="i" />
          </table>
        </div>
      </div>
      <!-- Modal -->
      <div class="modal fade" v-if="modal" id="exampleModal" tabindex="-1" aria-hidden="true">
        <div class="modal-dialog " width="20%">
          <div class="modal-content">
            <div class="modal-header">
              <h4 class="modal-title">{{ cryptoOne.symbol }} - Criptomoneda</h4>
              <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
            </div>
            <div class="modal-body">
              <div class="row">
                <div class="col-md-12">
                  <p><span class="nombre-desc">Símbolo: </span> {{ cryptoOne.symbol }}</p>
                  <hr>
                  <p><span class="nombre-desc">Quote Asset: </span>  {{ cryptoOne.quoteAsset }}</p>
                  <hr>
                  <p><span class="nombre-desc">Precio de apertura: </span> US$ {{ cryptoOne.openPrice }}</p>
                  <hr>
                  <p><span class="nombre-desc">Precio Oferta: </span> US$ {{ cryptoOne.askPrice }}</p>
                  <hr>
                  <p><span class="nombre-desc">Quote Asset: </span>  {{ cryptoOne.quoteAsset }}</p>
                  <hr>
                  <p><span class="nombre-desc">Precio más ALTO: </span>  US$ {{ cryptoOne.highPrice}}</p>
                  <hr>
                  <p><span class="nombre-desc">Precio más BAJO: </span>  US$ {{ cryptoOne.lowPrice }}</p>
                  <hr>
                  <p><span class="nombre-desc">Último precio: </span>  US$ {{ cryptoOne.lastPrice }}</p>
                  <hr>
                  <p><span class="nombre-desc">Base Asset: </span> {{ cryptoOne.baseAsset }}</p>
                  <hr>
                  <p><span class="nombre-desc">Volumen transado: </span> {{ cryptoOne.volume }}</p>
                  <hr>
                  <p><span class="nombre-desc">Hora: </span> {{ cryptoOne.at}}</p>
                  <hr>
                </div>
              </div>
            </div>
            <div class="modal-footer">
              <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">
                Cerrar
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import moment from 'moment';
import Coin_component from "./components/Coin_component.vue";
export default {
  components: {
    Coin_component, // coin_component
  },
  data() {
    return {
      crypCoin: [],
      cryptoOne: {},
      modal: false,
    };
  },
  created() {
    this.fetch();
  },
  methods: {
    fetch() {
      let result = axios
        .get("https://api.wazirx.com/sapi/v1/tickers/24hr")
        .then((res) => {
          this.crypCoin = res.data;
          console.log(res.data);
        })
        .catch((err) => {
          console.log(err);
        });
    },
    showModal(s) {
      //id - fetchOne
      this.coinOne(s);
    },
    async coinOne(s) {
      //llamada HTTP
      let resultado = await axios.get(
        "https://api.wazirx.com/sapi/v1/ticker/24hr?symbol=" + s
      );
      this.cryptoOne = resultado.data;
      this.modal = true;

      console.log(this.cryptoOne, "moneda");
    },
    format_date(value) {
    if (value) {
        return moment(String(value)).format('MM/DD/YYYY hh:mm')
    }
  },
}
}
</script>
<style scoped>
#app {
  font-family: 'Montserrat', sans-serif;
}

#home {
  background-color: #3762fb;
  color: white;
  min-height: 700px;
}

table {
  box-shadow: 2px 11px 26px -7px rgba(0, 0, 0, 0.534);
  min-width: 95%;
  margin: auto;
  margin-top: -300px;
  background-color: white;
  border-radius: 20px;
  border-bottom-width: transparent;
}
thead tr th {
  padding: 20px;
}

.modal-footer button {
  background-color: #ff5050;
  border-radius: 30px;
  border: 1px solid #ff5050;
}

.modal-header {
  background-color: #65ce97;
  color: white;
  border-radius: 20px 20px 0px 0px;
}

.modal-header .modal-title {
  font-weight: 200;
}

.modal-content {
  border-radius: 20px;
}

.nombre-desc{
  font-weight: bold;
}
</style>
