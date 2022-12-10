<template>
  <div class="main">
    <div class="treeSelf">
      <drag-tree
        :data="data"
        :allowDrag="allowDrag"
        :allowDrop="allowDrop"
        :defaultText="'New Node'"
        @current-clicked="curNodeClicked"
        @drag="dragHandler"
        @drag-enter="dragEnterHandler"
        @drag-leave="dragLeaveHandler"
        @drag-over="dragOverHandler"
        @drag-end="dragEndHandler"
        @drop="dropHandler"
        :disableDBClick="false"
        expand-all
      >
      </drag-tree>
    </div>
    <div class="showSec">
      <pre>{{ formatData }}</pre>
    </div>
  </div>
</template>

<script>
import { DragTree } from "./drag-tree";

export default {
  components: {
    DragTree,
  },
  data() {
    return {
      en: false,
      data: [
        {
          name: "Node 0-0",
          id: 0,
          children: [
            {
              name: "Node 1-1",
              id: 3,
              children: [
                {
                  name: "Node 2-1",
                  id: 4,
                  children: [],
                },
                {
                  name: "Node 2-2",
                  id: 10,
                  children: [],
                },
              ],
            },
            {
              name: "Node 1-2",
              id: 13,
              children: [],
            },
          ],
        },
        {
          name: "Node 0-1",
          id: 14,
          children: [],
        },
      ],
    };
  },
  computed: {
    formatData() {
      return JSON.stringify(this.data, null, 2);
    },
  },
  methods: {
    allowDrag(model, component) {
      return false;
    },
    allowDrop(model, component) {
      return false;
    },
    curNodeClicked(model, component) {
      // 当前被点击节点的model和其所在组件.
      // console.log('curNodeClicked', model, component);
    },
    dragHandler(model, component, e) {
      // console.log('dragHandler: ', model, component, e);
    },
    dragEnterHandler(model, component, e) {
      // console.log('dragEnterHandler: ', model, component, e);
    },
    dragLeaveHandler(model, component, e) {
      // console.log('dragLeaveHandler: ', model, component, e);
    },
    dragOverHandler(model, component, e) {
      // console.log('dragOverHandler: ', model, component, e);
    },
    dragEndHandler(model, component, e) {
      // console.log('dragEndHandler: ', model, component, e);
    },
    dropHandler(model, component, e) {
      // console.log('dropHandler: ', model, component, e);
    },
  },
};
</script>