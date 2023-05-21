<script>
import PopUp from "../components/PopUp.vue"
import From from "../components/From.vue"
export default{
    components:{
        PopUp,
        From
        
    },
    data(){
        return{
            isShow:false,
            account: null
        }
    },
    methods:{
        change(){
            this.isShow = !this.isShow
        }
        
    },
    mounted(){
        // console.log("mounted")
        this.account = localStorage.getItem("account")
    }
    
}
</script>

<template>
    <div class="total">
        <div class="left">
            <!-- 之後要改變樹 -->
            <h1>記帳系統</h1>
            <h2>{{account}}</h2>
            <h2>收支平衡</h2>
            <h2>金額</h2>
        </div>
        <div class="right">
            <div class="top">
                <div>
                    <h2>收入</h2>
                    <h2>11323232</h2>
                </div>
                <div>
                    <h2>支出</h2>
                    <h2>11323232</h2>
                </div>
            </div>
            <div class="top">
                <button type="button" @click="change">add</button>
                <button>delete</button>
            </div>
            <div class="from">
                <From />
            </div>  
            
        </div>
    </div>
    <PopUp v-if="isShow"
    @switch = "change"/>
    
    
</template>

<style lang="scss" scoped>
.total{
    display: flex;
    
    .left{
        width: 30vw;
        height: 100vh;
        background-color: beige;
        display: flex;
        text-align: center;
        justify-content: center;
        display: grid;
        // align-items: center;
    }
    .right{
        width: 70vw;
        height: 100vh;
        .top{
            margin-top: 100px;
            justify-content: space-around;
            display: flex;
        }
        .from{
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 50px 7%;

        }
        
    }
}
</style>