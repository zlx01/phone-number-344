<template>
  <div class="home">
    <ul>
      <li>输入手机号，调起手机号键盘</li>
      <li>tel 可以输入数字，字母，中文，不能输入空白，但值可以包含空白</li>
      <li>digit 只能输入数字，无法输入空白，值也不能包含空白</li>
    </ul>
    <br />
    <h2>type="tel"，通过监听属性变化增减空格，通过computed获取真实输入</h2>
    <WatchInput> </WatchInput>
    <br />
    <h2>type="digit"，通过formatter属性控制显示，通过computed获取真实输入</h2>
    <Formatter> </Formatter>
  </div>
</template>

<script>
// @ is an alias to /src
import WatchInput from "@/components/WatchInput.vue";
import Formatter from "@/components/Formatter.vue";

export default {
  name: "Home",
  components: {
    WatchInput,
    Formatter,
  },
};
</script>
