<script>
import Button from "./components/Button.vue";

export default {
  name: "App",
  components: {
    Button,
  },
  data() {
    return {
      name2: "hello world",
    };
  },
  methods: {
    changeName() {
      this.name2 = "hello world 2";
    },
    resetName() {
      this.name2 = "hello world";
    },
    handleOnChangedName(event) {
      this.name2 = event.target.value;
    },
  },
};
</script>

<template>
  <h1>{{ name2 }}</h1>
  <input type="text" :value="name2" @input="name2 = $event.target.value" />
  <Button class="btn-primary" @click="changeName" text="Change Name" />
  <Button @click="resetName" text="Reset Name" />

  <hr />
</template>

<style>
.btn-primary {
  background-color: #007bff;
  border-color: #007bff;
  color: #fff;
}
</style>
