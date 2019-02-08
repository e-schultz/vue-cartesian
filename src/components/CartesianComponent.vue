<template>
  <section>
      
    <section v-for="(combo, index) in combos" :key="index">
        
      <component :is="component" v-bind="combo" :key="index"/>
      <hr/>
    </section>
  </section>
</template>
<script>
import { map, pipe, xprod, unnest, reduce, mergeAll } from "ramda";

const arr = v => (Array.isArray(v) ? v : [v]);
const cartesianProduct = ({ theme = {}, ...props }) => {
 console.log(theme);
 const xproduct = reduce(
    pipe(
      xprod,
      map(unnest)
    ),
    [[]]
  );

  const parsedProps = Object.keys(props).reduce((acc, k) => {
    console.log(props[k]);
    return acc.concat([arr(props[k]).map(v => ({ [k]: v }))]);
  }, []);

  return map(mergeAll, xproduct(parsedProps));
};
export default {
  name: "CartesianComponent",
  inheritAttrs: false,
  props: ["component"],
  computed: {
    combos() {
      return cartesianProduct(this.$attrs);
    }
  }
};
</script>
