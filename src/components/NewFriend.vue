<template>
  <form action="" @submit.prevent="submitData">
    <div>
      <label for="">Name:</label>
      <input type="text" required v-model="enteredName" />
    </div>
    <div>
      <label for="">Phone:</label>
      <input type="tel" required v-model="enteredPhone" />
    </div>
    <div>
      <label for="">Email:</label>
      <input type="email" required v-model="enteredEmail" />
    </div>
    <div>
      <button>Add Friend</button>
    </div>
  </form>
</template>
<script>
export default {
  emits: ["add-contact"],
  data() {
    return {
      enteredName: "",
      enteredPhone: "",
      enteredEmail: "",
    };
  },
  methods: {
    submitData() {
      this.$emit(
        "add-contact",
        this.enteredName,
        this.enteredPhone,
        this.enteredEmail
      );
      this.enteredName = "",
      this.enteredPhone = "",
      this.enteredEmail = "";
    },
  },
};
</script>
