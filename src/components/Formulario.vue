<template>
  <div class="form">
    <h1>{{ msg }}</h1>
    <p>soy un component</p>
    <div class="formulario">
      <div class="div">
        <p>{{ errors }}</p>
      </div>
      <div class="div">
        <label for="consumo">Consumo: </label>
        <input
          id="consumo"
          v-model="consumo"
          type="number"
          name="consumo"
          min="0"
        />
      </div>
      <div class="div">
        <label for="movie">Seleccione lugar: </label>
        <select id="lugar" v-model="lugar" name="lugar">
          <option value="hogar">Hogar</option>
          <option value="empreza">Empresa</option>
        </select>
      </div>
      <div class="div">
        <label for="pago">Pago: </label>
        <input id="pago" v-model="pago" type="number" name="pago" min="0" />
      </div>
      <div class="div">
        <button v-on:click="checkForm">Enviar</button>
      </div>
      <div class="div">
        <p>Resultado: {{ resultado }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Formulario",
  props: {
    msg: String,
  },
  data() {
    return {
      errors: "",
      pago: null,
      consumo: null,
      lugar: "hogar",
      resultado: null,
    };
  },
  methods: {
    checkForm: function (e) {
      if (this.consumo && this.pago) {
        //var numeroObtenido  lugar_selected === 'H' ? (this.resultado = this.consumo) * 1 = this.pago; : (this.resultado = this.consumo) * 1 = this.pago;
        if (this.lugar === "hogar") {
          this.resultado = (this.pago - this.consumo) * 2;
        } else {
          this.resultado = (this.pago + this.consumo) / 3;
        }
        /*this.lugar === "hogar" ? () => {
            this.resultado = (this.pago - this.consumo ) * 2;

          }:() => {
            this.resultado = (this.pago + this.consumo ) / 3;
          }*/
        this.errors = "";
        return true;
      }
      if (!this.consumo || !this.pago) {
        this.errors = "Llenar todos los campos";
        console.log(this.errors);
        //this.errors.push('Llenar todos los campos');
      }
      /*if (!this.pago) {
        this.errors.push('El pago es obligatoria.');
      }

      if (!this.pago) {
        this.errors.push('El pago es obligatoria.');
      }*/

      e.preventDefault();
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/*
.formulario{
  width:40%;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
}*/
.div {
  margin: 15px;
}
button {
  background-color: #42b983;
  border: none;
  padding: 10px 20px;
}
button:hover {
  background-color: #86e2c2;
  border: none;
  color: #2c3e50;
  padding: 10px 20px;
}
</style>
