<template>
  <section id="message">
    <h2>留言</h2>
    <div class="messageboard">
      <Messagelist ref="messagelist" v-on:sendCount="updateCount"/>
      <Pagination ref="pagination"/>
      <form>
        <div class="inputWrapper">
          <label for="name">姓名</label>
          <input type="text" name="name" class="name" placeholder="请输入姓名" v-model.trim="name" v-on:click="hide1">
          <span class="warning" v-show="warning1">
            <svg class="icon" aria-hidden="true">
              <use xlink:href="#icon-warning"></use>
            </svg>
            请输入您的姓名
          </span>
        </div>
        <div class="inputWrapper">
          <label for="content">内容</label>
          <textarea name="content" class="content" placeholder="请输入留言" v-model.trim="content" v-on:click="hide2"></textarea>
          <span class="warning" v-show="warning2">
            <svg class="icon" aria-hidden="true">
              <use xlink:href="#icon-warning"></use>
            </svg>
            请输入留言内容
          </span>
        </div>
        <input type="reset" class="formButton" value="重置">
        <input type="submit" class="formButton" value="提交" v-on:click.prevent="saveMessage">
      </form>
    </div>
  </section>
</template>

<script>
  const AV = require('leancloud-storage')

  import Messagelist from './Messagelist'
  import Pagination from './Pagination'

  export default {
    name: "Message",
    data(){
      return {
        id: 0,
        name: '',
        content: '',
        warning1: false,
        warning2: false
      }
    },
    components: {
      Messagelist,
      Pagination
    },

    methods: {
      save(id, name, content) {
        let Message = AV.Object.extend('Message')
        let message = new Message()
        message.set('id', id)
        message.set('name', name)
        message.set('content', content)
        return message.save()
      },
      saveMessage() {
        const escapeHTML = str => str.replace(/[&<>'"]/g, tag => ({
          '&': '&amp;',
          '<': '&lt;',
          '>': '&gt;',
          "'": '&#39;',
          '"': '&quot;'
        }[tag] || tag))
        let name = escapeHTML(this.name)
        let content = escapeHTML(this.content)
        if(!name){
          this.warning1 = true
          return
        }else if(!content){
          this.warning2 = true
          return
        }
        this.save(this.id, this.name, this.content).then(message => {
          this.content = ''
          this.$refs.messagelist.loadMessages(parseInt(this.id / 10))
          this.$refs.pagination.clickPage(parseInt(this.id / 10))
        })

      },
      hide1(){
        this.warning1 = false
      },
      hide2(){
        this.warning2 = false
      },
      updateCount(count){
        this.id = count + 1
      }
    }
  }
</script>

<style scoped lang="scss">
  #message{
    form{
      padding: 30px;
      text-align: center;
      .inputWrapper{
        position: relative;
        margin: 0 auto;
        display: flex;
        justify-content: center;
        margin-left: -42px;

        label {
          margin: 10px 0;
          padding: 5px 10px;
        }

        @mixin form {
          width: 320px;
          line-height: 30px;
          margin: 10px 0;
          padding: 0 4px;
          vertical-align: middle;
          color: #3d4451;
          font-size: 16px;
          font-family: "Microsoft YaHei";
          border: 1px solid #cdcfd1;
          border-radius: 4px;
          box-shadow: 0 13px 10px -15px rgba(0, 0, 0, 0.18) inset;
          &::-webkit-input-placeholder {
            color: #999999;
            font-size: 16px;
            font-family: "Microsoft YaHei";
          }
        }

        .name {
          @include form;
        }

        .content {
          @include form;
          resize: none;
        }

        .warning {
          position: absolute;
          top: 16px;
          right: 80px;
          color: red;
          font-size: 14px;
          svg {
            fill: red;
            vertical-align: -2px;
          }
        }
      }
      .formButton{
        margin: 10px 16px;
        padding: 0 8px;
        line-height: 30px;
        font-size: 16px;
        font-family: "Microsoft YaHei";
        color: #3d4451;
        background-color: #efefef;
        border: 1px solid #cdcfd1;
        border-radius: 4px;
        cursor: pointer;
        &:hover{
          box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.18), 0 3px 4px 0 rgba(0, 0, 0, 0.15);
          border: 1px solid #e6686a;
          background-color: #e6686a;
          color: #ffffff;
        }
      }
    }
  }
</style>
