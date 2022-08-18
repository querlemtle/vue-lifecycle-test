<template>
  <nav ref="nav">{{ initNav }}</nav>
</template>

<script>
export default {
  name: "Nav",
  props: {
    initNav: {
      type: String,
    },
  },
  data() {
    return {
      nav: this.initNav,
    };
  },
  computed: {
    navHeader: {
      get() {
        return this.initNav;
      },
      set(value) {
        // update nav title
        this.$emit("update-nav", value);
      },
    },
  },
  beforeCreate() {
    console.log("<nav> beforeCreate");
    console.log("$el in beforeCreate: ", this.$el);
    console.log("data in beforeCreate: ", this.$data);
    console.log("<nav> in beforeCreate: ", this.$refs.nav);
    console.log("----------------");
  },
  created() {
    console.log("<nav> created");
    console.log("$el in created: ", this.$el);
    console.log("data in created: ", this.$data);
    console.log("<nav> in created: ", this.$refs.nav);
    console.log("----------------");
  },
  beforeMount() {
    console.log("<nav> beforeMount");
    console.log("$el in beforeMount: ", this.$el);
    console.log("<nav> in beforeMount: ", this.$refs.nav);
    console.log("----------------");
  },
  mounted() {
    console.log("<nav> mounted");
    console.log("$el in mounted: ", this.$el);
    console.log("<nav> in mounted: ", this.$refs.nav);
    console.log("----------------");
  },
  beforeUpdate() {
    console.log("<nav> beforeUpdate");
    console.log("$el in beforeUpdate: ", this.$el);
    console.log("data in beforeUpdate: ", this.$data);
    console.log("<nav> in beforeUpdate: ", this.$refs.nav);
    console.log("----------------");
  },
  updated() {
    console.log("<nav> updated");
    console.log("$el in updated: ", this.$el);
    console.log("data in updated: ", this.$data);
    console.log("<nav> in updated: ", this.$refs.nav);
    console.log("----------------");
  },
  beforeDestroy() {
    console.log("<nav> beforeDestroy");
    console.log("$el in beforeDestroy: ", this.$el);
    console.log("<nav> in beforeDestroy: ", this.$refs.nav);
    console.log("----------------");
  },
  destroyed() {
    console.log("<nav> destroyed");
    console.log("$el in destroyed: ", this.$el);
    console.log("data in destroyed: ", this.$data);
    console.log("<nav> in destroyed: ", this.$refs.nav);
    console.log("----------------");
  },
};
</script>

<style scoped>
nav {
  width: 50%;
  height: 50%;
  background-color: #f2c1bb;
}
</style>
