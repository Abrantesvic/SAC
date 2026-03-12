
<template>
<div>
<h2>Login</h2>
<input v-model="email" placeholder="Email">
<input v-model="password" type="password">
<button @click="login">Entrar</button>
</div>
</template>

<script>
import api from "../services/api"

export default{

data(){
return{
email:"",
password:""
}
},

methods:{

async login(){

const res = await api.post("/auth/login",{
email:this.email,
password:this.password
})

localStorage.setItem("token",res.data.token)

alert("Login realizado")

}

}

}
</script>
