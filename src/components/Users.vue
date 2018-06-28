<template>
    <div class="users">
       <h1>Users</h1>
       <form v-on:submit="addUser">
           <input type="text" v-model="newUser.name" placeholder="enter your name">
            <br />
            <input type="text" v-model="newUser.email" placeholder="enter your email">
            <br />
            <input type="submit" value="submit">
       </form>
       <ul>
           <li v-for="user in users" v-bind:key="user.name">
            <input type="checkbox" class="toggle" v-model="user.contacted">
            <span :class="{contacted: user.contacted}">
               {{user.name}}:{{user.email}}
               <button v-on:click="deleteUser">x</button>
            </span>
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
        addUser: function(e){
           // console.log('add');
           this.users.push({
               name: this.newUser.name,
               email: this.newUser.email,
               contacted: false
           });
            e.preventDefault();
        }, 
        deleteUser: function(){
           // console.log('delete this shit')
           this.users.splice(this.users.indexOf(user), 1);
        }
        
    },
}
</script>
<style scoped>
    .contacted{
        text-decoration: line-through;
    }
</style>
