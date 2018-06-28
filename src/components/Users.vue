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
               <button v-on:click="deleteUser(user)">x</button>
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
            users: []
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
        deleteUser: function(user){
           // console.log('delete this shit')
           this.users.splice(this.users.indexOf(user), 1);
        }
        
    },
    created: function(){
        //console.log('created ran oh...')
        this.$http.get('https://jsonplaceholder.typicode.com/users')
            .then(function(response){
                this.users = response.data;
            });
    }
}
</script>
<style scoped>
    .contacted{
        text-decoration: line-through;
    }
</style>
