<template>
    <slider class="slider" auto-play="true" interval="5000">
        <div class="frame" v-for="img in imageList" @click="jumpDetail()">
            <image class="image" resize="cover" :src="img.src"></image>
        </div>
        <indicator class="indicator"></indicator>
    </slider>
</template>
<script>
    import {YXBANNERS} from './config'

    export default {
        created() {
            this.getYXBanners()
        },
        data() {
            return {
                imageList: [],
            }
        },
        methods: {
            getYXBanners() {
                this.imageList = YXBANNERS
            },
            jumpDetail(){
                this.$router.open({
                    name: 'detail'
                })
            }
        }
    }
</script>

<style scoped>
    .iconfont {
        font-family: iconfont;
    }

    .image {
        width: 750px;
        height: 430px;
    }

    .slider {
        width: 750px;
        height: 430px;
    }

    .frame {
        width: 750px;
        height: 430px;
        position: relative;
    }

    .indicator {
        width: 750px;
        height: 40px;
        item-color: white;
        item-selected-color: #b4282d;
        item-size: 12px;
        position: absolute;
        bottom: 10px;
        right: 0px;
    }
</style>
