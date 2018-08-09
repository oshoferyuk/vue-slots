<template>
<div>
<div>HEADER {{this.param}}</div>
<slot></slot>
</div>
</template>
<script>
import Vue from "vue"
import Component from "vue-class-component"

@Component({   
    props:{
    param:{}
  }  
})
export default class Header extends Vue{    
    constructor(){
        super();        
    }
}
</script>
<style scoped>

</style>