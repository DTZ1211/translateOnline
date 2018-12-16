<template>
    <div id="translateInput">
        <form v-on:submit='formsubmit'>
            <!-- <input type="text" v-model="translateInput" placeholder="输入需要翻译的内容"> -->
            <el-input v-model="translateInput" placeholder="输入需要翻译的内容"></el-input>
            <select v-model="language">
                <option value="zh">中文</option>
                <option value="la">拉丁语</option>
                <option value="ko">韩语</option>
                <option value="en">英语</option>
                <option value="ja">日语</option>
            </select>
            <input type="submit" value="翻译" />
        </form> 
    </div>
</template>

<script>
export default {
    name: 'translateInput',
    data:function(){
        return{
            translateInput:"",
            language: ""
        }
    },
    methods:{
        formsubmit:function(e){
            // alert(this.translateInput);
            this.$emit("formtranslate",this.translateInput,this.language);
            //取消默认页面刷新事件
            e.preventDefault();
        }
    }
}
</script>

<style>

</style>
