<template lang="html">

  <div>
      <h2>Conversor de Temperatura</h2>
      <p>Ingrese temperatura °C <input type="number" v-model="temperaturaCelcius" ></p>
      <p>Conv. temperatura °F: <span :style="{ color: colorInputCelcius }">{{ conversionTemperatura.temperaturaFarenheit }}</span> </p>
      <p>Conv. temperatura °K: <span :style="{ color: colorInputCelcius }">{{ conversionTemperatura.temperaturaKelvin }}</span> </p>
      <p>Respuestas: 1:c 2:b 3:c 4:a 5:b  </p>
  </div>   

</template>

<script lang="js">

export default  {
  name: 'conversor-component',
  props: [],
  mounted () {
    
  },
  data () {
    return {
      temperaturaCelcius: 0
    }
  },
  methods: {

  },
  computed: {
    conversionTemperatura() {
      return {
        temperaturaFarenheit: ((this.temperaturaCelcius * 9/5) + 32).toFixed(2),
        temperaturaKelvin: (Number(this.temperaturaCelcius)  + 273.15).toFixed(2)
      }
    },
    colorInputCelcius(){
      var color = ""

      if(this.temperaturaCelcius <= 0){
        color = "blue"
      }
      else if(this.temperaturaCelcius >= 15){
        color = "red"
      }
      else{
        color = "magenta"
      }

      return color
    }
  }
}


</script>

<style scoped lang="css">
  .conversor-component {

  }
</style>
