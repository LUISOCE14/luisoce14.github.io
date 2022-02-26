<template>
    <div id="add-container ">


<!-- Modal Structure -->
  <div id="modal1" class="modal">
    <div class="modal-content">
      <h4>Informacion Rutina</h4>
      <div class="row">
          <form class="col s12" >
         <div class="row">
            <div class="input-field col s12">
                    <input placeholder="Nombre del Ejercicio"  type="text" v-model="title">
            </div>
         </div>
          <div class="row">
        <div class="input-field col s6">
          <input placeholder="Series" type="number" v-model="numSer">
        </div>
        <div class="input-field col s6">
          <input  type="number"  placeholder="Repeticiones" v-model="numRep">
        </div>
      </div>
          </form>
      </div>
    </div>

    <div class="modal-footer">
      
      <button class=" btn modal-close waves-effect waves-green " v-on:click="addTodo"><a href="#!"></a>Agree</button>
    </div>


  </div>
          
    </div>
</template>

<script>
import { uuid } from 'vue-uuid';
export default {
    name: 'TodoAdd',
    data(){
        return {
            title: '',
            numSer: 0,
            numRep: 0
        }
    },
    methods:{
        addTodo(){
            
            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                numSer: this.numSer,
                numRep: this.numRep,
                completed: false
            };
            this.title = '';
            this.numSer = 0;
            this.numRep = 0;
            this.$emit('add-todo', newTodo);
        }
    }
}
</script>

<style scoped>
    #add-container{
        padding: 10px;
    }
    input{
        padding: 10px;
        outline: none;
        border: solid 1px #ccc;
        width: 100%;
    }
    h2{
        border-bottom: solid 2px #ccc;
    }
</style>