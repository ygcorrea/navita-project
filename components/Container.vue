<template>
  <div class="container-style">
    <div class="table-title">
      <span> Veículos</span>
    </div>
    <div class="flex-div">
      <div class="main-table">
        <div class="table-style">
          <div class="brand">
            <div class="brand-title">Marcas</div>
          </div>
          <div class="brand-container">
            <div class="brand-main">
              <div class="brand-header">
                <span> Marca </span>
              </div>
              <div class="main-container">
                <div class="item-container">
                  <div v-for="item in brands" :key="item" class="item-text">
                    <div class="content">
                      {{ item.nome }}
                    </div>
                  </div>
                </div>
                <div class="item-container">
                  <div v-for="item in brands" :key="item" class="item-text">
                    <button
                      class="button-model"
                      :class="{ changeColor: changeC }"
                      @click="
                        getModel(item.codigo)
                        showModels()
                      "
                    >
                      Ver modelos
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div v-if="clicked" class="main-table-models">
        <div class="table-style">
          <div class="brand">
            <div class="brand-title">Modelos</div>
          </div>
          <div class="brand-container">
            <div class="brand-main">
              <div class="brand-header">
                <span> Modelo </span>
              </div>
              <div class="main-container">
                <div class="item-container">
                  <div v-for="item in models" :key="item" class="item-text">
                    <div class="content">
                      {{ item }}
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      changeC: false,
      brands: [],
      clicked: false,
      models: [],
      codigo: null,
    }
  },
  created() {
    axios
      .get(`https://parallelum.com.br/fipe/api/v1/carros/marcas`)
      .then((response) => {
        this.brands = response.data
      })
  },
  methods: {
    showModels() {
      this.clicked = true
      this.changeC = true
    },
    getModel(codigo) {
      axios
        .get(
          `https://parallelum.com.br/fipe/api/v1/carros/marcas/${codigo}/modelos`
        )
        .then((res) => {
          const modelsList = res.data.modelos.map((cod) => cod.nome)

          this.models = modelsList
        })
    },
  },
}
</script>
<style>
button {
  background: none;
  border: none;
  outline: none;
  text-decoration: none;
  cursor: pointer;
  color: #4e73df;
}

.content {
  margin-left: 13px;
}
.flex-div {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 640px;
}
.button-model {
  font-weight: 600;
}
.item-container {
  display: flex;
  flex-direction: column;
  width: 100%;
  font-size: 0.9em;
}
.changeColor {
  color: #1cc88a;
}
.main-table {
  display: flex;
  align-items: center;
  justify-content: center;
}
.main-table-models {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 40px;
}
.brand-main {
  padding: 20px;
  min-height: 195px;
}
.item-text {
  height: 50px;
  border-top: 1px solid #e3e6f0;
  align-items: center;
  display: flex;
  width: 100%;
}
.brand-header {
  width: 100%;
  border-top: 1px solid #e3e6f0;
  height: 40px;
  display: flex;
  align-items: center;
  font-weight: 700;
}
.main-container {
  display: flex;
  flex: 1;
  width: 100%;
}
.container-style {
  background: #f7f8fb;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.container-style span {
  font-size: 1.65em;
  margin-left: 6px;
}
.table-title {
  margin: 20px;
}
.table-style {
  padding: 2px;
  border: 1px solid #e3e6f0;
  border-radius: 5px;
  box-shadow: 0px 0px 20px rgba(58, 59, 69, 0.15);
  width: 95%;
  align-items: center;
  justify-content: center;
}
.brand {
  display: flex;
  align-items: center;
  height: 60px;
  background-color: #f8f9fc;
  border-bottom: 1px solid #e3e6f0;
}
.brand-title {
  margin-left: 15px;
  font-size: 1.03em;
  color: #4e73df;
  font-weight: 900;
  width: 2px;
}
.brand-container {
  background-color: #ffffff;
  color: #5a5c69;
  /* height: 300px; */
}
.brand-header span {
  font-size: 0.9em;
  margin-left: 14px;
}
</style>
