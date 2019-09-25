<template>
    <span class="bubble" :class="{'me': from == 'me', 'loading': loading}">
        {{text}}
    </span>
</template>

<style lang="sass" scoped>
.bubble
    padding: 12px
    border-radius: 40px
    color: #202124
    border: 1px solid #E8EAED
    display: inline-block
    position: relative
    background-color: white

    &::before
        
        position: absolute
        left: 0
        top: 0
        margin-top: -9px
        margin-left: -1px

    &.me
        float: right
        background-color: #EAFBFF
        border: 1px solid #EAFBFF
        color: #5F6368
        margin-top: 24px

        &::before
            content: ''

        &::after
            
            position: absolute
            right: 0
            top: 0
            margin-top: -9px
            margin-right: -1px

    &.loading
        width: 20px
        height: 16px
        animation: loading .8s ease infinite

@keyframes loading
    0%
        opacity: 0
    50%
        opacity: 1
    100%
        opacity: 0
</style>

<script>
export default {
    name: 'Bubble',
    props: ['text', 'from', 'loading']
}
</script>
