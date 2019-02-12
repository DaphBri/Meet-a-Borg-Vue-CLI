<template>

    <div id="container">
        <RobotItem 
        v-bind:data-gender="r.gender" 
        v-for="(r, index) in filteredRobots" 
        v-bind:key="index"
        v-bind:first_name="r.first_name"
        v-bind:last_name="r.last_name"
        v-bind:gender="r.gender"
        v-bind:index="index"
        v-bind:type="r.type"
        v-bind:language="r.language"
        v-bind:description="r.description"
        v-bind:portrait="r.portrait"
        />
    </div>
</template>

<script>
import RobotItem from './RobotItem.vue'


export default {
    props:['filteredRobots'],
    components: {
        RobotItem
    }
}
</script>

<style>

</style>
