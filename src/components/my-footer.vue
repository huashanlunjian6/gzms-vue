<template>
    <div id="my_footer">
        <mt-tabbar v-model="tabbar" fixed>
            <mt-tab-item id="index" >
                    首页 
                    <img src="..\assets\footer-images\index_enabled.png" slot="icon" v-if="tabbar=='index'" >
                    <img src="..\assets\footer-images\index_disabled.png" slot="icon"  v-else alt="">  
            </mt-tab-item>
            <mt-tab-item id="me" class="MyFontStyle">
                    我的
                <img src="..\assets\footer-images\me_enabled.png" slot="icon" v-if="tabbar=='me'" alt="">
                <img src="..\assets\footer-images\me_disabled.png" slot="icon" v-else alt="">
            </mt-tab-item>    
        </mt-tabbar>
    </div>
</template>
<style scoped>
    .MyFontStyle{
        color: #707070;
    }
    .mint-tabbar>.is-selected{
        color:#aa5 ;
    }
</style>
<script>
export default {
    data(){
        return{
            tabbar:'index'
        }
    },
   watch:{
       tabbar(value){
        //    console.log("123"+value);
           if(value=='me'){
               this.$router.push('/me').catch(e=>{});
                console.log(this.tabbar);
           }else if(value=='index'){
               this.$router.push('/').catch(e=>{});
               console.log( this.tabbar);
           }
       }

   }
}
</script>