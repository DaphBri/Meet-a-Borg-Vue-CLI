<template>
   <div class="middle-block__buttons">
        <div class="but tous" data-filter="All" @click="filter('')">Afficher tout le monde</div>
        <div class="but hommes" data-filter="Male" @click="filter('Male')">Afficher tout les hommes</div>
        <div class="but femmes" data-filter="Female" @click="filter('Female')">Afficher toutes les femmes</div>
        <!-- //data-xxx creation d'un atribut, n'importe lequel, semblabla a une classe+valeur -->
      </div> 
</template>

<script>
export default {
methods:{
   filter(type){
     console.log("filter in filterbuttons")
     this.$emit('filterTypes', type)
   }
}
}
</script>

<style>

</style>
