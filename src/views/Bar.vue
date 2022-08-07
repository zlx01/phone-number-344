<template>
  <div class="about">
    <!-- 输入手机号，调起手机号键盘 -->
    <!--tel可以输入数字，字母，中文，不能输入空白，但值可以包含空白-->
    <!--digit只能输入数字，无法输入空白，值也不能包含空白-->
    <van-field
      v-model="phoneNumberInput"
      type="tel"
      label="手机号"
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
