<template>
  <ol class="messageList">
    <li v-for="message in messages" v-bind:key="message.attributes.id">
      <div class="count">{{message.attributes.id + 1}}#</div>
      <div class="name">{{message.attributes.name}}</div>
      <div class="content">{{message.attributes.content}}</div>
    </li>
  </ol>
</template>

<script>
  const AV = require('leancloud-storage')

  export default {
    name: "MessageList",
    data(){
      return {
        messages: []
      }
    },
    created(){
      AV.init({
        appId: "XnxwXJqtmOYB6zwVkRo4uhbf-MdYXbMMI",
        appKey: "USHL2gvq84aLkrCae9wii0Wo"
      })
    },
    mounted(){
      this.loadMessages()
      
    },
    methods: {
      fetch(){
        let query = new AV.Query('Message')
        return query.find()
      },
      loadMessages(){
        this.fetch().then(messages => {
          this.messages = messages
          this.$emit('sendCount', messages[messages.length - 1].attributes.id || 0)
        })
      }
    }
  }
</script>

<style scoped lang="scss">
  .messageList{
    margin-top: 5px;
    border-top: 1px solid #dedede;
    > li{
      padding: 12px 0;
      border-bottom: 1px solid #dedede;
      .count{
        float: right;
        color: #999999;
      }
      .name{
        font-weight: bold;
        margin-bottom: 8px;
      }
    }
  }
</style>
