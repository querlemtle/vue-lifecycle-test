<template>
  <div id="app">
    <h5>Hint: 請開啟 console 觀察</h5>
    <header ref="header">
      {{ header }}
      <Nav :init-nav.sync="nav" />
    </header>
    <button class="update-btn" @click.prevent.stop="updateContent">
      Update DOM
    </button>
    <button class="destroy-btn" @click.prevent.stop="destroyComponent">
      Destroy component
    </button>
  </div>
</template>

<script>
import Nav from "./components/Nav.vue";

export default {
  name: "App",
  data() {
    return {
      header: "old header",
      nav: "old nav"
    };
  },
  methods: {
    updateContent() {
      this.header = "new header";
      this.nav = "new nav";
    },
    destroyComponent() {
      this.$destroy();
    },
  },
  components: {
    Nav,
  },
  beforeCreate() {
    console.log("<header> beforeCreate");
    console.log("$el in beforeCreate: ", this.$el);
    console.log("data in beforeCreate: ", this.$data);
    console.log("<header> in beforeCreate: ", this.$refs.header);
    console.log("----------------");
  },
  created() {
    console.log("<header> created");
    console.log("$el in created: ", this.$el);
    console.log("data in created: ", this.$data);
    console.log("<header> in created: ", this.$refs.header);
    console.log("----------------");
  },
  beforeMount() {
    console.log("<header> beforeMount");
    console.log("$el in beforeMount: ", this.$el);
    console.log("<header> in beforeMount: ", this.$refs.header);
    console.log("----------------");
  },
  mounted() {
    console.log("<header> mounted");
    console.log("$el in mounted: ", this.$el);
    console.log("<header> in mounted: ", this.$refs.header);
    console.log("----------------");
  },
  beforeUpdate() {
    console.log("<header> beforeUpdate");
    console.log("$el in beforeUpdate: ", this.$el);
    console.log("data in beforeUpdate: ", this.$data);
    console.log("<header> in beforeUpdate: ", this.$refs.header);
    console.log("----------------");
  },
  updated() {
    console.log("<header> updated");
    console.log("$el in updated: ", this.$el);
    console.log("data in updated: ", this.$data);
    console.log("<header> in updated: ", this.$refs.header);
    console.log("----------------");
  },
  beforeDestroy() {
    console.log("<header> beforeDestroy");
    console.log("$el in beforeDestroy: ", this.$el);
    console.log("<header> in beforeDestroy: ", this.$refs.header);
    console.log("----------------");
  },
  destroyed() {
    console.log("<header> destroyed");
    console.log("$el in destroyed: ", this.$el);
    console.log("data in destroyed: ", this.$data);
    console.log("<header> in destroyed: ", this.$refs.header);
    console.log("----------------");
  },
};
</script>

<style scoped>
header {
  padding: 0.5rem;
  width: 50%;
  height: 100px;
  background-color: #cef3f3;
}

.update-btn {
  margin-right: 1rem;
}

.destroy-btn {
  margin-top: 1rem;
  background-color: #ef233c;
  border: 2px solid #a4161a;
  color: #fff;
}
</style>