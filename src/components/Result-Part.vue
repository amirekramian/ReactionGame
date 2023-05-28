<template>
    <div>
        <h2>your result:</h2>
        <h1>{{result}} ms</h1>
        <br>
        <h1>
            <span v-if="result<=150">fucking rapid</span>
            <span v-if="result<210 && result>150">not bad</span>
            <span v-if="result>210">ridiiii</span>

        </h1>
    </div>
</template>

<script>
export default {
props:['result']
}
</script>

<style lang="css" scoped>
h2{
    color: #250069;
}
h1{
    color: #00b35f;
}
</style>>

