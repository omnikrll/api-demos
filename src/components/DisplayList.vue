<template>
    <ul>
        <li v-for="(fact, index) in yearfacts" v-bind:key="index">
           {{ fact }}
        </li>
    </ul>
</template>

<script>
export default {
    name: 'DisplayList',
    props: ['yearfacts']
}
</script>

<style lang="scss">
</style>