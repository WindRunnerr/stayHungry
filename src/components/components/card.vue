<template>
    <div class="sh-card-wrapper" @click="cardClick">
        <hooks></hooks>
        <div class="sh-card"
            :style="cardStyle"
        >
            <h3>标题</h3>
            <div class="content-wrapper">
                <p>内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容内容</p>
            </div>
        </div>
    </div>
</template>

<script>
    import hooks from "./hooks";
  export default {
    name: "card",
    props: {
      type: {
        type: String,
        default: 'list'
      }
    },
    methods: {
      cardClick () {
        this.$parent.dialogCardVisible = true
      }
    },
    computed: {
      cardStyle () {
        return this.type === 'list' ? {
          height: '150px',
          width: '400px'
        } : {
          height: '800px',
          width: '1000px'
        }
      }
    },
    components: { hooks }
  }
</script>

<style lang="less" scoped>
    .sh-card-wrapper {
        transition: all 0.6s;
        margin: 20px;
        display: inline-block;
        .sh-card {
            display: inline-block;
            width: 400px;
            height: 150px;
            position: relative;
            color: #333333;
            border-radius: 10px;
            border: 1px solid rgba(00,00,00,.3);
            box-shadow: 0px 15px 15px 0px rgba(00,00,00,.3);
            background: rgba(256,256,256,.9);
            h3 {
                line-height: 64px;
            }
            .content-wrapper {
                text-align: left;
                text-indent: 2em;
                padding: 0 2em 2em;
            }
        }
    }
</style>