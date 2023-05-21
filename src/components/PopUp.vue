<script>
export default{
    components:{

    },
    data(){
        return{
          
                textData:"",
                numberData:"" 
        }
    },
    methods:{
        close(){

            const info = {
                
            }

            localStorage.setItem("item",this.textData);
            localStorage.setItem("money",this.numberData)

            this.$emit("switch")
        }
    }

}
</script>

<template>
    <div class="box">
    </div>

    <div class="box2">
        <div class="top2">
            <p>{{ textData }}</p>
            <p>{{ numberData }}</p>
            <p>輸入項目</p>
            <input type="text" v-model="textData">
        </div>
        <div>
            <p>輸入金額</p>
            <input type="number" v-model="numberData">
        </div>
        <div class="flex">
            <button type="button"
            @click="close"
            >要確定ㄟ!!</button>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.box{
    width: 100vw;
    height: 100vh;
    position: fixed;
    top: 0px;
    left: 0px;
    background-color: black;
    opacity: 0.5;
}
.box2{
    width: 500px;
    height: 500px;
    background-color: aliceblue;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50% , -50%);
    border-radius: 30px;
    justify-content: center;
    text-align: center;
    .top2{
        margin-top: 100px;
    }
    .flex{
        padding: 20px;
    }
}
</style>