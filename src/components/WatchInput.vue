<template>
  <div>
    <van-cell-group>
      <van-field
        v-model="phoneNumberInput"
        type="tel"
        label="手机号"
        maxlength="13"
        placeholder="请输入手机号"
      />
    </van-cell-group>
  </div>
</template>

<script>
export default {
  data() {
    return {
      phoneNumberInput: "",
    };
  },
  watch: {
    phoneNumberInput(val, oldValue) {
      if (val.length > oldValue.length) {
        // 文本框中输入
        if (val.length === 4 || val.length === 9) {
          let length = val.length;
          this.phoneNumberInput =
            val.substr(0, length - 1) + ` ${val[length - 1]}`;
        }
      } else {
        // 文本框中删除
        if (val.length === 9 || val.length === 4) {
          this.phoneNumberInput = this.phoneNumberInput.replace(/\s*$/g, "");
        }
      }
    },
  },
  computed: {
    phoneNumber() {
      return this.phoneNumberInput.replace(/\s/g, "");
    },
  },
};
</script>
