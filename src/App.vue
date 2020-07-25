<template>
  <div id="app">
    <TreeMenu :label="tree.label"
              :nodes="tree.nodes"
              :depth="0"
    ></TreeMenu>
  </div>
</template>

<script>
  let tree = {
    label: 'root',
    nodes: [
      {
        label: 'item1',
        nodes: [
          {
            label: 'item1.1'
          },
          {
            label: 'item1.2',
            nodes: [
              {
                label: 'item1.2.1'
              }
            ]
          }
        ]
      },
      {
        label: 'item2'
      }
    ]
  };
  import TreeMenu from '@/components/TreeMenu'
  export default {
    name: 'app',
    data () {
      return {
        tree
      }
    },
    components: {
      TreeMenu
    }
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
}
</style>
