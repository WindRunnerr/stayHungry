<template>
    <div class="home">
        <card @click.capture="dialogCardVisible = true"></card>
        <card @click.capture="dialogCardVisible = true"></card>
        <card @click.capture="dialogCardVisible = true"></card>
        <card @click.capture="dialogCardVisible = true"></card>
        <div id="modalBox" v-if="dialogCardVisible" @click.self="dialogCardVisible = false">
            <i class="el-icon-close close"></i>
            <Carousel3d
                    style="text-align: center"
                    :width="1000"
                    :height="900"
            >
                <Slide :index="0"><card type="card"></card></Slide>
                <Slide :index="1"><card type="card"></card></Slide>
                <Slide :index="2"><card type="card"></card></Slide>
                <Slide :index="3"><card type="card"></card></Slide>
            </Carousel3d>
        </div>
    </div>
</template>

<script>
  import card from "./components/card";
  import { Carousel3d, Slide } from 'vue-carousel-3d';

  export default {
    name: "home",
    components: {card,Carousel3d,Slide},
    data () {
      return {
        dialogCardVisible: false,
        screenWidth: 0,
        screenHeight: 0
      }
    },
    mounted () {
      window.hehe = this
    },
    methods: {
    }
  }
</script>

<style lang="less">
    .home {
        .carousel-3d-slide {
            text-align: center!important;
            border: none!important;
            background: inherit!important;
        }
        position: relative;
        padding: 30px 50px;

        &:before {
            content: '';
            display: block;
            width: 100%;
            height: 100%;
            position: fixed;
            top: 0;
            right: 0;
            bottom: 0;
            left: 0;
            background: url('../assets/school_girl.jpg');
            opacity: 0.3;
            pointer-events: none;
        }

        opacity: 1;

        .kk {
            background: red;
            border: 1px solid white;
        }

        .clearfix {
            /*display: none;*/
        }

        #boxFixed {
            background: #333333;
        }
        .isFixed {
            position: fixed;
            top: 0;
            left: 0;
            z-index: 2;
        }
        #modalBox {
            position: fixed;
            left: 0;
            top: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,.3);
        }
    }
</style>