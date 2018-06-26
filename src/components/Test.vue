<template>
    <div class="test">
        <input type="text" v-model="title"><br />
        <h1>{{title}}</h1>
        <p v-if="showName">{{user.firstName}}</p>
        <p v-else>Nobody</p>
        <ul>
            <li v-for="item in items" v-bind:key="item">{{item.title}}</li>
        </ul>
        <button v-on:click="greet">Say Greeting</button>
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
            showName: false,
            items:[
                {title: 'Item 1'},
                {title: 'Item 2'},
                {title: 'Item 3'},
                {title: 'Item 4'}
            ]
        }
    }
}
</script>
<style scoped>

</style>
