<template>
     <div class="middle-block" id="middleBlock">
      <div class="middle-block__txt">
        <div class="title">Faites votre choix</div>

        <RobotCount 
        v-bind:malesCount="males.length"
        v-bind:femalesCount="females.length"
        />

        <div class="text">Robot ipsum Picoist encephaloform cortropic Filclinic Nippoploid kilolytic zoate. Vesicoity levoparous Egyptococcus stepsepalous stenoales sexuoling ochllyze xeraceae tarsorrhea taxthymia. Cytococcus cheirify gynaecoetic tristomy triboness bathyac conplastic siderogenesis ophioatory egenous. Myary cobaltofuge orphobe pneumonform Angloplex thalassoodont stethometric. Pathoholic newance poikilocline technographer desderma cuprless anthrostat hexgon cyanoicide. Pneumonozyme dendrism exbisect methylphage iridicoable hemoscope anthropomere.</div>
      </div>

      <FilterButtons 
      
       @filterTypes="filter($event)"
      />

    </div>
</template>

<script>
import RobotCount from './RobotCount.vue'
import FilterButtons from './FilterButtons.vue'

export default {
  props:['males', 'females'],

  components: {
        RobotCount,
        FilterButtons
},
  methods:{
      filter(type){
        console.log("filter in robotfilter")
          this.$emit('filterApp', type)
      }
  },
}
</script>

<style>

</style>
