<template>
  <span>
    <el-col :span="15" style="background-color: #323335;border-radius: 10px;height: 90%;overflow: auto;">
      <!--  上边栏  -->
      <div style="display: flex; align-items: center;padding-left: 1%; height: 9%">
        <el-avatar shape="square" style="margin-right: 1%;cursor:pointer;"/>
        <div style="border: 1px solid #16334a">徐志摩</div>
      </div>

      <!--  窗口  -->
      <div style="height: 80%;overflow: auto;">
        <!--  接收信息  -->
        <div style="width: 90%;display: flex;align-items: center;margin-left: 1%;margin-top: 1%;">
          <span style="margin-right: 6px">
            <el-avatar shape="square" style="cursor:pointer"/>
          </span>
          <div style="background-color: floralwhite;border-radius: 10px;">
            <div style="padding: 15px;font-size: 14px;word-break: break-all;">
              11111111111
            </div>
          </div>
        </div>

        <!--  主动发送  -->
        <div
            style="float: right;width: 70%;margin-right: 1%;margin-top:1%;display: flex; align-items: center;justify-content: flex-end">
          <div style="margin-left: 1.6%;background-color: #12CEC2FF;border-radius: 10px;display: inline-block;">
            <div style="padding: 15px;font-size: 14px;word-break: break-all">
              2222222222222222222222222222222222222222222222
            </div>
          </div>
          <span style="margin-left: 6px">
            <el-avatar shape="square" style="cursor:pointer;"/>
          </span>
        </div>
      </div>

      <!-- 输入框 -->
      <div style="margin-top: 1%;height: 8%;width: 48vw">
        <span>语音、</span>
        <el-input id="chat-input" placeholder="请开始你的表演......" type="text" style="width: 70%" v-model="chatMsg"/>
        <Emoji/>
        <span>截图、</span>
        <span>文件、</span>
        <span>发送</span>
      </div>
    </el-col>
  </span>
</template>

<script>


import Emoji from "@/component/index/window/Emoji";

export default {
  name: "Window",

  components: {
    Emoji
  },

  data() {
    return {
      chatMsg: '',
      input: '',
      search: '',
    }
  },

  method: {
    append(emoji) {
      this.input += emoji
    },
  },

  directives: {
    focus: {
      inserted(el) {
        el.focus()
      },
    },
  },
}
</script>

<style scoped>
#chat-input {
  border-radius: 20px;
  font-size: 14px;
  white-space: pre-wrap;
  overflow-y: auto;
  resize: vertical;
}
</style>
