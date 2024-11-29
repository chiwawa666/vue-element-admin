<template>
  <div class="tab-container">
    <div class="tabs">
      <!-- tab导航 -->
      <div
        v-for="tab in tabs"
        :key="tab.name"
        @click="handleClick(tab, $event)"
        :class="['tab_items', { active: activename === tab.name }]"
      >
        {{ tab.label }}
      </div>
    </div>

    <!-- tabs内容 -->
    <div class="tab-content">
      <div v-for="tab in tabs" :key="tab.name">
        <div v-show="activename === tab.name">{{ tab.content }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "TabPane",
      activename: "first",
      tabs: [
        { name: "first", label: "Tab 1", content: "Tab 1 content" },
        { name: "second", label: "Tab 2", content: "Tab 2 content" },
        { name: "third", label: "Tab 3", content: "Tab 3 content" },
      ],
    };
  },
  methods: {
    handleClick(tab, event) {
      this.activename = tab.name;
    },
  },
};
</script>
<style lang="scss" scoped>
.tabs {
  display: flex;
  border: 1px solid #ccc;
  padding: 10px;
  .tab_items {
    padding: 10px;
    cursor: pointer;
    &.active {
      color: rgb(47, 0, 255);
    }
  }
}
.tab-content {
  margin-top: 10px;
  border: 1px solid #ccc;
  padding: 10px;
}
</style>>

