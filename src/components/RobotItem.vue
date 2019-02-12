<template>
 
      <div class="box">
        <p>{{first_name}} <strong>{{last_name}}</strong> ({{index}})</p>
        <div class="card" :class="gender" >
            <div class="type"><strong>Type: </strong>{{type}}</div>
            <img :src="portrait" alt="">
            <div class="language"><strong>Langue parlée :</strong> {{language}}</div>
        </div>
        <div class="description">{{description}}</div>
      </div>
    
</template>

<script>
export default {

props: ['first_name', 'last_name', 'gender', 'index', 'type', 'language', 'description', 'portrait' ]
}
</script>

<style>

</style>
