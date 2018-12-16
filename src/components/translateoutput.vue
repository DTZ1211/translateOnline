<template>
    <div id="translateOutput">
        <!-- 这里显示翻译之后的内容 -->
        <h2>{{ translatedText }}</h2>
    </div>
</template>

<script>
export default {
    name: 'translateOutput',
    props:[
        "translatedText"
    ]
}
</script>

<style>

</style>
