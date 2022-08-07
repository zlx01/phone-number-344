<template>
  <div class="about">
    <van-field
      v-model="phoneNumberInput"
      type="digit"
      label="手机号"
      :formatter="formatter"
      maxlength="13"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      phoneNumberInput: "",
    };
  },
  computed: {
    phoneNumber() {
      return this.phoneNumberInput.replace(/\s/g, "");
    },
  },
  methods: {
    formatter(value) {
      return value
        .replace(/\s/g, "")
        .replace(/(\d{3})(\d{0,4})(\d{0,4})/, "$1 $2 $3")
        .trim();
    },
  },
};
</script>
