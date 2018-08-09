<template>
<div class="layout__content">
    <slot name="header" :item="headerData">----------header is not implemented-----------</slot>
    <slot name="content" :item="contentData">----------content is not implemented-----------</slot>
    <slot name="footer">----------footer is not implemented-----------</slot>

<h3>outer</h3>
<button @click="onClick">click to change data in header</button>
</div>
</template>
<script>
import Vue from "vue"
import Component from "vue-class-component"

@Component({})
export default class Layout extends Vue{
    headerData = {name: 'first header', btns: 3}
    contentData = {name: 'content data'}
    onClick(){
        this.headerData = {name: 'super header', btns: 4};
    }
}
</script>
<style scoped>

.layout__content{
    display:flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
    height: 500px;    
    width: 100%;
}
</style>