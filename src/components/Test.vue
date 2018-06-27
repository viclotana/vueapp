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
        <br />
        <input type="text" v-on:keyup="pressed">
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
    },
    methods:{
        greet: function(){
            alert("hi man");
        },
        pressed: function(e){
            console.log(e.target.value);
        }
    }
}
</script>
<style scoped>

</style>
