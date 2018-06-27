<template>
    <div class="users">
       <h1>Users</h1>
       <form v-on:submit="addUser">
           
       </form>
       <ul>
           <li v-for="user in users" v-bind:key="user.name">
               {{user.name}}:{{user.email}}
           </li>
       </ul>
    </div>
</template>


<script>
export default {
    name: 'users',
    
    data(){
        return {
            newUser: {},
            users: [
                {
                    name: 'Lotanna Nwose',
                    email: 'vic@gmail.com',
                    contacted: false
                },
                {
                    name: 'tanna Nse',
                    email: 'Nic@gmail.com',
                    contacted: false
                },
                {
                    name: 'Lotan Nwos',
                    email: 'vicy@gmail.com',
                    contacted: false
                },
            ]
        }
    },
    methods:{
        
    },
}
</script>
<style scoped>

</style>
