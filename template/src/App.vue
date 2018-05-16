<template lang="pug">
  .app
    img(src="./assets/logo.png")
    {{#router}}
    router-view
    {{else}}
    HelloWorld
    {{/router}}
</template>


<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
{{#unless router}}
import HelloWorld from '{{ srcAlias }}/components/HelloWorld'
{{/unless}}

{{#router}}@Component{{else}}@Component({
  components: {
    HelloWorld
  }
}){{/router}}
export default class AppComponent extends Vue {}
</script>

<style lang="scss">
.app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
