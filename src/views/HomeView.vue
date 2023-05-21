<script>
import { RouterLink, RouterView } from 'vue-router'
export default{
    components:{

    },
    data(){
        return{
            text:""

        }
    },
    methods:{
        save(){
            localStorage.setItem("account",this.text)
            console.log("save")

            this.$router.push('/left');
        }

    }
}
</script>

<template>
    <div class="center">
        <div>
            <h1>記帳系統</h1>
        </div>
        
        <div>
            <p>輸入帳號</p>
            <input type="text" v-model="text">
        </div>
        <div>
            <p>輸入密碼</p>
            <input type="passeord">
        </div>
        <div class="flex">
            <button>log out</button>
            <button @click="save">left</button>
        </div>
    </div>
</template>

<style lang="scss" scoped>

.center{
    align-items: center;
    justify-content: center;
    text-align: center;
    width: 500px;
    height: 500px;
    background-color: aquamarine;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    .flex{
        justify-content: space-between;
        padding: 20px;
    }
}
</style>