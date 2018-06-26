<template>
    <div class="test">
        <h1>{{title}}</h1>
        <p v-if="showName">{{user.firstName}}</p>
        
    </div>
</template>


<script>
export default {
    name: 'test',
    data(){
        return{
            title: 'Hello Man',
            user: {
                firstName: 'Lotanna',
                lastName: 'Nwose'
            },
            showName: false
        }
    }
}
</script>
<style scoped>

</style>
