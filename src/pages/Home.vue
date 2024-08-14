<template>
    <div>
        
        <h1 class="title">Введите логин и пароль</h1>
                <!-- <p v-if="!isAuth">вы не авторизованы</p> -->

                <div class="form-floating">
                <input 
                    v-model="username"
                    type="text" 
                    class="form-control"  placeholder="username">
                
                </div>
                <div class="form-floating">
                <input 
                    v-model="password"
                    type="password" 
                    class="form-control"  placeholder="Password">
                
                </div>
        <my-button @click="listMessage">Получить message</my-button>
        <div v-if="f_str" class="users">
            <div v-for="val in f_str.action['data']" :key="val">
                <div>{{ val.dt}} - dt</div>
                <div>{{ val.subject}} - subject</div>
                <div>{{val.text}} - text</div>
                <br>
            </div>
        </div>
        
    </div>
</template>

<script>
import UserService from '@/services/UserService'
export default {
    data: ()=>{
        return {
            list_users: [],
            dic_users: [],
            connection: null,
            f_str: null,
            username: '',
            password: '',
        }
    },
    methods:{

    },
}
</script>

<style scoped>

</style>