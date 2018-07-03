<template>
   <div>
        <p class='color'>Name: {{botProp.name}}<p>
        <p>Attack: {{botProp.attack}}</p>
        <p>Health: {{botProp.health}}</p>
        <hr>
    </div>
        
</template>

<script>
    export default {
        props: ['botProp', 'name', 'attack', 'health']
        };
</script>

<style scoped>
</style>