<template>
  <div class="hello">
    
    <cartesian-component
      :component="BaseButton"
      :label="['label 1', 'label 2']"
      :disabled="[true, false]"
      :color="['#969A97','#D6D1CD','#E5ECE9']"
    />
  </div>
</template>

<script>
import BaseButton from "./BaseButton";
import CartesianComponent from "./CartesianComponent";

export default {
  name: "HelloWorld",
  components: {
   // BaseButton,
    CartesianComponent
  },
  props: {
    msg: String
  },
  data() {
    return {
      BaseButton: BaseButton
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
