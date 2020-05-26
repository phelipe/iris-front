<template>
<div class="container">
  <div class="row">
    <div class="col"></div>
    <div class="col-6">
      <div class="hello">
        <h1>IRIS</h1>
        <div>
          <div class="form-group row">
            <label for="exampleInputEmail1">Entrada 1</label>
            <input type="number" class="form-control" 
              placeholder="Petal Legth" v-model = "entrys.entry1"
              @keypress="isNumber($event)" step="0.001">
          </div>
          <div class="form-group row">
            <label for="exampleInputEmail1">Entrada 2</label>
            <input type="number" class="form-control" 
              placeholder="Enter email" v-model = "entrys.entry2" 
              @keypress="isNumber($event)" step="0.001">
          </div>
          <div class="form-group row">
            <label for="exampleInputEmail1">Entrada 3</label>
            <input type="number" class="form-control"
              placeholder="Enter email" v-model = "entrys.entry3" 
              @keypress="isNumber($event)" step="0.001">
          </div>
          {{entrys}}
          <button  class="btn btn-primary btn-lg btn-block" v-on:click="enviar()">Enviar</button>
        </div>  
      </div>
    </div>
    <div class="col"></div>
  </div>
</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function() {
    return  {
      entrys: {
        entry1: 1,
        entry2: 2,
        entry3: 2
      }
    }
  },
  methods: {
    teste: function () {
      console.log("teste")
    },
    enviar: function () {
      console.log("fdfdfaaaa")
      this.$http.post("http://localhost:8000/dados", this.entrys)
        .then(res => {
            //console.log("certo")
            this.result = res.body
          },
          res => {
            console.log(res)
            console.log("erro")
          }
        )
    },
    isNumber: function (evt) {
      evt = (evt) ? evt : window.event;
      var charCode = (evt.which) ? evt.which : evt.keyCode;
      if ((charCode > 31 && (charCode < 48 || charCode > 57)) && charCode !== 44) {
        evt.preventDefault();
      } else {
        return true;
      }
    }

  }
}
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
