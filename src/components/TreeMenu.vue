<template>
  <div class="tree-menu">
    <div class="label-wrapper" :style="indent" @click="toggleChildren">{{ label }}</div>
    <TreeMenu
      v-show="showChildren"
      v-for="(node, ind) in nodes"
      :nodes="node.nodes"
      :label="node.label"
      :depth="depth + 1"
      :key="ind"
    >
    </TreeMenu>
  </div>
</template>
<script>
  export default {
    props: [ 'label', 'nodes', 'depth' ],
    name: 'TreeMenu',
    data () {
      return {
        showChildren: false
      }
    },
    computed: {
      indent() {
        return { transform: `translate(${this.depth * 50}px)` }
      }
    },
    methods: {
      toggleChildren () {
        this.showChildren = !this.showChildren
      }
    }
  }
</script>
<style lang="scss"  scoped>
  .tree-menu {
    .label-wrapper {
    padding-bottom: 10px;
    margin-bottom: 10px;
    border-bottom: 1px solid #ccc;
      .has-children {
        cursor: pointer;
      }
    }
  }
</style>
