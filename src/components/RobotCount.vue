<template>
    <div class="text">Il y a <span class="male"> {{malesCount}} hommes</span> et <span class="female"> {{femalesCount}} femmes</span> !</div>
</template>

<script>
export default {
    props:['femalesCount', 'malesCount']
}
</script>

<style>

</style>
