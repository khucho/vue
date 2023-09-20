<!-- <template>
  <div class="container bg-light">
    Bootstrap Install
    <div class="row">
      <div class="col-md-6 bg-primary">
        Div1
      </div>
      <div class="col-md-6 bg-warning">
        Div2
      </div>
    </div>
  </div>
</template> -->
<template>
  <MethodComponent></MethodComponent>
</template>
<script>
import MethodComponent from "./components/MethodComponent.vue";
export default{
  name:'App',
  components:{
    MethodComponent
  }
}
</script>