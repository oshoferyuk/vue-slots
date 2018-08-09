<template>
<div>
<div @click="onClick">
  this is app message: {{message}}
</div>
<Layout>

<!-- pass data from Layout where we define slot as a property -->
<div slot="header" slot-scope="row">
  <Header :param="row"></Header>
</div>

<!-- pass data from Layout where we define slot inside -->
<!-- <Header slot="header" slot-scope="row">{{row}}</Header> --> 

<h1 slot="content" slot-scope="content">this is content</h1>

</Layout>
<slot name="footer"></slot>
</div>
</template>
<script>
import Vue from "vue"
import Component from "vue-class-component"
import { Prop } from 'vue-property-decorator'
import Layout from "./Layout"
import Header from "./Header"

@Component({  
  components: {Layout, Header},
  props:{
    initialMessage:{}
  }  
})
export default class App extends Vue{  
  constructor(){
    super();
    this.message = this.initialMessage;
  }  
  onClick(){
    
    this.message = "goodbye!";
  }

}
</script>