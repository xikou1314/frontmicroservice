<template>
  <div class="box">
    iframe
    <button @click="sendMsg">发送信息到iframe3</button>
    <micro src="/test/vuedemo3/" name="vuedemo3" type="iframe" class="height"></micro>
  </div>
</template>

<script>
  import micro from '../components/micro';

  export default {
    name: 'IframeBox',
    components: { micro },
    props: {
    },
    computed: {

    },
    created() {
      console.log('创建');
    },
    methods: {
      sendMsg() {
        // document.getElementById('vuedemo3').contentWindow.onBaseMessage('这是main传递给iframe3的信息');
        window.BaseMessager.trigger('vuedemo3', '这是main传递给iframe3的信息');
      }
    }
  };
</script>

<style lang="scss" scoped>
.box {
    margin: 0 auto;
}
.height {
  height: 800px;
}
</style>
