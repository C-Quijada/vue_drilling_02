<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-8 col-sm-6 ">
                <form>
                  <div class="form-group">
                    <label for="nombre">Nombre:</label>
                    <input v-model="nombre" type="text" class="form-control" placeholder="Ingrese su nombre" aria-describedby="emailHelp">
                  </div>
                  <div class="form-group">
                    <label for="">Apellido</label>
                    <input v-model="apellido" type="text" class="form-control" placeholder="Ingrese su apellido" aria-describedby="emailHelp">
                  </div>
                    <div class="form-group">
                      <label for="">Correo</label>
                      <input v-model="correo" type="email" class="form-control" placeholder="Ingrese su correo" aria-describedby="emailHelp">
                    </div>
                    <div class="form-group"> 
                      <label for="exampleInputPassword1">Edad</label>
                      <input v-model="edad" type="number" class="form-control" placeholder="Ingrese su edad">
                      <div v-if="registrado">
                        <div v-if="edad > 0 && edad < 14"> 
                          eres un niño
                        </div>
                        <div v-else-if ="edad > 13 && edad < 19"> 
                          eres un adolecente
                        </div>
                        <div v-else-if ="edad > 17  && edad < 36 "> 
                          eres un adulto joven
                        </div>
                        <div v-else-if ="edad > 34  && edad < 65 "> 
                          eres adulto
                        </div>
      
                        <div v-else-if ="edad > 63 "> 
                          eres tercera edad
                        </div>
                      </div>
                    </div>
                    
                    
                  </form>
                  <button v-on:click="registrar" type="submit" class="btn btn-primary">Registrar</button>
                  
                  

                    
                  
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'component-name',
    // props: {},
    data: function (){
        return {
          nombre: "",
          apellido: "",
          correo:"",
          edad:"",
          registrado: false,
        }
    },
    //computed: {},
    methods: {
      registrar()
      {
        if(this.nombre == ''){
          console.log('El nombre esta vacio')
          return
        }else if(this.apellido == ''){
          console.log('apellido esta vacio')
          return
        }else if(this.correo == ''){
          console.log('correo esta vacio')
          return
        }else if(this.edad == ''){
          console.log('edad esta vacio')
          return
        }
        this.registrado = true
        let saludo = `Saludos ${this.nombre} ${this.apellido}, tu correo es ${this.correo} y tu edad es ${this.edad} `
        alert(saludo)
        
      }
    },
    //watch: {},
    //component: {},
    //mixins: {},
    //filters: {},
    // --Lifecycle Methods
    // --End Lifecycle Methods
}

</script>

<style scoped>
    
</style>