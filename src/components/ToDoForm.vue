<template>
  <form @submit.prevent="onSubmit">
    <h2 class="label-wrapper">
      <label class="label__lg" for="new-todo-input"> What needs to be done? </label>
    </h2>
    <input
      class="input__lg"
      type="text"
      id="new-todo-input"
      name="new-todo"
      autocomplete="off"
      v-model.trim="label"
    />
    <button class="btn btn__primary btn__lg" type="submit">Add</button>
  </form>
</template>

<script>
  export default {
    methods: {
      onSubmit() {
        if(!this.label) return;
        this.$emit("todo-added", this.label);
        this.label = "";
      }
    },
    data() {
      return {
        label: ""
      };
    }
  };
</script>
