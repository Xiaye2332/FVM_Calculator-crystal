<script setup>
import {useDark} from '@vueuse/core'

const isDark = useDark()


</script>
<template>
  <el-form ref="form" label-width="100px" :inline="true">
    <el-form-item label="深色模式">
      <el-switch size="laige" v-model="isDark"/>

    </el-form-item>
  </el-form>
  <h5>说明:</h5>
  <span class="notice">1.计算结果为通过计算机模拟大量样本情况下的最终结果<br>2.成功率加成为打开背包后鼠标移动到“属性加成”区域显示的“卡片成功率+ xx%”字样<br>3.保险节省量是在面板显示的保险情况下，通过点保险可以节省的水晶<br>4.节省水晶价是上述节省的水晶除以保险需要消耗的点券<br><br> 如果你有任何疑问或建议，欢迎参加我们的<a
      href="https://survey.xiayeqz.com:3999/s/QEFoBL" target="_blank" style="color: #409EFF">问卷调查</a>，交流群301119931</span>
  <el-divider></el-divider>
  <h5>贡献者:</h5>
  <a href="https://github.com/czyczy608" target="_blank">
    <el-tooltip content="czyczy608" placement="top">
      <el-avatar
          src="https://avatars.githubusercontent.com/u/57560140?v=4">
      </el-avatar>

    </el-tooltip>
    &ensp;</a>
  <a href="https://github.com/Xiaye2332" target="_blank">
    <el-tooltip content="Xiaye2332" placement="top">
      <el-avatar
          src="https://avatars.githubusercontent.com/u/86192453?v=4">
      </el-avatar>
    </el-tooltip>
    &ensp;</a>
  <a href="https://github.com/superboyyy" target="_blank">
    <el-tooltip content="superboyyy" placement="top">
      <el-avatar
          src="https://avatars.githubusercontent.com/u/75305545?v=4">
      </el-avatar>
    </el-tooltip>
  </a>
  <span class="notice"><br><br>本页面遵照GPLv3协议开放源代码，您可以自由传播和修改，转载请注明作者和出处<br><a
      href="https://github.com/Xiaye2332/FVM_Calculator-crystal" target="_blank"><img
      src="https://img.shields.io/badge/Github-FVM_Calculator_crystal%20v1.3-purple"></a></span>
  <el-divider></el-divider>
  <h5>更新日志:</h5>
  <span class="notice">2023/2/19 &nbsp;Beta版发布<br>2023/2/22 &nbsp;RC版发布，新增了可选目标星级功能，在四叶草下拉框内查看所选四叶草对应的卡牌等级<br>2023/2/22 &nbsp;v1.0 正式版发布<br>2023/2/28 &nbsp;v1.1 简洁化了部分说明<br>2023/3/10 &nbsp;v1.2 重构部分函数，计算结果更精确<br>2023/3/25 &nbsp;v1.3 重构四叶草计算函数，修复部分bug<br><br><br></span>
</template>

<style scoped>


*, :before, :after {
  box-sizing: border-box;
}


img {
  max-width: 100%;
}

.page-content .doc-content a {
  display: inline-flex;
  align-items: center;
}


a {
  font-weight: 500;
  text-decoration: inherit;
}

a, area, button, [role=button], input, label, select, summary, textarea {
  touch-action: manipulation;
}

body {
  margin: 0;
  width: 100%;
  min-width: 320px;
  min-height: 100vh;
  line-height: 1.4;
  font-size: 16px;
  font-weight: 400;
  direction: ltr;
  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  transition: background-color var(--el-transition-duration-fast);
}

body {
  font-family: Helvetica Neue, Helvetica, PingFang SC, Hiragino Sans GB, Microsoft YaHei, \5fae\8f6f\96c5\9ed1, Arial, sans-serif;
  font-weight: 400;
  font-size: var(--el-font-size-base);
  color: var(--el-text-color-primary);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -webkit-tap-highlight-color: transparent;
}


.notice {
  font-family: Helvetica Neue, Helvetica, PingFang SC, Hiragino Sans GB, Microsoft YaHei, \5fae\8f6f\96c5\9ed1, Arial, sans-serif;
  font-weight: 400;
  font-size: var(--el-font-size-base);
  color: var(--el-text-color-primary);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -webkit-tap-highlight-color: transparent;
  margin-bottom: 50px;
}


</style>
