<template>
    <h1>Conditional Rendering</h1>
    <p v-if="x === 0">The number is zero</p>
    <p v-else-if="x === 5">The number is {{ x }}</p>
    <p v-else>The number is not zero</p>
    <!-- wrapping the tags to avoid v-if code duplication -->
    <div v-if="display">
        <h6>Imen</h6>
        <h6>El Hakim</h6>
    </div>
    <!-- using template because div tag can cause problems in the layout -->
    <template v-if="display === true">
        <h6>Welyne</h6>
        <h6>Developper</h6>
    </template>
    <!-- v-show is more efficient than v-if because the rendered element remains in the DOM with display:none -->
    <h2 v-show="display">Using v-show</h2>
    <!-- passing props -->
    <div v-show="showCdtR">
        <h2>Heyyy</h2>
    </div>
    <h2>{{ message }}</h2>

</template>

<script>

export default{
    name: 'ConditionalRendering',
    data(){
        return{
            x: 5,
            display: true
        }
    },
    props:{
        showCdtR: {
            type: Boolean
        },
        message: {
            type: String
        }
    }
}
</script>

<style scoped>

</style>
