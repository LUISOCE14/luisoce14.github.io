<template>
    <div>
        <table class="striped centered">
        <thead>
          <tr>
             
              <th>Nombre de Ejercicio</th>
              <th>Series</th>
              <th>Repeticiones</th>
              <th>Completada</th>
              <th>Eliminar</th>
          </tr>
        </thead>

        <tbody>
          <tr v-bind:key="todo.id" v-for="todo in todoslist">
            <td>{{todo.title}}</td>   
            <td>{{todo.numSer}}</td>  
            <td>{{todo.numRep}}</td>    
            <td><label><input type="checkbox"  v-model="todo.completed"><span></span></label></td>
            <td><a href="#!"><i class="material-icons" @click="$emit('delete-todo', todo.id)">delete</i></a></td>
            
          </tr>
         
        </tbody>
      </table>
    </div>
</template>

<script>
    export default {
        name: 'Todos',
        props: ['todoslist'],
    }
</script>

<style></style>