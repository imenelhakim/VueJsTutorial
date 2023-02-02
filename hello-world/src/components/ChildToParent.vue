<template>
    <h1>hey</h1>
    <input :value="newMessage" @input="updateMessage" />
</template>

<script>

export default{
    props: {
        newMessage:{         
            type: String,
            required: true
        }
    },
    methods:{
        updateMessage(event){
            this.$emit('update:message', event.target.value)
        }
    }
}
</script>

<style scoped>

</style>